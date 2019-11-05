# Charachter Classes

字符类别区分字符的种类，例如区分字母和数字。

```js


// /指示以下字符应被特殊对待或“转义”
console.log('chrisfang.'.match(/\./)) //.
console.log('chrisfang.'.match(/./g)) // [ 'c', 'h', 'r', 'i', 's', 'f', 'a', 'n', 'g', '.' ]

// . 匹配一切字符 在字符集内与文字.匹配
console.log('chrisfang.'.match(/\./)) //.

// \d 匹配数字 
console.log('chris22fang'.match(/\d/)) //2

// \D 匹配非数字
console.log('chris22fang'.match(/\D/)) //c

// \w 匹配基本拉丁字母中的任何字母数字字符，包括下划线。等效于[A-Za-z0-9_]。
console.log('克鲁斯2_'.match(/\w/)) //2

// \W 匹配基本拉丁字母中不是单词字符的任何字符。等效于[^ A-Za-z0-9_]
console.log('克鲁斯2_'.match(/\W/)) //克

// \s 匹配单个空格字符，包括空格，制表符，换页符，换行符和其他Unicode空格。  基本等于[\ f \ n \ r \ t \ v \ u00a0 \ u1680 \ u2000- \ u200a \ u2028 \ u2029 \ u202f \ u205f \ u3000 \ ufeff]
console.log(('chris ' + '\n' + '\r' + '\f' + '\t').match(/\s/g)) // [ ' ', '\n', '\r', '\f', '\t' ]

// \S 匹配非空格符，等效于[^ \ f \ n \ r \ t \ v \ u00a0 \ u1680 \ u2000- \ u200a \ u2028 \ u2029 \ u202f \ u205f \ u3000 \ ufeff]
console.log(('chris ' + '\n' + '\r' + '\f' + '\t').match(/\S/g)) // [ 'c', 'h', 'r', 'i', 's' ]

// \t 匹配水平制表符。
console.log(('chris' + '\t' + 'fang').match(/\t/)) //t

// \r 匹配回车符
console.log(('chris' + '\r' + 'fang').match(/\r/)) //r

// \n 匹配换行符
console.log(('chris' + '\n' + 'fang').match(/\n/)) //n

// \f 匹配换页符
console.log(('chris' + '\f' + 'fang').match(/\f/)) //f

// \b 匹配退格符
console.log(('chris' + '\b' + 'fang').match(/[\b]/)) //b

// \0匹配一个NUL字符。不要在此后面加上其他数字。
console.log(('chris' + '\0' + 'fang').match(/\0/)) //'\u0000'

// \cX 使用插入号表示法匹配控制字符 其中X是A–Z的字母(小写也支持)（对应于代码点U + 0001–U + 001F）
let str = ''; // 用于存放 \x00-\xff 这256个字符
for (var i = 0; i <= 255; i++) {
    str += String.fromCharCode(i); // 填充字符
}
console.log(str.match(/\cA/)); //\u0001

// xhh将字符与代码hh（两个十六进制数字）匹配。 HH对应该字符的 Unicode 码点
console.log(str.match(/\x0c/)) // /f

// uhhhh 将UTF-16代码单元与值hhhh（四个十六进制数字）匹配。
console.log(str.match(/\u0008/)) //b

```



