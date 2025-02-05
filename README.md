# GameTest
Game Testing — это процесс тестирования видеоигр для выявления ошибок (багов), улучшения игрового процесса и обеспечения высокого качества продукта перед его выпуском.


<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Поймай квадрат!</title>
    <style>
        body { text-align: center; font-family: Arial, sans-serif; }
        #gameArea { position: relative; width: 300px; height: 300px; background: lightgray; margin: auto; }
        #square {
            width: 50px; height: 50px; background: red; position: absolute;
            top: 50%; left: 50%; transform: translate(-50%, -50%);
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h2>Поймай квадрат!</h2>
    <p>Нажми на квадрат, чтобы набрать очки.</p>
    <div id="gameArea">
        <div id="square"></div>
    </div>
    <p>Очки: <span id="score">0</span></p>

    <script>
        let score = 0;
        const square = document.getElementById("square");
        const scoreDisplay = document.getElementById("score");

        square.addEventListener("click", () => {
            score++;
            scoreDisplay.textContent = score;
            moveSquare();
        });

        function moveSquare() {
            const gameArea = document.getElementById("gameArea");
            const maxX = gameArea.clientWidth - square.clientWidth;
            const maxY = gameArea.clientHeight - square.clientHeight;

            const randomX = Math.floor(Math.random() * maxX);
            const randomY = Math.floor(Math.random() * maxY);

            square.style.left = randomX + "px";
            square.style.top = randomY + "px";
        }
    </script>
</body>
</html>
