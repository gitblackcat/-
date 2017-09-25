谷歌浏览器input自动填充内容,背景色会是黄色,想改的话:

```
input:-webkit-autofill {
  -webkit-box-shadow: 0 0 0px 1000px white inset;
  -webkit-text-fill-color: #333;
}
```

`autocomplete="off"`