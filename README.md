# Assertions

断言（assertions）表明以某种方式会存在匹配，包括先行断言\(look-ahead\)、后行断言（look-behind）、以及条件表达式（conditional expressions）

```js

// eg:

// x(?=y) 先行断言: y紧跟x的情况下匹配x 但是匹配结果只有X
console.log(('chrisfang').match(/\w+(?=fang)/)) // chris
console.log(('chrisfang').match(/chris(?=fang1)/)) // null

// x(?!y) 负向先行断言: x后无y紧随的情况下匹配x。
console.log(('chrisfang').match(/\w{5}(?!fang)/)) // hrisf // 很有意思,断言后,特殊字符匹配不会按照默认开始
console.log(('chrisfang').match(/chris(?!fang)/)) // null

// (?<=y)x 后行断言: x紧随y的情况下匹配x。
console.log(('chrisfang').match(/(?<=chris1)\w+/)) // null
console.log(('chrisfang').match(/(?<=chris)fang/)) // fang

// (?<!y)x 负向后行断言: x不紧随y的情况下匹配x.
console.log(('chrisfang').match(/(?<!chris)\w{5}/)) // chris // 很有意思,断言后,特殊字符匹配不会按照默认开始
console.log(('chrisfang').match(/(?<!chris)fang/)) // null

```







