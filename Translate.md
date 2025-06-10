
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TRANSLATE</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>EDULINGO</h1>
        <li class="nav-item">
            <a class="nav-link" href="index.html"><i class="fas fa-home" style="color: #2ecc71;"></i>HOME</a>
        </li>
        <p>Translate educational content into your local language.</p>

        
        <!-- Text Translation Section -->
        <div class="section">
           
            <h2>Text Translation</h2>
            <textarea id="inputText" placeholder="Enter text to translate..."></textarea>
            <label for="languageSelect">Select Language:</label>
            <select id="languageSelect">
                <option value="en">English</option>
                <option value="es">Spanish</option>
                <option value="fr">French</option>
                <option value="hi">Hindi</option>
                <option value="zh">Chinese</option>
                <!-- Add more languages as needed -->
            </select>
            <button id="translateTextBtn">Translate Text</button>
            <div id="translatedTextOutput"></div>
        </div>

        <!-- File Translation Section -->
        <div class="section">
            <h2>File Translation</h2>
            <input type="file" id="fileInput" accept=".txt,.pdf,.docx">
            <label for="fileLanguageSelect">Select Language:</label>
            <select id="fileLanguageSelect">
                <option value="en">English</option>
                <option value="es">Spanish</option>
                <option value="fr">French</option>
                <option value="hi">Hindi</option>
                <option value="zh">Chinese</option>
                <!-- Add more languages as needed -->
            </select>
            <button id="translateFileBtn">Translate File</button>
            <div id="translatedFileOutput"></div>
        </div>
    </div>

    <script src="script.js"></script>
</body>
</html>
