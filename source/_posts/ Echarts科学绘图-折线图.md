---
title: Echarts科学绘图-折线图
date: 2022-3-22 10:00:00
comment: 'waline'
index_img: /img/index.jpg
categories: Echarts
tags: Echarts
---

<script src="https://cdn.jsdelivr.net/npm/echarts@4.8.0/dist/echarts.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/echarts-gl@1.1.1/dist/echarts-gl.min.js"></script>

&nbsp;&nbsp;&nbsp;&nbsp;设置type: 'line' 来绘制折线图，横坐标是类目型(category)，纵坐标是数值型(value)，因为横坐标和纵坐标都是默认的类型，所以这里 xAxis 和 yAxis 的 type 属性都可以隐去不写，用'-'来表示空数据。

```js
option = {  //这里 xAxis 和 yAxis 的 type 属性都可以隐去不写
    xAxis: {
        type: 'category',  //横坐标是类目型（category）
        data: ['A', 'B', 'C', 'D', 'E', 'F']
    },
    yAxis: {
        type: 'value'  //纵坐标是数值型（value）
    },
    series: [
        {
            data: [120, 200, 150, 400, '-', 280],  //空数据
            type: 'line'  //折线图
        }
    ]
};
```

{% echarts 400 '100%' %}
option = {  //这里 xAxis 和 yAxis 的 type 属性都可以隐去不写
    xAxis: {
        type: 'category',  //横坐标是类目型（category）
        data: ['A', 'B', 'C', 'D', 'E', 'F']
    },
    yAxis: {
        type: 'value'  //纵坐标是数值型（value）
    },
    series: [
        {
            data: [120, 200, 150, 400, '-', 280],  //空数据
            type: 'line'  //折线图
        }
    ]
};
{% endecharts %}

&nbsp;&nbsp;&nbsp;&nbsp;用数组表示来实现笛卡尔坐标系中的折线图，折线的顺序也是按照数组顺序排布的。用label来显示数据点的数值，用emphasis.label来设置鼠标放上去的时候显示数值。

```js
option = {
    xAxis: {},
    yAxis: {},
    series: [
        {
            data: [
                [20, 120],  //用数组表示就可以实现笛卡尔坐标系中的折线图
                [50, 200],
                [40, 50]
            ],
            type: 'line',
            label: {   //默认显示数据点的数值
                show: true,
                position: 'bottom',  //数值的位置
                textStyle: {
                    fontSize: 10  //数值大小
                }
            },
            emphasis: {
                label: {  //鼠标放上去的时候显示数值
                    show: true,
                    position: "top",  //数值的位置
                    textStyle: {
                        fontSize: 20  //数值大小
                    }
                }
            }
        }
    ]
};
```

{% echarts 400 '100%' %}
option = {
    xAxis: {},
    yAxis: {},
    series: [
        {
            data: [
                [20, 120],  //用数组表示就可以实现笛卡尔坐标系中的折线图
                [50, 200],
                [40, 50]
            ],
            type: 'line',
            label: {   //默认显示数据点的数值
                show: true,
                position: 'bottom',  //数值的位置
                textStyle: {
                    fontSize: 10  //数值大小
                }
            },
            emphasis: {
                label: {  //鼠标放上去的时候显示数值
                    show: true,
                    position: "top",  //数值的位置
                    textStyle: {
                        fontSize: 20  //数值大小
                    }
                }
            }
        }
    ]
};
{% endecharts %}
