### 基本概念

https://www.zhihu.com/question/26685414

对于我们程序员来说，基本就是**报表编程**，目标是让观者，以最轻松的方式理解负责数据。

### 知名解决方案

百度 echarts ，阿里巴巴的 https://antv.alipay.com/g2/doc/ 。最知名的开源库是 https://github.com/d3/d3 。

其中 echarts 是基于 canvas 的，g2/d3 都是 svg 的。


### 一个易用方案

http://recharts.org/#/zh-CN 是一个比较容易上手的基于 react/d3 技术的数据可视化解决方案。


### 步骤一：展示一个基本的 piechart

参考：http://recharts.org/#/en-US/examples/TwoSimplePieChart

视频：
http://digicity-1253322599.costj.myqcloud.com/chart-1-install.mp4


### 步骤二：修改数据

先来解决报错

>Warning: Failed prop type: The prop `dataKey` is marked as required in `Pie`, but its value is `undefined`.
    in Pie (at App.js:15)
    in App (at index.js:5)

警告：类型检查失败。datakey 这个属性在 Pid 中是必填的，但是目前的值是 undefined 。

视频：
http://digicity-1253322599.costj.myqcloud.com/chart-2-data.mp4


### 步骤三：修改 piechart 的大小和位置


```
<PieChart width={800} height={400}>
  <Pie cx={500} cy={200} innerRadius={40} outerRadius={80}
    />
</PieChart>
```


- **cx**
  - https://developer.mozilla.org/zh-CN/docs/Web/SVG/Attribute/cx
  - svg 属性，对于<circle> 和<ellipse> 元素, 此属性定义元素中心的X轴坐标. 如果未指定该属性, 默认为 "0"。

- **cy**
  - svg 属性，对于<circle> 和<ellipse> 元素, 此属性定义元素中心的X轴坐标. 如果未指定该属性, 默认为 "0"。

- **innerRadius**
  - rechart 自己的属性，内半径

- **outerRadius**
  - rechart 自己的属性，外半径

视频： http://digicity-1253322599.costj.myqcloud.com/chart-3-size.mp4


### 步骤四：设置颜色


视频：http://digicity-1253322599.costj.myqcloud.com/chart-4-color.mp4


### 步骤五：click 事件

视频：chart-5-click
http://digicity-1253322599.costj.myqcloud.com/chart-5-click.mp4



### 最终代码：

https://github.com/happypeter/dj-demos/tree/master/pie-chart
