<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cool Website</title>
    <style>
        /* Reset some default styles */
        body, h1, p {
            margin: 0;
            padding: 0;
        }

        /* Main styles */
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
        }

        header {
            background-color: #333;
            color: #fff;
            padding: 10px;
            text-align: center;
        }

        .container {
            max-width: 800px;
            margin: 20px auto;
            padding: 20px;
            background-color: #fff;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
            border-radius: 5px;
        }

        .hero {
            text-align: center;
            padding: 50px 0;
            background-image: url('your-image-url.jpg');
            background-size: cover;
            background-position: center;
            color: #fff;
        }

        .hero h1 {
            font-size: 36px;
            margin-bottom: 10px;
        }

        .hero p {
            font-size: 18px;
        }

        .cta-button {
            display: inline-block;
            background-color: #ff5500;
            color: #fff;
            padding: 10px 20px;
            border-radius: 5px;
            text-decoration: none;
            margin-top: 20px;
        }

        .cta-button:hover {
            background-color: #e04400;
        }

        footer {
            text-align: center;
            padding: 20px;
            background-color: #333;
            color: #fff;
        }
    </style>
</head>
<body>
    <header>
        <h1>Cool Website</h1>
        <p>Welcome to our cool website created with HTML and CSS!</p>
    </header>

    <div class="container">
        <div class="hero">
            <h1>Discover the Magic</h1>
            <p>Explore our amazing content and have a great time!</p>
            <a class="cta-button" href="#">Get Started</a>
        </div>
    </div>

    <footer>
        <p>&copy; 2023 Cool Website. All rights reserved.</p>
    </footer>
</body>
</html>
