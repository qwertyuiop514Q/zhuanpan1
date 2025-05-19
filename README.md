# zhuanpan1
我的转盘小游戏
<!DOCTYPE html>
<html lang="zh">
<head>
  <meta charset="UTF-8">
  <title>转盘游戏</title>
  <style>
    body {
      text-align: center;
      font-family: sans-serif;
      background-color: #f9f9f9;
    }

    .wheel {
      width: 300px;
      height: 300px;
      border: 10px solid #333;
      border-radius: 50%;
      margin: 50px auto;
      position: relative;
      overflow: hidden;
      transform: rotate(0deg);
      transition: transform 4s ease-out;
    }

    .segment {
      width: 50%;
      height: 50%;
      position: absolute;
      top: 50%;
      left: 50%;
      transform-origin: 0% 0%;
      background: #ffcc00;
      color: #000;
      line-height: 140px;
      text-align: center;
      font-weight: bold;
    }

    .pointer {
      width: 0; 
      height: 0; 
      border-left: 20px solid transparent;
      border-right: 20px solid transparent;
      border-bottom: 30px solid red;
      position: absolute;
      top: 10px;
      left: calc(50% - 20px);
    }

    button {
      padding: 10px 20px;
      font-size: 18px;
      cursor: pointer;
    }
  </style>
</head>
<body>

<h1>🎯 转盘游戏</h1>

<div class="pointer"></div>
<div class="wheel" id="wheel">
  <!-- 6 个选项 -->
  <div class="segment" style="transform: rotate(0deg) skewY(-60deg); background: #f44336;">火锅</div>
  <div class="segment" style="transform: rotate(60deg) skewY(-60deg); background: #e91e63;">烧烤</div>
  <div class="segment" style="transform: rotate(120deg) skewY(-60deg); background: #9c27b0;">披萨</div>
  <div class="segment" style="transform: rotate(180deg) skewY(-60deg); background: #2196f3;">汉堡</div>
  <div class="segment" style="transform: rotate(240deg) skewY(-60deg); background: #4caf50;">寿司</div>
  <div class="segment" style="transform: rotate(300deg) skewY(-60deg); background: #ff9800;">麻辣烫</div>
</div>

<button onclick="spin()">🎲 开始转盘</button>

<script>
  let angle = 0;
  function spin() {
    const wheel = document.getElementById('wheel');
    const randomSpin = Math.floor(Math.random() * 360 + 1440); // 至少转 4 圈
    angle += randomSpin;
    wheel.style.transform = `rotate(${angle}deg)`;
  }
</script>

</body>
</html>
