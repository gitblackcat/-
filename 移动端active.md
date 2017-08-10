`:active`伪类是在类似'mousedown'事件触发的时机生效的,Android 可以触发 mousedown ，IOS却不可以

加上以下代码,就可以正常使用`:active`了

```html
<body ontouchstart="" onmouseover="">
</body>
```

参考

[https://stackoverflow.com/questions/8330559/hover-effects-using-css3-touch-events](https://stackoverflow.com/questions/8330559/hover-effects-using-css3-touch-events)

