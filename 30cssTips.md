# 30个常用css选择符<sup>[出处](https://yanhaijing.com/css/2014/01/04/the-30-css-selectors-you-must-memorize/)</sup>

本笔记中记录的大部分选择器属于CSS3规范中的一部分, 因此只有在现代浏览器中才可以使用.

### 1.*

星号选择器将匹配页面中的所有元素, 大部分开发者使用这个技巧将外边距和内边距重置为零.

``` css
* {
    margin: 0;
    padding: 0;
}
```

'*'也能作为子选择器符使用,但是不建议用在生产环境中,它会给浏览器带来大量不必要的负担.

```css
#container * {
    border: 1px solid #000;
}
```

[查看例子](https://cdn.tutsplus.com/net/uploads/legacy/840_cssSelectors/selectors/star.html)

**兼容性**

* IE6+
* Firefox
* Chrome
* Safari
* Opera


### 2.#x

id选择符是唯一的,不允许重复

```css
#container {
    width: 960px;
    margin: auto;
}
```

[查看例子](https://cdn.tutsplus.com/net/uploads/legacy/840_cssSelectors/selectors/id.html)

**兼容性**

* IE6+
* Firefox
* Chrome
* Safari
* Opera


### 3. .x

类选择符可以多次使用,当你想给一组元素应用样式的时候可以使用类选择符.另外,特殊元素应用样式的时候才使用id

```css
.error {
    color: red
}
```

[查看例子](https://cdn.tutsplus.com/net/uploads/legacy/840_cssSelectors/selectors/class.html)

**兼容性**

* IE6+
* Firefox
* Chrome
* Safari
* Opera


### X Y

后代选择符选择其元素的所有子/孙元素

```css
li a {
    text-decoration: underline;
}
```

[查看例子](https://cdn.tutsplus.com/net/uploads/legacy/840_cssSelectors/selectors/descend.html)

**兼容性**

* IE6+
* Firefox
* Chrome
* Safari
* Opera


### 5. X

类型选择符直接选择元素

```css
a { color: red; }
ul { margin-left: 0; }
```

[查看例子](https://cdn.tutsplus.com/net/uploads/legacy/840_cssSelectors/selectors/tagName.html)

**兼容性**

* IE6+
* Firefox
* Chrome
* Safari
* Opera


### 6. X:visited and X:link

`:link `伪类选择符选择所有已经被点击过的锚标签
`:visited`伪类选择符选择被点击过的或被访问过的锚标签

```css
a:link { color: red; }
a:visited { color: purple; }
```

[查看例子](https://cdn.tutsplus.com/net/uploads/legacy/840_cssSelectors/selectors/links.html)

**兼容性**

* IE7+
* Firefox
* Chrome
* Safari
* Opera

### 7. X + Y

相邻选择符选择只紧贴在X元素之后的Y元素

```css
ul + p {
    color: red;
}
```

[查看例子](https://cdn.tutsplus.com/net/uploads/legacy/840_cssSelectors/selectors/adjacent.html)

**兼容性**

* IE7+
* Firefox
* Chrome
* Safari
* Opera


### 8. X > Y

直接后代选择符只选择直系子级元素

```css
div#container > ul {
    border: 1px solid #000;
}
```
```html
<div id="container">
    <ul>
        <li>list Item
            <ul>
                <li>child</li>
            </ul>
        </li>
        <li>list Item</li>
        <li>list Item</li>
        <li>list Item</li>
    </ul>
</div>
```

[查看例子](https://cdn.tutsplus.com/net/uploads/legacy/840_cssSelectors/selectors/childcombinator.html)

**兼容性**

* IE7+
* Firefox
* Chrome
* Safari
* Opera

### 9. X ~ Y

兄弟选择符与`X + Y`一样,但是它没有约束, 它选择`X`后面的所有`Y`元素

```css
ul ~ p {
    color: red;
}
```

[查看例子](https://cdn.tutsplus.com/net/uploads/legacy/840_cssSelectors/selectors/generalcombinator.html)

**兼容性**

* IE7+
* Firefox
* Chrome
* Safari
* Opera

### 10. X[attr]

属性选择器只选择`attr`属性的标签

```css
a[title] {
    color: green;
}
```
[查看例子](https://cdn.tutsplus.com/net/uploads/legacy/840_cssSelectors/selectors/attributes.html)

**兼容性**

* IE7+
* Firefox
* Chrome
* Safari
* Opera

### 11. X[href="xxx"]

链接选择符选择所以`href`属性为`xxx`的`X`元素

> 注意我们将href值用引号包裹.记住,当使用JavaScript的css选择符引擎时也这么做.如果可能的话,尽可能使用css3选择符代替非官方的方法

```css
a[href="http://net.tutsplus.com"] {
    color: #1f6053;
}
```

[查看例子](https://cdn.tutsplus.com/net/uploads/legacy/840_cssSelectors/selectors/attributes2.html)

**兼容性**

* IE7+
* Firefox
* Chrome
* Safari
* Opera

### 12. X[href*="xxx"]

`*`号指定了包含该属性的值必须包含定义的值. 也就是说选择了href值为`xxx.com`, `net.xxx.com`或者`aaaxxx.com`

> 由于这个描述过于宽泛,所以需要更多特性来限制,分别使用 `^` 和 `&` 来限定字符串的开始和约束

```css
a[href*="tuts"] {
    color: #1f6053;
}
```

[查看例子](https://cdn.tutsplus.com/net/uploads/legacy/840_cssSelectors/selectors/attributes3.html)

**兼容性**

* IE7+
* Firefox
* Chrome
* Safari
* Opera

### 13. X[href^="http"]

`^(carat)`符表示字符串的开始,正则表达式符号

```css
a[href^="http"] {
   background: url(path/to/external/icon.png) no-repeat;
   padding-left: 10px;
}
```

[查看例子](https://cdn.tutsplus.com/net/uploads/legacy/840_cssSelectors/selectors/attributes4.html)

**兼容性**

* IE7+
* Firefox
* Chrome
* Safari
* Opera

### 14. X[href$=”.jpg”]

`$(dolor)`符表示字符串的结束,正则表达式符号

```css
a[href$=".jpg"] {
   color: red;
}
```

[查看例子](https://cdn.tutsplus.com/net/uploads/legacy/840_cssSelectors/selectors/attributes5.html)

**兼容性**

* IE7+
* Firefox
* Chrome
* Safari
* Opera

### 15. X[data-*="xxx"]

获取自定义属性的元素

```css
a[data-filetype="image"] {
   color: red;
}
```

```html
<a href="path/to/image.jpg" data-filetype="image"> Image Link </a>
```

[查看例子](https://cdn.tutsplus.com/net/uploads/legacy/840_cssSelectors/selectors/attributes6.html)

**兼容性**

* IE7+
* Firefox
* Chrome
* Safari
* Opera

### 16. X[foo~="bar"]

~(tilda)符

### 17. X:checked

```css
/* no sample yet */
```

### 18. X:after

```css
/* no sample yet */
```

### 19. X:hover

```css
/* no sample yet */
```

### 20. X:not(selector)

```css
/* no sample yet */
```

### 21. X::pseudoElement

```css
/* no sample yet */
```

### 22. X:nth-child(n)

```css
/* no sample yet */
```

### 23. X:nth-last-child(n)

```css
/* no sample yet */
```

### 24. X:nth-of-type(n)

```css
/* no sample yet */
```

### 25. X:nth-last-of-type(n)

```css
/* no sample yet */
```

### 26. X:first-child

```css
/* no sample yet */
```

### 27. X:last-child

```css
/* no sample yet */
```

### 28. X:only-child

```css
/* no sample yet */
```

### 29. X:only-of-type

```css
/* no sample yet */
```

### 30. X:first-of-type

```css
/* no sample yet */
```