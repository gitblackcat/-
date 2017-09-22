### return false不跳转
```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>

<body>
    <div>
        <a href="http://www.baidu.com">baidu</a>
    </div>
    <script>
    document.querySelector('div').onclick = function(event) {
        return false
    }
    </script>
</body>

</html>
```

在`div`上面`return false`的时候`a`链接也不会跳转,这是为什么?

可能是DOM0级方法导致该问题的出现

解决方法就是用`event.stopPropagation()`具体的禁止冒泡来替代`return false`

#### 参考
[https://segmentfault.com/q/1010000011306726?_ea=2589968](https://segmentfault.com/q/1010000011306726?_ea=2589968)