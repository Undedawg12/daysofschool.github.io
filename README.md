<!DOCTYPE html>
<!--
  GitHub Pages Ready

  1. Save this file as index.html
  2. Upload it to a GitHub repository
  3. Go to Settings > Pages
  4. Select Deploy from branch > main
  5. Your website will go live automatically
-->
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Countdown to June 16</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: Arial, Helvetica, sans-serif;
    }

    body {
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #111827, #1f2937, #374151);
      color: white;
      overflow: hidden;
    }

    .container {
      text-align: center;
      padding: 40px;
      border-radius: 24px;
      background: rgba(255, 255, 255, 0.08);
      backdrop-filter: blur(10px);
      box-shadow: 0 8px 30px rgba(0,0,0,0.35);
      width: 90%;
      max-width: 600px;
    }

    h1 {
      font-size: 3rem;
      margin-bottom: 20px;
    }

    .countdown {
      display: flex;
      justify-content: center;
      gap: 20px;
      flex-wrap: wrap;
      margin-top: 20px;
    }

    .time-box {
      background: rgba(255,255,255,0.12);
      padding: 20px;
      border-radius: 18px;
      min-width: 110px;
    }

    .number {
      font-size: 3rem;
      font-weight: bold;
    }

    .label {
      margin-top: 8px;
      font-size: 1rem;
      opacity: 0.85;
      text-transform: uppercase;
      letter-spacing: 1px;
    }

    .message {
      margin-top: 25px;
      font-size: 1.2rem;
      opacity: 0.9;
    }

    @media (max-width: 600px) {
      h1 {
        font-size: 2rem;
      }

      .number {
        font-size: 2.2rem;
      }

      .time-box {
        min-width: 90px;
        padding: 15px;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Countdown to June 16</h1>

    <div class="countdown">
      <div class="time-box">
        <div class="number" id="days">0</div>
        <div class="label">Days</div>
      </div>

      <div class="time-box">
        <div class="number" id="hours">0</div>
        <div class="label">Hours</div>
      </div>

      <div class="time-box">
        <div class="number" id="minutes">0</div>
        <div class="label">Minutes</div>
      </div>

      <div class="time-box">
        <div class="number" id="seconds">0</div>
        <div class="label">Seconds</div>
      </div>
    </div>

    <div class="message" id="message"></div>
  </div>

  <script>
    const targetDate = new Date('June 16, 2026 00:00:00').getTime();

    function updateCountdown() {
      const now = new Date().getTime();
      const distance = targetDate - now;

      if (distance <= 0) {
        document.getElementById('days').innerText = '0';
        document.getElementById('hours').innerText = '0';
        document.getElementById('minutes').innerText = '0';
        document.getElementById('seconds').innerText = '0';
        document.getElementById('message').innerText = 'June 16 has arrived!';
        return;
      }

      const days = Math.floor(distance / (1000 * 60 * 60 * 24));
      const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((distance % (1000 * 60)) / 1000);

      document.getElementById('days').innerText = days;
      document.getElementById('hours').innerText = hours;
      document.getElementById('minutes').innerText = minutes;
      document.getElementById('seconds').innerText = seconds;

      document.getElementById('message').innerText = `${days} days left until June 16!`;
    }

    updateCountdown();
    setInterval(updateCountdown, 1000);
  </script>
</body>
</html>
