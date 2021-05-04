// var arr=[1,2,3,[4,5],[6,[7,[8]]]]

使用递归的方式处理。wrap 内保存结果ret，返回一个递归函数
```js
function wrap() {
    const ret = [];
    return function flat(a) {
        for (var item of a) {
            if (item.constructor === Array) {
                ret.concat(flat(item));
            } else {
                ret.push(item);
            }
        }
        return ret;
    }
};
console.log(wrap()(arr));
```