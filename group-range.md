# Group Range

组和范围表示表达字符的组和范围。

```js

// x|y 匹配x或y
console.log(('chrisfang212').match(/\w|\d/ig)) //[ 'c', 'h', 'r', 'i', 's', 'f', 'a', 'n', 'g', '2', '1', '2' ]

// [xyz] [x-z] 字符集, 表示匹配任何一个封闭的字符
console.log(('chrisfang212').match(/[abcdefg]/ig)) // [ 'c', 'f', 'a', 'g' ]
console.log(('chrisfang212').match(/[a-g]/ig))  // [ 'c', 'f', 'a', 'g' ]

// [^xyz] [^x-z] 否定字符集, 表示匹配不在范围的任何一个封闭的字符
console.log(('chrisfang212').match(/[^abcdefg]/ig)) // [ 'h', 'r', 'i', 's', 'n', '2', '1', '2' ]
console.log(('chrisfang212').match(/[^a-g]/ig))  // [ 'h', 'r', 'i', 's', 'n', '2', '1', '2' ]

// (x) 匹配x，并且记住x
console.log(('chrisfang212').replace(/\w+(fang212)/, 'qiang$1')) //qiangfang212

// \n (n是一个正整数) \n代表着第几个括号所捕获的值 而非 表达式
console.log(('chrisfang212').match(/(\d)\1/)) // null
console.log(('chrisfang222').match(/(\d)\1/)) // 22

// (?<Name>x) 匹配x并将其以<Name>指定的名称存储在返回的匹配项的groups属性中。组名必须使用尖括号（“ <”和“>”）
console.log(('chrisfang222').match(/(?<hello>\d)/).groups.hello)  //2

// (?:x) 非捕获组：匹配x但不记得匹配项。
console.log(('chrisfang222').match(/(?:\d)/)) // 2
console.log(('chrisfang222').match(/(?:\d)\1/)) // null

```



