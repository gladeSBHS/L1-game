# L1Game
<!doctype html>

<body>
    <canvas id="gameCanvas" width="600" height="600"></canvas>
    <script>
        var canvas, canvasContext;

        window.onload = function() {
            canvas = document.getElementById('gameCanvas');
            canvasContext = canvas.getContext('2d');

            document.addEventListener('keydown', keyPressed);
            document.addEventListener('keyup', keyReleased);

            setInterval(mainloop, 1000 / 50);

        }

        var SIZE = 20;
        var playerXpos = 0;
        var playerYpos = 0;
        var playerXspeed = 5;
        var playerYspeed = 5;

        const LEFT_KEY = 37;
        const RIGHT_KEY = 39;
        const UP_KEY = 38;
        const DOWN_KEY = 40;

        function mainloop() {
            colorRect(0, 0, canvas.width, canvas.height, 'black');
            colorRect(playerXpos, playerYpos, SIZE, SIZE, 'red');
        }



        function keyPressed(evt) {
            console.log(evt.keyCode);
            if (evt.keyCode == RIGHT_KEY) {
                RIGHT_KEY = true;
            }
        }

        function keyReleased(evt) {
            if (evt.keyCode == RIGHT_KEY) {
                RIGHT_KEY = false;
            }
        }

        function colorRect(x, y, w, h, c) {
            canvasContext.fillStyle = c;
            canvasContext.fillRect(x, y, w, h);
        }

    </script>
</body>
