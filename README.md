<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>หาค.ร.นและห.ร.ม</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f0f0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            position: relative;
        }
        .container {
            background-color: #ffffff;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            max-width: 400px;
            width: 100%;
            text-align: center;
        }
        h1 {
            color: #333;
            margin-bottom: 20px;
        }
        input[type="number"] {
            width: calc(100% - 20px);
            padding: 10px;
            margin: 10px 0;
            box-sizing: border-box;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        button {
            padding: 10px 20px;
            background-color: #28a745;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
            margin-top: 10px;
        }
        button:hover {
            background-color: #218838;
        }
        .result {
            margin-top: 20px;
            font-size: 18px;
            color: #555;
        }
        .credit {
            position: absolute;
            bottom: 10px;
            right: 10px;
            font-size: 12px;
            color: #888;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>หาค.ร.นและห.ร.ม</h1>
        <label for="num1">จำนวนเต็มที่ 1:</label>
        <input type="number" id="num1">
        <label for="num2">จำนวนเต็มที่ 2:</label>
        <input type="number" id="num2">
        <button onclick="calculate()">คำนวณ</button>
        <div class="result" id="result"></div>
    </div>
    <div class="credit">สร้างโดย Anas Masae</div>

    <script>
        function gcd(a, b) {
            while (b != 0) {
                let t = b;
                b = a % b;
                a = t;
            }
            return a;
        }

        function lcm(a, b) {
            return Math.abs(a * b) / gcd(a, b);
        }

        function calculate() {
            const num1 = parseInt(document.getElementById('num1').value);
            const num2 = parseInt(document.getElementById('num2').value);

            if (isNaN(num1) || isNaN(num2)) {
                document.getElementById('result').innerText = "กรุณาใส่จำนวนเต็มที่ถูกต้อง";
                return;
            }

            const gcdResult = gcd(num1, num2);
            const lcmResult = lcm(num1, num2);

            document.getElementById('result').innerText = `ห.ร.ม ของ ${num1} และ ${num2} คือ: ${gcdResult}\nค.ร.น ของ ${num1} และ ${num2} คือ: ${lcmResult}`;
        }
    </script>
</body>
</html>
