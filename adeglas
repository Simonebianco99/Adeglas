<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calcolo delle Facce</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #e0ffe0; /* Verde molto chiaro */
        }
        .container {
            background: white;
            padding: 20px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
            border-radius: 8px;
            text-align: center;
        }
        .input-field {
            margin-bottom: 10px;
        }
        .input-field label {
            display: block;
            margin-bottom: 5px;
        }
        .input-field input {
            width: 100%;
            padding: 8px;
            box-sizing: border-box;
        }
        .result {
            margin-top: 20px;
            font-weight: bold;
        }
        .final-result {
            margin-top: 20px;
            font-weight: bold;
            color: red;
        }
        .highlight {
            background-color: yellow;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Inserisci Dimensioni</h2>
        <div class="input-field">
            <label for="length">Lunghezza (cm):</label>
            <input type="number" id="length" required>
        </div>
        <div class="input-field">
            <label for="width">Larghezza (cm):</label>
            <input type="number" id="width" required>
        </div>
        <div class="input-field">
            <label for="height">Altezza (cm):</label>
            <input type="number" id="height" required>
        </div>
        <button onclick="calculateAreas()">Calcola Aree Totali</button>
        <div class="result" id="result"></div>
        <div class="result" id="abundanceResult" style="display:none;"></div>
        <div class="input-field" id="thickness-input" style="display:none;">
            <label for="thickness">Inserisci Spessore del Materiale:</label>
            <input type="number" id="thickness">
        </div>
        <button id="calculateFinalButton" style="display:none;" onclick="calculateFinalValue()">Calcola Valore Finale</button>
        <div class="final-result" id="finalResult" style="display:none;"></div>
    </div>

    <script>
        let abundanceResult = 0;

        function calculateAreas() {
            const length = parseFloat(document.getElementById('length').value);
            const width = parseFloat(document.getElementById('width').value);
            const height = parseFloat(document.getElementById('height').value);

            if (isNaN(length) || isNaN(width) || isNaN(height)) {
                alert('Per favore, inserisci tutti i valori.');
                return;
            }

            const face1 = length * width;
            const face2 = width * height;
            const face3 = width * height;
            const face4 = length * height;
            const face5 = length * height;

            const totalArea = face1 + face2 + face3 + face4 + face5;
            const formattedTotalArea = totalArea.toFixed(2);

            document.getElementById('result').innerText = `La somma delle aree è: ${formattedTotalArea}`;

            // Calcola l'abbondaggio
            abundanceResult = (totalArea * 1.2).toFixed(2);
            document.getElementById('abundanceResult').innerText = `Abbonda aggio → ${abundanceResult}`;
            document.getElementById('abundanceResult').style.display = 'block';

            // Mostra il campo di input per lo spessore del materiale
            document.getElementById('thickness-input').style.display = 'block';
            document.getElementById('calculateFinalButton').style.display = 'block';
        }

        function calculateFinalValue() {
            const thickness = parseFloat(document.getElementById('thickness').value);

            if (isNaN(thickness)) {
                alert('Per favore, inserisci un valore valido per lo spessore del materiale.');
                return;
            }

            // Somma lo spessore del materiale con 2, poi moltiplica per 10
            const intermediateValue = (thickness + 2) * 10;

            // Moltiplica il valore intermedio con l'abbondaggio
            const finalValue = (abundanceResult * intermediateValue).toFixed(2);

            document.getElementById('finalResult').innerHTML = `Valore Finale → <span class="highlight">${finalValue} €</span>`;
            document.getElementById('finalResult').style.display = 'block';
        }
    </script>
</body>
</html>
