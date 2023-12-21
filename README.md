<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Morse Code Translator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
        }

        .container {
            text-align: center;
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        textarea {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
        }

        button {
            padding: 10px;
            background-color: #4caf50;
            color: #fff;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Morse Code Translator</h1>
        <label for="inputText">Enter text:</label>
        <textarea id="inputText" placeholder="Type your text here"></textarea>
        <button onclick="translateToMorse()">Translate to Morse Code</button>
        <label for="outputMorse">Morse Code:</label>
        <textarea id="outputMorse" readonly></textarea>
    </div>

    <script>
        function translateToMorse() {
            const inputText = document.getElementById("inputText").value.toUpperCase();
            const morseCode = textToMorse(inputText);
            document.getElementById("outputMorse").value = morseCode;
        }

        function textToMorse(text) {
            const morseCodeMap = {
                'A': '.-', 'B': '-...', 'C': '-.-.', 'D': '-..', 'E': '.', 'F': '..-.', 'G': '--.', 'H': '....',
                'I': '..', 'J': '.---', 'K': '-.-', 'L': '.-..', 'M': '--', 'N': '-.', 'O': '---', 'P': '.--.',
                'Q': '--.-', 'R': '.-.', 'S': '...', 'T': '-', 'U': '..-', 'V': '...-', 'W': '.--', 'X': '-..-',
                'Y': '-.--', 'Z': '--..', '0': '-----', '1': '.----', '2': '..---', '3': '...--', '4': '....-',
                '5': '.....', '6': '-....', '7': '--...', '8': '---..', '9': '----.',
                ' ': '/'
            };

            return text.split('').map(char => morseCodeMap[char] || char).join(' ');
        }
    </script>
</body>
</html>
