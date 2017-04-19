在`<td>`中的水平垂直居中是非常简单的,并没有想象中那么难.切忌上来就是给`<td>`一个相对定位,然后给`<td>`中的元素一个绝对定位,如

```
td{
    position: relative;
}
td > div{
    position: absolute;
    top: 50%;
    left: 50%;
    margin-left: -30px;
    margin-top: -20px;
    width: 60px;
    height: 40px;
}
```

这样显得非常的繁琐

**_然后最重要的是,这样在非IE浏览器中支持,在IE浏览器中一律垂直方向不能居中_**

- 方法一进行垂直水平居中

在`<table>`中自带`align`的特性,可以给子元素,不管是块级子元素还是内联子元素都能垂直水平居中.如下: 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        body,html,table,td,tr,p{
            padding: 0;
            margin: 0;
        }
        table{
            width: 100%;
            margin: 100px auto;
            border: 1px solid #000;
            border-right: none;
            border-bottom: none;
            border-spacing: 0;
        }
        td{
            border: 1px solid #000;
            border-left: none;
            border-top: none;
        }
        .test{
            position: relative;
            background-color: green;
        }
        .aa{
            background-color: red;
            width: 180px;
        }
    </style>
</head>
<body>
    <table>
        <tr>
            <td width="200px;">
                <p>123123</p>
                <p>123123</p>
                <p>123123</p>
                <p>123123</p>
                <p>123123</p>
                <p>123123</p>
            </td>
            <td class="test" align="center">
                <div class="aa">
                    <p>123</p>
                    <p>123</p>
                    <p>123</p>
                </div>
                <!-- <span class="aa">aaa</span> -->
            </td>
        </tr>
    </table>
</body>
</html>
```

但并不推荐该方法,一方面是在 HTML 4.01 中,`<table>`元素的`align`和`bgcolor` 属性是不被赞成使用的.在 XHTML 1.0 Strict DTD,`<table>`元素的`align`和`bgcolor`属性是不被支持的.另一方面是会让`<td>`的子元素的后代元素都继承居中,很麻烦

- 方法二进行垂直水平居中

仔细研究`<table>`会发现,其实`<td>`是自带垂直居中效果的,所以对于`<td>`中子元素是块级子元素的,直接使用`margin: auto;`就ok了;对于`<td>`中子元素是内联子元素的,就在`<td>`中使用`text-align: center;`以及在该内联子元素中添加`vertical-align: middle;`就好
