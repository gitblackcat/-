做项目时候,无意中遇到的一件事情:

```
f($f)
    font-size $f
    [data-dpr="2"] &
        font-size $f*2
    [data-dpr="3"] &
        font-size $f*3

div
    f(15px) !important
```

编译出来是以下,并没有带`!important`

```
div {
  font-size: 15px;
}
[data-dpr="2"] div {
  font-size: 30px;
}
[data-dpr="3"] div {
  font-size: 45px;
}
```

正确做法

```
f($f,imp = )
    font-size $f imp
    [data-dpr="2"] &
        font-size $f*2 imp
    [data-dpr="3"] &
        font-size $f*3 imp

div
    f(15px,!important)
```

编译出来就是正常的

```
div {
  font-size: 15px !important;
}
[data-dpr="2"] div {
  font-size: 30px !important;
}
[data-dpr="3"] div {
  font-size: 45px !important;
}
```