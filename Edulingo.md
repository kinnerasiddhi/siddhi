
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EDULINGO</title>
    <link rel="stylesheet" href="style.css">
  <link rel="icon" type="image/x-icon" href="edulingo.jpg">
</head>
<body>
    
    <div class="container">
        

        
        <h1>Edulingo</h1>
        <p>Translate educational content into your local language.</p>
            <nav class="navbar navbar-expand-lg navbar-light bg-light">
                <div class="container-fluid">
                    <a class="navbar-brand" href="#">
                        <img src="edulingo.jpg" alt="Logo" style="height: 100px;" onclick="location.reload();">
                        EduLingo
                    </a>
                    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
                        <span class="navbar-toggler-icon"></span>
                    </button>
                    <div></div>
                    <div class="collapse navbar-collapse" id="navbarNav">
                        <ul class="navbar-nav ms-auto">
                           
                            <li class="nav-item">
                                <a class="nav-link" href="translate.html"><i class="fas fa-book" style="color: #3498db;"></i> Translate</a>
                            </li>
                            <li class="nav-item">
                                <a class="nav-link" href="speechtotext.html"><i class="fas fa-stethoscope" style="color: #e74c3c;"></i> Speech-to-Text</a>
                            </li>
            
                            <!-- Language Dropdown -->
                            <div class="dropdown">
                                <button class="btn btn-primary dropdown-toggle" type="button" id="languageDropdown" data-bs-toggle="dropdown" aria-expanded="false">
                                    English
                                </button>
                                <ul class="dropdown-menu" id="languageList">
                                    <li><a class="dropdown-item" href="#" data-lang="en">English</a></li>
                                    <li><a class="dropdown-item" href="#" data-lang="hi">Hindi</a></li>
                                    <li><a class="dropdown-item" href="#" data-lang="te">Telugu</a></li>
                                    <li><a class="dropdown-item" href="#" data-lang="ta">Tamil</a></li>
                                    <li><a class="dropdown-item" href="#" data-lang="kn">Kannada</a></li>
                                </ul>
                            </div>
                        </ul>
                    </div>
                </div>
            </nav>
            Reply
            Forward
            

    <script src="script.js"></script>
</body>
</html><
