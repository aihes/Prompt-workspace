Task：
1、为如下数据选择一种最好的Echarts数据化展示方式等。
2、将数据转换为Echarts渲染的数据格式。
3、写Echarts渲染的代码，将数据进行渲染：

Context：
ECharts是一个基于 JavaScript
的开源可视化图表库，提供了常规的折线图、柱状图、散点图、饼图、K线图，用于统计的盒形图，用于地理数据可视化的地图、热力图、线图，用于关系数据可视化的关系图、treemap、旭日图，多维数据可视化的平行坐标，还有用于
BI 的漏斗图，仪表盘，并且支持图与图之间的混搭。

我不是前端同学对前端代码不熟悉，因此有以下要求。

要求：

- 一定要给出完整的代码，方便我直接运行代码； Provide the full code.
- 如果不能一次性给出，可以分多次给出；If you cannot provide the full code all at once, you can provide it in multiple
  parts.

- 记住给出完整的代码，思考流程使用javascript注释形式。Remember to provide the full code and use javascript comments to
  explain the thought process.

- 在javascript注释中体现思考过程。Reflect the thinking process in the JavaScript comments.

Example，案例：

```
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>ECharts</title>
    <!-- Import ECharts file -->
    <script src="https://cdn.jsdelivr.net/npm/echarts@5/dist/echarts.min.js"></script>
</head>
<body>
    <!-- Prepare div containers with dimensions for ECharts -->
    <div id="nvidiaChart" style="width: 800px;height:400px;"></div>
    <div id="appleChart" style="width: 800px;height:400px;"></div>
    <div id="businessChart" style="width: 800px;height:400px;"></div>
    <script type="text/javascript">
        // Initialize ECharts instances
        var nvidiaChart = echarts.init(document.getElementById('nvidiaChart'));
        var appleChart = echarts.init(document.getElementById('appleChart'));
        
        // Prepare data
        var years = ['2017', '2018', '2019', '2020'];
        
        // NVIDIA data
        var nvidiaRevenue = [97, 117, 109, 166];
        var nvidiaProfit = [30, 41, 28, 39];
        var nvidiaStockPrice = [200, 135, 235, 520];
        
        // Apple data
        var appleRevenue = [229.2, 265.6, 260.2, 274.5];
        var appleProfit = [48.4, 59.5, 55.3, 57.4];
        var appleStockPrice = [169.23, 157.74, 293.65, 132.69];        
        // NVIDIA chart options
        var nvidiaOption = {
            title: { text: 'NVIDIA Financial and Stock Data' },
            tooltip: {},
            legend: { data: ['Revenue', 'Profit', 'Stock Price'] },
            xAxis: { data: years },
            yAxis: {},
            series: [
                { name: 'Revenue', type: 'bar', data: nvidiaRevenue },
                { name: 'Profit', type: 'bar', data: nvidiaProfit },
                { name: 'Stock Price', type: 'line', data: nvidiaStockPrice }
            ]
        };
        
        // Apple chart options
        var appleOption = {
            title: { text: 'Apple Financial and Stock Data' },
            tooltip: {},
            legend: { data: ['Revenue', 'Profit', 'Stock Price'] },
            xAxis: { data: years },
            yAxis: {},
            series: [
                { name: 'Revenue', type: 'bar', data: appleRevenue },
                { name: 'Profit', type: 'bar', data: appleProfit },
                { name: 'Stock Price', type: 'line', data: appleStockPrice }
            ]
        };
        
        nvidiaChart.setOption(nvidiaOption);
        appleChart.setOption(appleOption);
    </script>
</body>
</html>
```

我的数据：

```
以下是一些基本英伟达公司的财务数据：

2017年：年度总收入为97亿美元，净利润为30亿美元。
2018年：年度总收入为117亿美元，净利润为41亿美元。
2019年：年度总收入为109亿美元，净利润为28亿美元。
2020年：年度总收入为166亿美元，净利润为39亿美元。
以下是一些股票相关的数据：

2017年末：股票价格约为200美元。
2018年末：股票价格约为135美元。
2019年末：股票价格约为235美元。
2020年末：股票价格约为520美元。


以下是Apple公司的一些数据
年份	年度总收入 (亿美元)	净利润 (亿美元)	每股收益 (美元)
2017	229.2	48.4	9.27
2018	265.6	59.5	12.01
2019	260.2	55.3	11.97
2020	274.5	57.4	13.20

以下是一些与苹果股票相关的历史数据：

年份	年末股票价格 (美元)	年度股息 (美元)
2017	169.23	2.46
2018	157.74	2.72
2019	293.65	3.05
2020	132.69	3.28


我的业务数据，value是人数，name是类目偏好：

```

<!DOCTYPE html>
