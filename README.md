# 前端：网页定位导航

分别用 jQuery 与 JavaScript 完成了屏幕滚动楼层导航的效果。

## 1. jQuery 部分主要方法与属性

* DOM 加载完成以后开始
```
$(document).ready(function(){})
```

* 捕获屏幕滚动事件
`scroll(function(){})`

* 屏幕从顶部滚动距离
`scrollTop`

* 获取对象的距离屏幕的偏移量
`offset()`：获取数据，分别是top和left两个属性
`offset().top`：获取从顶部到对象的偏移量
`offset().left`：获取从左边到jQury对象的偏移量

## 2. JavaScript 部分主要方法与属性
 
* DOM 加载完成开始
```
window.onload = function(){}
```

* 屏幕滚动事件
```
window.onscroll = function(){}
```

* 获取屏幕滚动距离，需要考虑兼容性
```
var top = document.documentElement ? document.documentElement.scrollTop : document.body.scrollTop;
```

* 关于 getElementsByClassName 的兼容性
不考虑兼容性，可以使用：
```
var items = document.getElementById('content').getElementsByClassName('item');
```

考虑兼容性则使用：
```
function.getByClassName(obj, cls){
    var elements = obj.getElementsByTagName("*"); // 获取所有DOM元素
    var result = [];
    for (var i=0; i < elements.length; i++){
        if (elements[i].className == cls) {
            result.push(elements[i]);
        }
    }
    return result;
}
var items = getByClassName(document.getElementById("content"), "item")
```


