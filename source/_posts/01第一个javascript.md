---
title: 测试JavaScript
date: 2019-10-10 10:00:00
comment: 'waline'
index_img: /img/index.jpg
---


## JavaScript 32-4 笔记

```html
<script>
    window.onload = function () {
        var oDiv = document.getElementById("div1");
        oDiv.style.color = "red";
    }
</script>
<div id="div1">绿叶学习网</div>
```

通过`document.getElementById("div1")`为html中的`div`注入样式。

```html
<script>
    window.onload = function () {
        var oUl = document.getElementById("list");
        var oLi = oUl.getElementsByTagName("li");
        oLi[2].style.color = "red";
    }
</script>

<ul id="list">
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
    <li>jQuery</li>
    <li>Vue.js</li>
</ul>
```

通过`document.getElementById("list")`获取`ul`，再通过`getElementsByTagName("li")`获取标签`li`元素列表，`oLi[2].style.color`即可
选择第二个`li`标签。

```html
<script>
    window.onload = function () {
        var arr = ["HTML", "CSS", "JavaScript", "jQuery", "Vue.js"];
        var oUl = document.getElementById("list");
        var oLi = document.getElementsByTagName("li");

        for (var i = 0; i < oLi.length; i++) {
            oLi[i].innerHTML = arr[i];
            oLi[i].style.color = "red";
        }
    }
</script>

<ul id="list">
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
</ul>
```

`oLi[i].innerHTML`即可为标签注入html代码

```html
<script>
    window.onload = function () {
        document.body.innerHTML = "<input type='button' value='按钮'/><input type='button' value='按钮'/><input type='button' value='按钮'/>"
        var oBtn = document.getElementsByTagName("input");

        oBtn[0].onclick = function () {
            alert("表单元素共有：" + oBtn.length + "个");
        };
    }
</script>
```

   `oBtn[0].onclick`是点击后触发，`alert`是简单的浏览器弹窗，`oBtn.length`是元素个数

```html
<script>
    window.onload = function () {
        document.body.innerHTML = "<input id='btn' type='button' value='按钮'/><input type='button' value='按钮'/><input type='button' value='按钮'/>"
        var oBtn = document.getElementById("btn");

        oBtn.onclick = function () {
            alert("表单元素共有：" + oBtn.length + "个");
        };
    }
</script>
```

也可以通过`document.getElementById`来获取单个按钮。

```html
<script>
    window.onload = function () {
        var oLi = document.getElementsByClassName("select");
        oLi[0].style.color = "red";
    }
</script>
<ul id="list">
    <li>HTML</li>
    <li>CSS</li>
    <li class="select">JavaScript</li>
    <li class="select">jQuery</li>
    <li class="select">Vue.js</li>
</ul>
```
利用`document.getElementsByClassName`获取特定ClassName的元素

```html
<script>
    window.onload = function () {
        var oDiv = document.querySelectorAll(".test");
        oDiv[1].style.color = "red";
    }
</script>
<div>绿叶学习网</div>
<div class="test">绿叶学习网</div>
<div class="test">绿叶学习网</div>
<div>绿叶学习网</div>
<div class="test">绿叶学习网</div>
```
也可以使用`document.querySelectorAll`获取特定ClassName的元素

```html
<script>
    window.onload = function () {
        var oLi = document.querySelector("#list li:nth-child(3)");
        oLi.style.color = "red";
    }
</script>
<ul id="list">
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
    <li>jQuery</li>
    <li>Vue.js</li>
</ul>
```
`document.querySelector`获取`id="list"`中第三个`li`

```html
<script>
    window.onload = function () {
        var oInput = document.getElementsByName("status");
        oInput[2].checked = true;
    }
</script>
你的最高学历:
<label><input type="radio" name="status" value="本科" />本科</label>
<label><input type="radio" name="status" value="硕士" />硕士</label>
<label><input type="radio" name="status" value="博士" />博士</label>
```
`document.getElementsByName`获取普通的`name="status"`元素，`oInput[2].checked`将第二个元素打勾

```html
<script>
    window.onload = function () {
        document.title = "绿叶学习网";
        document.body.innerHTML = "<strong style='color:#cd8d8d'>欢迎来到绿叶学习网</strong>";
    }
</script>
```
`document.title`和`document.body.innerHTML`可以设置html的标题和内容

