# Boundaries

边界指示行和单词的开头和结尾。

```js

// eg:

// ^ 匹配输入的开始。 如果多行标志设置为true，则也将在换行符后立即匹配。
let str = `chris cang`
console.log(('chrisfang').match(/^c/)) // c
console.log(('chrisfang').match(/^h/)) // null
console.log(str.match(/^c/gm)) // ['c']

// $ 匹配输入结束。
console.log(('chrisfang').match(/\w+g$/)) // chrisfang
console.log(('chrisfang').match(/\w+n$/)) // null

// \b 匹配单词边界。 这是一个单词字符后面没有或由另一字字符的前面，例如字母和一个空间之间的位置。 请注意，匹配的单词边界不包括在匹配中。换句话说，匹配的单词边界的长度为零。
// 区分退格符 (('chris' + '\b' + 'fang').match(/[\b]/) //b)
console.log(('c hrisfang').match(/\bh\w+/)) // hrisfang
console.log(('chrisfang').match(/\bh\w+/)) // null

// \B匹配非单词边界。  与\b相反
console.log(('c hrisfang').match(/\Bh\w+/)) // null
console.log(('chrisfang').match(/\Bh\w+/)) // hrisfang



```



