<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>磁芯损耗预测结果</title>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
</head>
<body>
    <h1>真实值与预测值对比</h1>
    <canvas id="myChart" width="400" height="200"></canvas>
    <script>
        const ctx = document.getElementById('myChart').getContext('2d');
        
        // 示例数据，替换为你的真实值和预测值
        const actualValues = [1.2, 1.5, 1.8, 2.0, 2.1];  // 真实值
        const predictedValues = [1.1, 1.6, 1.9, 2.1, 2.0];  // 预测值
        
        const labels = actualValues.map((_, index) => index + 1); // 样本编号

        const myChart = new Chart(ctx, {
            type: 'line', // 折线图
            data: {
                labels: labels,
                datasets: [
                    {
                        label: '真实值',
                        data: actualValues,
                        borderColor: 'blue',
                        fill: false,
                    },
                    {
                        label: '预测值',
                        data: predictedValues,
                        borderColor: 'red',
                        fill: false,
                    }
                ]
            },
            options: {
                responsive: true,
                scales: {
                    x: {
                        title: {
                            display: true,
                            text: '样本编号'
                        }
                    },
                    y: {
                        title: {
                            display: true,
                            text: '磁芯损耗 (W/m^3)'
                        }
                    }
                }
            }
        });
    </script>
</body>
</html>
