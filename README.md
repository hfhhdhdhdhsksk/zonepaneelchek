# zonepaneelchek
file:///Users/joostvanagthoven/Downloads/systeemzonepaneel.html
<!DOCTYPE html>
<html lang="nl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Zonnepaneel Adviseur</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            color: #333;
            margin: 0;
            padding: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f9fafb; /* Lichtgrijze achtergrond */
            background-image: radial-gradient(circle, #ffffff 10%, #f9fafb 40%); /* Subtiele patroonachtergrond */
        }

        .container {
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            padding: 30px;
            width: 400px;
            max-width: 90%;
            text-align: center;
        }

        h1 {
            font-size: 24px;
            margin-bottom: 20px;
        }

        label {
            display: block;
            margin-bottom: 10px;
            font-weight: bold;
            text-align: left;
        }

        input, select {
            width: 100%;
            padding: 10px;
            font-size: 16px;
            margin-bottom: 20px;
            border: 1px solid #ddd;
            border-radius: 4px;
            box-sizing: border-box;
        }

        button {
            background-color: #4caf50;
            color: #fff;
            padding: 12px 20px;
            font-size: 16px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        button:hover {
            background-color: #45a049;
        }

        #advies {
            margin-top: 20px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Zonnepaneel Adviseur</h1>
        <p>Beantwoord de volgende vragen om het beste zonnepaneelbedrijf te vinden:</p>

        <label for="stroomverbruik">Hoeveel kWh stroom verbruikt u per jaar?</label>
        <input type="number" id="stroomverbruik" min="0" placeholder="Aantal kWh">

        <label for="aantalpersonen">Hoeveel mensen wonen er in uw huishouden?</label>
        <input type="number" id="aantalpersonen" min="1" placeholder="Aantal personen">

        <label for="terugleveren">Wilt u stroom terugleveren aan het net?</label>
        <select id="terugleveren">
            <option value="ja">Ja</option>
            <option value="nee">Nee</option>
        </select>

        <label for="opslaan">Wilt u stroom opslaan met een batterij?</label>
        <select id="opslaan">
            <option value="ja">Ja</option>
            <option value="nee">Nee</option>
        </select>

        <label for="zonpanelen">Heeft u al zonnepanelen? Zo ja, bij welk bedrijf?</label>
        <select id="zonpanelen">
            <option value="geen">Geen</option>
            <option value="coolblue">Coolblue</option>
            <option value="lg">LG Solar</option>
            <option value="ikea">IKEA Zonnepanelen</option>
        </select>

        <button onclick="adviseerZonnepaneelBedrijf()">Adviseer beste zonnepaneelbedrijf</button>

        <p id="advies"></p>
    </div>

    <script>
        function adviseerZonnepaneelBedrijf() {
            const stroomverbruik = document.getElementById('stroomverbruik').value;
            const aantalpersonen = document.getElementById('aantalpersonen').value;
            const terugleveren = document.getElementById('terugleveren').value;
            const opslaan = document.getElementById('opslaan').value;
            const zonpanelen = document.getElementById('zonpanelen').value;

            let adviesTekst = "Het beste zonnepaneelbedrijf voor u is: ";

            if (stroomverbruik > 5000 && aantalpersonen > 3) {
                adviesTekst += "Coolblue";
            } else if (terugleveren === 'ja' && opslaan === 'ja') {
                adviesTekst += "LG Solar";
            } else if (zonpanelen !== 'geen') {
                adviesTekst += "IKEA Zonnepanelen";
            } else {
                adviesTekst += "Geen specifiek advies gevonden.";
            }

            document.getElementById('advies').textContent = adviesTekst;
        }
    </script>
</body>
</html>
