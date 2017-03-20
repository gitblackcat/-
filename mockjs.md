mock.js只要引入文件,写好假数据就能用,在jquery中,没有固定套路格式

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
    <script src="http://mockjs.com/dist/mock.js"></script>
    <script>
        Mock.mock('http://g.cn', {
            'name'     : '@name',
            'age|1-100': 100,
            'color'    : '@color'
        })

        //jquery可以这么写
        $.ajax({
            url: 'http://g.cn',
            dataType:'json'
        }).done(function(data, status, xhr){
            console.log( JSON.stringify(data, null, 4) )    
        })

        //也可以这么写
        $.ajax({
            type: "get",
            url: "http://g.cn",
            async: false,
            dataType: "json",
            success: function(data){
                //console.log( data )
            }
        })
    </script>
</body>
</html>
```

[http://mockjs.com/](http://mockjs.com/)

[https://segmentfault.com/a/1190000003087224](https://segmentfault.com/a/1190000003087224)