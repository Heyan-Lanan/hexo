---
title: Plotly动态可视化绘图-散点图
math: true
date: 2022-3-23 22:57:00
comment: 'waline'
mermaid: true
index_img: /img/index.jpg
categories: Python
tags: Plotly
---

可以设置三种模式，分别是<p class="note note-primary">mode='markers',#xtr1,散点图</p><p class="note note-primary">mode='lines',#xtr2,线形图</p><p class="note note-primary">mode='lines+markers',#xtr3,线形图+散点图组合</p>

```python
import plotly as py
import plotly.graph_objs as go
import numpy as np  # 产生随机数
pyplt = py.offline.plot  # 预定义

N = 100
random_x = np.linspace(0, 1, N)  # 生成 0-1 100个数字的均匀序列
random_y0 = np.random.randn(N) + 5  # 生成N个随机数序列
random_y1 = np.random.randn(N)
random_y2 = np.random.randn(N) - 5

# Create traces
trace0 = go.Scatter(
    x=random_x,
    y=random_y0,
    mode='markers',  # 纯散点的绘图
    name='markers'  # 曲线名称
)
trace1 = go.Scatter(
    x=random_x,
    y=random_y1,
    mode='lines+markers',  # 散点+线的绘图
    name='lines+markers'
)
trace2 = go.Scatter(
    x=random_x,
    y=random_y2,
    mode='lines',  # 线的绘图
    name='lines'
)

data = [trace0, trace1, trace2]
pyplt(data, filename='tmp/scatter_basic_demo.html')
```
<div align="center"><iframe width="800" height="600" frameborder="0" scrolling="no" src="//plotly.com/~ningyu/5.embed"></iframe></div>
​	还可以设置散点和线段的颜色和宽度，以及是否显示x，y方向的0刻度线。

```python
import plotly as py
import plotly.graph_objs as go
import numpy as np

pyplt = py.offline.plot

N = 500
x = np.random.randn(N)

trace0 = go.Scatter(
    x=np.random.randn(N),
    y=np.random.randn(N) + 2,
    name='Above',
    mode='markers+lines',  # 散点+线的绘图
    marker=dict(
        size=10,  # 设置点的宽度
        color='rgba(152, 0, 0, .8)',  # 设置点的颜色
        line=dict(
            width=2,  # 设置线条的宽度
            color='rgb(0, 0, 0)'  # 设置线条的颜色
        )
    )
)

trace1 = go.Scatter(
    x=np.random.randn(N),
    y=np.random.randn(N) - 2,
    name='Below',
    mode='markers',
    marker=dict(
        size=10,
        color='rgba(255, 182, 193, .9)'
    )
)

data = [trace0, trace1]

layout = dict(title='Styled Scatter',
              yaxis=dict(zeroline=True),  # 显示y轴的0刻度线
              xaxis=dict(zeroline=False)  # 不显示x轴的0刻度线
              )

fig = dict(data=data, layout=layout)
pyplt(fig, filename='tmp/scatter_style.html')
```