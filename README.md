<!DOCTYPE html>
<html lang="cs">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Střídající se GIFy</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            overflow: hidden;
        }

        /* Kontejner pro střídající se GIFy */
        .background-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
        }

        .background-container img {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: none;
        }

        /* Styl červeného tlačítka */
        .button-container {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }

        .button {
            background-color: red;
            color: white;
            font-size: 24px;
            padding: 20px 40px;
            border: none;
            cursor: pointer;
            border-radius: 10px;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.3);
            transition: 0.3s;
        }

        .button:hover {
            background-color: darkred;
        }
    </style>
</head>
<body>

    <div class="background-container">
        <img src="aliens-alien.gif" alt="GIF 1">
        <img src="yay.gif" alt="GIF 2">
    </div>

    <div class="button-container">
        <button class="button">NEMAČKAT</button>
    </div>

    <script>
        let gifs = document.querySelectorAll('.background-container img');
        let index = 0;

        function changeGif() {
            gifs.forEach(gif => gif.style.display = 'none');
            gifs[index].style.display = 'block';
            index = (index + 1) % gifs.length;
        }

        changeGif();
        setInterval(changeGif, 3000);
    </script>

</body>
</html>
