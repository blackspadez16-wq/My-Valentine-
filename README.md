# My-Valentine-
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Surprise!</title>
    <style>
        body {
            background-color: #ffdae0;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            font-family: 'Arial', sans-serif;
            text-align: center;
        }
        .page { display: none; }
        .active { display: flex; flex-direction: column; align-items: center; }
        
        h1 { color: #d63384; font-size: 2.5rem; }
        
        /* Buttons */
        .btn {
            padding: 15px 25px;
            font-size: 1.2rem;
            border-radius: 50px;
            border: none;
            cursor: pointer;
            margin: 10px;
            transition: 0.2s;
        }
        #yesBtn { background-color: #ff4d6d; color: white; }
        #noBtn { background-color: #888; color: white; position: absolute; }
        .next-btn { background-color: #d63384; color: white; margin-top: 20px; }

        /* Simple Doodle Cat Style */
        .cat-container { font-size: 80px; margin-bottom: 20px; }
        
        /* Image Style */
        .final-pic {
            max-width: 80%;
            border-radius: 15px;
            border: 5px solid white;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }
    </style>
</head>
<body>

    <div id="page1" class="page active">
        <h1>Will you be my Valentine? ❤️</h1>
        <div style="height: 100px; width: 300px; position: relative;">
            <button id="yesBtn" class="btn" onclick="showPage(2)">Yes</button>
            <button id="noBtn" class="btn" onmouseover="moveNo()">No</button>
        </div>
    </div>

    <div id="page2" class="page">
        <div class="cat-container">🐱💐</div>
        <h1>I love you!</h1>
        <p>Here are some flowers for you.</p>
        <button class="btn next-btn" onclick="showPage(3)">Click for a surprise</button>
    </div>

    <div id="page3" class="page">
        <h1>Forever & Always</h1>
        <img src="https://via.placeholder.com/300" class="final-pic" alt="Our Picture">
        <p>❤️</p>
    </div>

    <script>
        function moveNo() {
            const noBtn = document.getElementById('noBtn');
            const x = Math.random() * (window.innerWidth - noBtn.offsetWidth);
            const y = Math.random() * (window.innerHeight - noBtn.offsetHeight);
            noBtn.style.left = x + 'px';
            noBtn.style.top = y + 'px';
            noBtn.style.position = 'fixed';
        }

        function showPage(pageNumber) {
            // Hide all pages
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });
            // Show the requested page
            document.getElementById('page' + pageNumber).classList.add('active');
        }
    </script>
</body>
</html>
 
