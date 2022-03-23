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

&nbsp;&nbsp;&nbsp;&nbsp;可以设置三种模式，分别是<p class="note note-primary">mode='markers',#xtr1,散点图</p><p class="note note-primary">mode='lines',#xtr2,线形图</p><p class="note note-primary">mode='lines+markers',#xtr3,线形图+散点图组合</p>

```python
import chart_studio
import chart_studio.plotly as py
import plotly.graph_objects as go
import numpy as np  # 产生随机数

chart_studio.tools.set_credentials_file(
    username='ningyu',
    api_key='GFRRsIuXgMH0teXjCScZ'
)

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
py.plot(data, filename='scatter_basic_demo')
```
<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~ningyu/11.embed"></iframe>
​	还可以设置散点和线段的颜色和宽度，以及是否显示x，y方向的0刻度线。

```python
import chart_studio
import chart_studio.plotly as py
import plotly.graph_objects as go
import numpy as np

chart_studio.tools.set_credentials_file(
    username='ningyu',
    api_key='GFRRsIuXgMH0teXjCScZ'
)

N = 500

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
py.plot(fig, filename='scatter_style')
```

<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~ningyu/13.embed"></iframe>

&nbsp;&nbsp;&nbsp;&nbsp;利用pandas导入csv数据进行绘图

```python
import chart_studio
import chart_studio.plotly as py
import plotly.graph_objects as go
import pandas as pd

chart_studio.tools.set_credentials_file(
    username='ningyu',
    api_key='GFRRsIuXgMH0teXjCScZ'
)

df = pd.read_csv('Chapter02/dat/tk01_m15.csv')
df9 = df[:10]
print(df9)
idx = df9['xtim']
xd0 = (df9['close'] - 27) * 50
df2 = df9.copy()
df2['xd1'] = xd0 - 10
df2['xd2'] = xd0
df2['xd3'] = xd0 + 10
print('df2\n', df2)

xtr1 = go.Scatter(
    x=idx,
    y=df2['xd1'],
    mode='markers',  # xtr1,散点图
    name='xtr1-markers',
)
xtr2 = go.Scatter(
    x=idx,
    y=df2['xd2'],
    mode='lines',  # xtr2,曲线图
    name='xtr2-lines',
)
xtr3 = go.Scatter(
    x=idx,
    y=df2['xd3'],
    mode='markers+lines',  # xtr3,曲线+散点组合
    name='xtr3-markers+lines',
)
xdat = ([xtr1, xtr2, xtr3])
layout = go.Layout(
    title='收盘价--15分钟分时数据',
    xaxis=go.layout.XAxis(tickangle=-15)  # 标签的角度

)

fig = go.Figure(data=xdat, layout=layout)
py.plot(fig, filename=r'scatter_apply')

print('ok')

```
<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~ningyu/15.embed"></iframe>