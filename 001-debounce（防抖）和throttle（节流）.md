### debounce（防抖）

 触发高频时间后n秒内函数只会执行一次,如果n秒内高频时间再次触发,则重新计算时间。 

```js
const debounce = (fn, time) => {
    let timeout = null;
    return function() {
        clearTimeout(timeout)
        timeout = setTimeout(() => {
            fn.apply(this, arguments);
        }, time);
    }
};
```

使用：

```js
box.onmousemove = debounce(function (e) {
    box.innerHTML = `${e.clientX}, ${e.clientY}`
}, 1000);
```

 防抖常应用于用户进行搜索输入节约请求资源，`window`触发`resize`事件时进行防抖只触发一次。 

###  throttle（节流）

 高频时间触发,但n秒内只会执行一次,所以节流会稀释函数的执行频率。 

```js
const throttle = (fn, time) => {
    let flag = true; // 闭包的妙用
    return function() {
        if (!flag) return;
        flag = false;
        setTimeout(() => {
            fn.apply(this, arguments);
            flag = true;
        }, time);
    }
};
```

 使用：

```js
box.onmousemove = throttle(function (e) {
    box.innerHTML = `${e.clientX}, ${e.clientY}`
}, 1000);
```



节流常应用于鼠标不断点击触发、监听滚动事件。 

### 区别

1. 都是持续触发不执行。防抖是只会执行最后一次的事件。节流是n秒时间一到，就会立马执行当前的时间。 

### 参考文献

> [函数的防抖和节流是个啥](https://zhuanlan.zhihu.com/p/72923073 )   