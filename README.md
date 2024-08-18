<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Digital Clock</title>
    <style>
        body {
            background-color: #1a1a1a;
            color: white;
            font-family: 'Arial', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            flex-direction: column;
        }

        .clock {
            border: 2px solid;
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            font-size: 3em;
            position: relative;
            background: linear-gradient(45deg, #00ff00, #ff00ff);
            color: white;
            box-shadow: 0px 0px 20px 10px rgba(0, 0, 0, 0.5);
        }

        .clock .time {
            border: 2px solid;
            border-radius: 15px;
            padding: 15px;
            text-align: center;
            background: #000;
            color: white;
            box-shadow: 0px 0px 10px 2px rgba(0, 0, 0, 0.5);
            display: inline-block;
        }

        .clock .time span {
            margin: 0 5px;
        }

        .clock .time .label {
            font-size: 0.5em;
            display: block;
        }

        .title {
            font-size: 2em;
            color: #00ff00;
        }

        .title span {
            color: #ff00ff;
        }
    </style>
</head>
<body>
    <div class="title">
        Digital <span>Clock</span>
    </div>
    <div class="clock">
        <div class="time">
            <span id="hours">00</span>
            <span class="label">HOURS</span>
        </div>
        <span>:</span>
        <div class="time">
            <span id="minutes">00</span>
            <span class="label">MINS</span>
        </div>
        <span>:</span>
        <div class="time">
            <span id="seconds">00</span>
            <span class="label">SEC</span>
        </div>
    </div>

    <script>
        function updateClock() {
            const now = new Date();
            const hours = String(now.getHours()).padStart(2, '0');
            const minutes = String(now.getMinutes()).padStart(2, '0');
            const seconds = String(now.getSeconds()).padStart(2, '0');

            document.getElementById('hours').textContent = hours;
            document.getElementById('minutes').textContent = minutes;
            document.getElementById('seconds').textContent = seconds;
        }

        setInterval(updateClock, 1000);
        updateClock(); // initial call to set the clock immediately
    </script>
</body>
</html>
