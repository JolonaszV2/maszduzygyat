<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Studniówka</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            text-align: center;
            background-color: #ffe6e6;
            color: #d63384;
            margin: 0;
            padding: 0;
        }
        h1 {
            margin-top: 20vh;
            font-size: 3em;
            font-weight: bold;
        }
        .buttons {
            margin-top: 20px;
        }
        button {
            font-size: 1.5em;
            padding: 10px 20px;
            margin: 10px;
            border: 2px solid #d63384;
            background-color: white;
            color: #d63384;
            border-radius: 10px;
            cursor: pointer;
            transition: 0.3s ease;
        }
        button:hover {
            background-color: #d63384;
            color: white;
        }
        .hidden {
            display: none;
        }
        #message {
            font-size: 2.5em;
            margin-top: 20px;
        }
        #qrCode {
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <h1>Czy pójdziesz ze mną na studniówkę?</h1>
    <div class="buttons">
        <button onclick="showLove()">TAK</button>
        <button onclick="showNoRefusal()">NIE</button>
    </div>
    <div id="message" class="hidden"></div>
    <div id="qrCode" class="hidden"></div>

    <script>
        function showLove() {
            const message = document.getElementById('message');
            const qrCode = document.getElementById('qrCode');
            message.classList.remove('hidden');
            message.innerHTML = "KOCHAM CIĘ";
            qrCode.classList.add('hidden');
        }

        function showNoRefusal() {
            const message = document.getElementById('message');
            const qrCode = document.getElementById('qrCode');
            message.classList.remove('hidden');
            message.innerHTML = "Nie przyjmuję odmowy";
            
            // Tworzenie kodu QR
            qrCode.classList.remove('hidden');
            qrCode.innerHTML = "";
            const qrCanvas = document.createElement('canvas');
            qrCanvas.id = 'qrCanvas';
            qrCode.appendChild(qrCanvas);

            // Wygenerowanie kodu QR
            const qrText = "Nie przyjmuję odmowy!";
            const qr = new QRCode(qrCanvas, {
                text: qrText,
                width: 200,
                height: 200
            });
        }
    </script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
</body>
</html>
