# Quenterfiers

量词：表示匹配的字符或表达式的数量。

```js

//eg:

// x* 匹配前一项x 0或更多次
console.log(('chrisfang').match(/ch*/g)) //[ 'ch' ]
console.log(('chrisfangcc').match(/ch*/g)) //[ 'ch', 'c', 'c' ]

// x+ 匹配前一项x 1次或多次, 等效于{1，}。
console.log(('chrisfang').match(/c+/g)) //[ 'c' ]
console.log(('chrisfangcc').match(/c+/g)) //[ 'c', 'cc' ]

//x?  匹配前一项x 0或1次
console.log(('chrisfang').match(/c?hr?/g)) //[ 'chr' ]
console.log(('chrisfanghh').match(/c?hr?/g)) //[ 'chr', 'h', 'h' ]

//x{n} n为正整数，精确的匹配前一项x n次出现。
console.log(('chrisfangcc').match(/c{2}/g)) // [ 'cc' ]

// x{n,} n为正整数，精确的匹配前一项x n次及n次以上。
console.log(('chrisfangcc').match(/c{3,}/g)) // null
console.log(('chrisfangcccc').match(/c{3,}/g)) // [ 'cccc' ]

//x{n,m} 其中n为0或正整数，m为正整数，m> n。至少匹配n个和最多m个先前项x。
console.log(('chrisfangcc').match(/c{1,3}/g)) // [ 'c', 'cc' ]
console.log(('chrisfangcccc').match(/c{1,4}/g)) //[ 'c', 'cccc' ]

// 在任何量词*，+ 、?或{}之后立即使用，则使量词为非贪婪的（匹配最小次数），而不是默认的贪婪的（匹配最大次数） 。
console.log(('chhhhrisfangchhhhrchhhhr').match(/c.*r/g)) // [ 'chhhhrisfangchhhhrchhhhr' ]
console.log(('chhhhrisfangchhhhrchhhhr').match(/c.*?r/g)) // [ 'chhhhr', 'chhhhr', 'chhhhr' ]

console.log(('chhhhrisfangchhhhrchhhhr').match(/c.{1,}r/g)) // [ 'chhhhrisfangchhhhrchhhhr' ]
console.log(('chhhhrisfangchhhhrchhhhr').match(/c.{1,}?r/g)) // [ 'chhhhr', 'chhhhr', 'chhhhr' ]

console.log(('chhhhrisfangchhhhrchhhhr').match(/c.?h/g)) // [ 'chh', 'chh', 'chh' ]
console.log(('chhhhrisfangchhhhrchhhhr').match(/c.??h/g)) // [ 'ch', 'ch', 'ch' ]

```



