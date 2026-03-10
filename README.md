<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>0 秒</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: "Microsoft YaHei", Arial, sans-serif;
            background: linear-gradient(135deg, #e0f7fa 0%, #f5f5f5 100%);
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            color: #333;
        }
        .timer-box {
            background: white;
            padding: 40px 60px;
            border-radius: 12px;
            box-shadow: 0 4px 20px rgba(0,0,0,0.1);
            text-align: center;
        }
        .main-title {
            font-size: 32px;
            margin-bottom: 20px;
            color: #2196f3;
        }
        .timer-text {
            font-size: 24px;
            margin-bottom: 15px;
        }
        .hint-text {
            font-size: 14px;
            color: #666;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <div class="timer-box">
        <h1 class="main-title">窗口打开计时器</h1>
        <p class="timer-text">当前窗口已打开：<span id="timer">0</span> 秒</p>
        <p class="hint-text">👉 浏览器标签页名称同步显示计时</p>
    </div>

    <script>
        // 记录页面打开的起始时间
        const startTime = Date.now();
        const timerElement = document.getElementById('timer');

        // 每秒更新计时器和窗口标题
        function updateTimer() {
            const elapsedSeconds = Math.floor((Date.now() - startTime) / 1000);
            timerElement.textContent = elapsedSeconds;
            document.title = `${elapsedSeconds} 秒`; // 核心：修改窗口标题
        }

        // 立即执行一次，避免延迟
        updateTimer();
        // 每秒更新
        setInterval(updateTimer, 1000);
    </script>
</body>
</html>
