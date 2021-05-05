实现一个字符串匹配算法,从长度为n的字符串S中,查找是否存在字符串T,T的长度是m,若存在返回所在位置。

```js
const find = (S, T) => {
    if (S.length < T.length) return -1;
    for (let i = 0; i < S.length; i++) {
        if (S.slice(i, i + T.length) === T) return i;
    }
    return -1;
}
```