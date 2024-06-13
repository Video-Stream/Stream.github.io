<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Кликер</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            font-family: Arial, sans-serif;
        }

        #counter {
            font-size: 2em;
            margin-bottom: 20px;
        }

        #clickButton {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            border: 5px solid black;
            background-size: cover;
            background-image: url('data:image/jpeg;base64,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');
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div id="counter">0</div>
    <div id="clickButton" onclick="incrementCounter()"></div>

    <script>
        let counter = 0;
        function incrementCounter() {
            counter++;
            document.getElementById('counter').textContent = counter;
        }
    </script>
</body>
<html>

