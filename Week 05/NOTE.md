学习笔记
##proxy概述
- 专门为底层库设计的特性
- 基本用法

`const p = new Proxy(target, handler)`

- target: 要使用 Proxy 包装的目标对象
- handler: 一个通常以函数作为属性的对象，各属性中的函数分别定义了在执行各种操作时代理 p 的行为。
- 举例：

```
const handler = {
    get: function(obj, prop) {
        return prop in obj ? obj[prop] : 37;
    }
};

const p = new Proxy({}, handler);
p.a = 1;
p.b = undefined;

console.log(p.a, p.b);      // 1, undefined
console.log('c' in p, p.c); // false, 37
```

- 参考https://www.jianshu.com/p/77eaaf34e732
- set函数必须return一个boolean值，所以使用return Reflect.set(target, key, value),相当于

```
target[key] = value;
return true;
```

- 如果一个对象既想设置起来像普通对象一样，又可以监听，可以使用Proxy
- 与getter, setter最主要的区别就是proxy object即使设置一个没有的属性，也会默认出发set的值

##模仿reactive
- vue中effect:跟踪更改它的函数, 我们在 proxy 中的 getter 中执行此操作，称为 effect
- trigger:触发函数以便它可以更新最终值：我们在 proxy 中的 setter 中进行该操作，名为 trigger

## reactive作用
- 半成品的双向绑定，负责从数据到dom元素的一条线的监听，或是任何本地输入