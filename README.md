# EventProject
this is a project about changing theme in which you can change theme on clicking button
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="shortcut icon" href="https://cdn.pixabay.com/photo/2024/06/21/14/19/house-8844430_1280.jpg" type="image/x-icon">
    <title>Document</title>
</head>
<body>
    <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AI-Powered Theme Switcher</title>
    <link rel="stylesheet" href="styles.css">
    <style>
        body {
            transition: background-color 0.5s, color 0.5s, font-family 0.5s;
        }
        
        body.cyberpunk {
            background-color: black;
            color: #00ff00;
            font-family: 'Courier New', Courier, monospace;
            font-size: xx-large;
            filter: drop-shadow(16px 16px 20px blue); 

        }
        body.cyberpunk img {
            box-shadow: 0 0 20px rgba(0, 255, 0, 0.8), 0 0 40px rgba(0, 255, 0, 0.6);
        }
        body.nature {
            background-color: #e0f7fa;
            color: #004d40;
            font-family: 'Georgia', serif;
            background-image: linear-gradient(rgba(0,0,0,0),rgba(0,0,0,0)),url("https://cdn.pixabay.com/photo/2023/04/27/19/03/flower-meadow-7955256_1280.jpg");
        }
        
        body.retro {
            background-color: grey;
            color: #0000ff;
            font-family: 'Comic Sans MS', cursive;
            filter: grayscale(100%);
            transition: 2s;
            }
            
        img{
            height: 200px;
        }
        
    </style>
</head>
<body>
    <div class="theme-switcher">
        <input type="text" id="theme-input" placeholder="Type a theme (e.g., cyberpunk)">
        <button id="apply-theme" onclick="f1()">Apply Theme</button>
    </div>
    <div class="content">
        <h1>Welcome to the Themed Page</h1>
        <p>This page changes its appearance based on the selected theme.</p>
        <img src="https://cdn.pixabay.com/photo/2019/07/07/14/03/fiat-500-4322521_1280.jpg" alt="Theme-image" id="car">
    </div>
    
</body>
    <script>
        document.getElementById('apply-theme').addEventListener('click', function() {
            const themeInput = document.getElementById('theme-input').value.toLowerCase();
            const validThemes = ['cyberpunk', 'nature', 'retro'];
        
            // Remove existing theme classes
            document.body.classList.remove(...validThemes);
        
            if (validThemes.includes(themeInput)) {
                document.body.classList.add(themeInput);
                localStorage.setItem('selected-theme', themeInput);
            } else {
                alert('Please enter a valid theme: cyberpunk, nature, or retro.');
            }
        });
        
        // Load the saved theme on page load
        window.onload = function() {
            const savedTheme = localStorage.getItem('selected-theme');
            if (savedTheme) {
                document.body.classList.add(savedTheme);
                document.getElementById('theme-input').value = savedTheme;
            }
        };
    </script>
</html>
