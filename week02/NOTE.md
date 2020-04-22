# 每周总结可以写在这里
# Javascript

## atom


[Unicode](https://www.fileformat.info/info/unicode/)
[中文字符](https://www.fileformat.info/info/unicode/block/cjk_unified_ideographs/index.htm)

可用 `String.fromCharCode(num)` `'\t'.codePointAt()` 进行打印

* javascript 如何处理 emoji 字符
* 为什么不要用中文做变量名, 如何更安全使用中文作为变量名
* "厉".codePointAt(0).toString(16)

* inputElement
  * WhiteSpace: `\v`, `\t`, `nbsp` 无分词效果空格(`/u00A0`), zwnbsp-零宽nbsp
  * LineTerminator
  * Comment
  * Token: 一切有效的东西
    * Punctuator: 符号, 用于构成代码结构
    * IdentifierName: 标识符
      * 变量名: 不可与关键字重合, 特例: `get`, `undefined` 全局不可改变量名
      * 属性名: 可与关键字重合
    * Literal: 直接量
      * NumericLiteral
      * StringLiteral
    * Template

* Type
  * Number: IEEE 754 Double Float
    * 浮点数比较: Math.abs(0.1 + 0.2 - 0.3) < Number.EPSILON
    * `97 .toString(2)`
  * String
    * USC: U+0000 ~ U+FFFF, unicode 的 BMP 范围
    * GB: 国标
    * 存储方式: UTF8/UTF16
      * UTF8 使用 8 位存储
      * UTF16 使用 18 位存储
    * 引号内的特殊字符 `\'"bfnrtv`
  * Boolean
  * Null
  * Undifined
  * Symbol

正则表达式： https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Regular_Expressions
揭秘 0.1 + 0.2 != 0.3 https://www.barretlee.com/blog/2016/09/28/ieee754-operation-in-js/
ASCII，Unicode 和 UTF-8 ： http://www.ruanyifeng.com/blog/2007/10/ascii_unicode_and_utf-8.html