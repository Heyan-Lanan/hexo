---
title: Echarts科学绘图-条形图
date: 2022-3-21 10:00:00
comment: 'waline'
index_img: /img/index.jpg
categories: Echarts
tags: Echarts
---

&nbsp;&nbsp;&nbsp;&nbsp;先看一个入门的示例，先引入echarts.js文件，可以下载到本地也可以从jsdelivr引入，为图表准备一个容器，然后基于这个容器添加图表，这里我定义的是myChart，然后新建option变量来配置图表，最后使用刚指定的配置项和数据显示图表，这样第一个图表就绘制完成啦！可以设置一些参数包括标题，图例，x轴数据，y轴数据，图表的类型。


<p class="note note-primary">后续文章均只展示option，我会给出详细的注释</p>


```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <title>ECharts</title>
    <!-- 引入刚刚下载的 ECharts 文件 -->
    <script src="https://cdn.jsdelivr.net/npm/echarts@5.3.1/dist/echarts.js"></script>
</head>
<body>
<!-- 为 ECharts 准备一个定义了宽高的 DOM -->
<div id="main" style="width: 600px;height:400px;"></div>
<script type="text/javascript">
    // 基于准备好的dom，初始化echarts实例
    const myChart = echarts.init(document.getElementById('main'));
    // 指定图表的配置项和数据
    const option = {
        title: {
            text: 'ECharts 入门示例'  //标题
        },
        tooltip: {},
        legend: {
            data: ['销量']  //图例
        },
        xAxis: {
            data: ['衬衫', '羊毛衫', '雪纺衫', '裤子', '高跟鞋', '袜子']  //x轴数据是类目型的
        },
        yAxis: {},
        series: [
            {
                name: '销量',  //和前面的图例名字保持一致
                type: 'bar',  //条形图bar chart
                data: [5, 20, 36, 10, 10, 20]  //y轴数据
            }
        ]
    };
    // 使用刚指定的配置项和数据显示图表。
    myChart.setOption(option);
</script>
</body>
</html>
```

<script src="https://cdn.jsdelivr.net/npm/echarts@4.8.0/dist/echarts.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/echarts-gl@1.1.1/dist/echarts-gl.min.js"></script>
{% echarts 400 '100%' %}
const option = {
    xAxis: {
        data: ['A', 'B', 'C', 'D', 'E']
    },
    yAxis: {},
    series: [
        {
            type: 'bar',
            data: [10, 22, 28, 43, 49],
            barWidth: '50%',  //柱条宽度
            barMinHeight: '20',  //柱条最小高度
            showBackground: true,  //背景颜色
            backgroundStyle: {
                color: 'rgba(213,124,124,0.8)'
            }
        }
    ]
};
{% endecharts %}