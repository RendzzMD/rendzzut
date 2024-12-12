<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Convert Foto ke URL</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f4f4f9;
        }

        .container {
            text-align: center;
            background: #333;
            padding: 20px;
            border-radius: 10px;
            color: white;
            width: 400px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
        }

        input[type="file"] {
            margin: 20px 0;
        }

        textarea {
            width: 100%;
            height: 150px;
            margin-top: 10px;
            border-radius: 5px;
            padding: 10px;
            border: none;
            resize: none;
            font-size: 14px;
            background: #222;
            color: white;
        }

        button {
            background-color: #4CAF50;
            color: white;
            border: none;
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
            border-radius: 5px;
        }

        button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Convert Foto ke URL</h2>
        <p>Unggah foto Anda untuk mendapatkan URL berbasis data.</p>
        <input type="file" id="fileInput" accept="image/*">
        <button onclick="convertToURL()">Convert</button>
        <textarea id="result" readonly placeholder="Hasil URL akan muncul di sini..."></textarea>
    </div>

    <script>
        function convertToURL() {
            const fileInput = document.getElementById('fileInput');
            const result = document.getElementById('result');

            if (!fileInput.files.length) {
                alert('Pilih file terlebih dahulu!');
                return;
            }

            const file = fileInput.files[0];
            const reader = new FileReader();

            reader.onload = function(e) {
                result.value = e.target.result;
            };

            reader.onerror = function() {
                alert('Terjadi kesalahan saat membaca file.');
            };

            reader.readAsDataURL(file);
        }
    </script>
</body>
</html>
