---
layout: post
categories: Design
title: 异常先行
---

一个软件系统，只是可以提供相应的[功能](https://zh.wikipedia.org/wiki/%E5%8A%9F%E8%83%BD%E9%9C%80%E6%B1%82)，还不能算是完成了预期的目标，

它还要满足一些[非功能](https://zh.wikipedia.org/wiki/%E9%9D%9E%E5%8A%9F%E8%83%BD%E6%80%A7%E9%9C%80%E6%B1%82)方面的限制条件。

<br/>

[健壮性](https://zh.wikipedia.org/wiki/%E5%81%A5%E5%A3%AE%E6%80%A7_(%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%A7%91%E5%AD%A6))就是一个典型的例子，

它反映了系统对于规范要求以外输入情况的处理能力。

<br/>

为了实现健壮性，我们不仅需要考虑所有可能的输入，

更重要的是要考虑**异常流**，即系统在遭遇异常时究竟如何表现。

<br/>

这里有一个常见的误区，那就是，人们为了防止系统崩溃，

不论是否出现错误，总是让它看起来是正常，

这其实是一种**自欺欺人**的做法。

<br/>

这种做法不仅不能够提高系统的健壮性，

反而人为的向定位问题增添了很多障碍，提高了沟通成本，

出错的场景被隐藏掉了，只有接口的提供者才知道原因。

<br/>

那么如何设计一个健壮的系统呢？

本文提供了一些思路。

<br/>

### 1. Fail Fast 哲学

[Fail Fast](http://wiki.c2.com/?FailFast)是[Erlang](https://www.erlang.org/)语言的编程哲学之一，

说的是一个子系统在遇到问题的时候，应该尽早崩溃。

<br/>

常见的`if-return`模式（或者`if-throw`），就是Fail Fast思想的一种应用。

```
function failSlow() {
    if (x != null) {
        // 使用x做一些事情
    }
}

function failFast(x) {
    if (x == null) {
        return;
    }

    // 使用x做一些事情
}
```

以上两个JavaScript函数，表现了不同的处理问题风格。

如果代码后文要用到`x`，且当前没有`x`，那不如**尽早返回**。

<br/>

还有一种写法，

```
function assertPrecondition(x) {
    assert(x == null);

    // 使用x做一些事情
}
```

以上代码，通过`assert`对函数的**前置条件**进行了**断言**。

<br/>

使用`if-return`或者`assert`，会在很大程度上避免嵌套`if`的出现，

否则，我们就不得不在很多`if`条件中编写业务逻辑。

<br/>

例如，以下展示了嵌套`if`的某个场景，

```
if (x != null) {
    if (y > 0) {
        if (z) {
            // 业务逻辑
        }
    }
}
```

<br/>

改成`assert`后，将前置条件与正常的业务逻辑解耦了。

```
assert(x != null);
assert(y > 0);
assert(z);

// 业务逻辑
```

<br/>

### 2. 不要吃掉异常

**如果子系统无法处理某个错误，那就把它抛出来，而不是吃掉它。**

<br/>

下面我们来看一个例子，

```
function application() {
    service();

    // 其他service
}

function service() {
    try {
        // 业务逻辑
    } catch (e) {
        // 什么也不做
        // 或者即使是写日志
    }
}
```

<br/>

以上代码，我们在`application`函数中调用了`service`，

但是`service`吃掉了异常。

<br/>

那么一旦`application`的用户指出了错误，定位问题就是一件麻烦事，

`application`的编写者，要去询问每一个`service`的提供者，到底出现了什么状况。

<br/>

我们再来看下，如果不吃掉异常会怎样，

```
function application() {
    service();

    // 其他service
}

function service() {
    try {
        // 业务逻辑
    } catch (e) {
        // 写日志
        throw e;
    }
}
```

<br/>

以上代码，我们修改了`service`函数，

它确实捕获了异常，但是如果这个异常`service`无法处理，那就向上抛出去。

<br/>

这样的话，甚至根本轮不到`application`的用户指出错误了，

`application`自己都能拿到异常的调用栈信息，

并且，即使由用户指出了，也能不依赖于`service`来定位问题的原因。

<br/>

可能有人会说，如果异常都被抛出了，没有人处理怎么办？

是的，吃掉异常不也是没人处理它吗？

所以，抛出异常就相当于**显式的**向调用者提问，这个异常到底应该如何处理。

<br/>

换句话说，

**异常被静默处理，应该是大家协商后的决定。**

<br/>

### 3. 让异常成为一种约定

异常和异常的处理应该是一体的，它们应该被**统一的**设计和使用。

各个系统的边界处，应该如何反馈异常，以及这些异常应该如何被处理，应该事先被约定好。

这样才会减少冗余的个性化的异常处理逻辑。

<br/>

例如，使用[面向切面编程](https://zh.wikipedia.org/wiki/%E9%9D%A2%E5%90%91%E4%BE%A7%E9%9D%A2%E7%9A%84%E7%A8%8B%E5%BA%8F%E8%AE%BE%E8%AE%A1)，

我们可以在系统的边界上定义一个**异常切面**，统一处理错误。

<br/>

```
function application() {
    MyService.service();

    // 其他service
}

// 装饰器是一个高阶函数
const exceptionAOP = Class => {
    const service = Class.service;

    Class.service = function (...args) {
        try {
            return service.call(this, ...args);
        } catch (e) {
            // 写日志
            throw e;
        }
    };

    return Class;
};

class MyService {
    @exceptionAOP
    static service() {
        // 业务逻辑
    }
}
```

<br/>

以上代码，为了简洁起见，我们用[装饰器](https://tc39.github.io/proposal-decorators/)实现了一个异常切面，

目前，装饰器是[ECMAScript TC39](https://github.com/tc39/proposals) Stage2的特性。

<br/>

在这个切面中，我们统一的将异常写入了日志中，

再将异常抛出。

<br/>

### 4. 主动抛出异常

有了异常切面，我们就不用担心未被捕获的异常了，

向系统中添加一种异常，总是伴随着修改异常切面来完成。

有了这种异常处理机制，我们就可以**主动抛出一些业务异常**了。

<br/>

例如，上文中提到的`assert`，如果不满足前置条件断言，

我们可以主动抛异常。

<br/>

```
// 1. 新增异常
class PreconditionException extends Error { };

const exceptionAOP = Class => {
    const { service } = Class;

    Class.service = function (...args) {
        try {
            return service.call(this, ...args);
        } catch (e) {

            // 2. 新增处理方式
            if (e instanceof PreconditionException) {
                // 写日志，前置条件断言失败
                throw e;
            }

            // 写日志
            throw e;
        }
    };

    return Class;
};

const assert = condition => {
    if (!condition) {
        throw new PreconditionException;
    }
}

class MyService {
    @exceptionAOP
    static service(x) {
        assert(x);

        // 业务逻辑
    }
}
```

<br/>

**注：**

如果认为每次都修改`exceptionAOP`是一件麻烦事，我们可以这样做，

```
// 1. 新增异常
class PreconditionException extends Error { };

// 2. 新增处理方式
exceptionHandler.add({
    exception: PreconditionException,
    handler: e => {
        // 写日志，前置条件断言失败
        throw e;
    }
});
```

<br/>

其中`exceptionHandler`是我们编写的辅助对象，具体实现方式可以灵活选择，

在切面上的用法如下，

```
const exceptionAOP = Class => {
    const service = Class.service;

    Class.service = function (...args) {
        try {
            return service.call(this, ...args);
        } catch (e) {
            // 使用exceptionHandler处理异常
            exceptionHandler.handle(e);
        }
    };

    return Class;
};
```

<br/>

### 5. 先考虑异常处理

在设计系统的时候，异常以及异常处理方式应该事先考虑，

否则人们就会按照各自的便利来编写逻辑，

这样很容易产生**兼容性问题**。

<br/>

例如，有些接口可能会通过**返回异常值**来反馈异常，

而有的接口会通过**上抛异常**来反馈，

这样在处理方式上就很难统一处理，业务逻辑写起来会比较繁琐。

<br/>

即使已经确定为返回异常值的方式，也容易出现以下问题，

```
// 接口1
{
    isSuccess: boolean,
    message: string,
    data: object
}

// 接口2
{
    succeed: boolean,
    msg: string,
    data: object
}
```

以上两个接口的数据类型是不同的，

第一个接口用`isSuccess`来标志异常，第二个用`succeed`，

那么这两个接口的调用者，就不得不**分别处理**它们。

<br/>

因此，这是下层服务返回了两种异常，但是期望它们用相同的方式处理，

这很显然是**系统设计**的不恰当。

<br/>

并且，当我们意识到这个问题的时候，再进行修改就难了，

抛出异常和处理异常的代码要同时修改，是一种**接口变更**，

会涉及兼容性问题。

<br/>

### 结语

我们可能都体会过，知道错误但是不知道原因的那种**憋闷感**，

在整个调用链路上，一环一环的排查，结果发现是某个服务吃掉了异常。

<br/>

如果有日志可循，这还不是难事，最多是花费一些时间，

但如果日志都不健全，定位一个问题简直是难于登天，甚至要手动debug才行。

究其原因可能是，**人们想要隐藏错误，以使得系统看似健壮。**

<br/>

所以，哪有不出错的系统，我们只能**及时修正**。
