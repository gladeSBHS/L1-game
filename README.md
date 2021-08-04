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
        const UP_KEY = 40;
        const DOWN_KEY = 38;
        var rightKeyPressed = false;
        var leftKeyPressed = false;
        var upKeyPressed = false;
        var downKeyPressed = false;

        function mainloop() {
            colorRect(0, 0, canvas.width, canvas.height, 'black');
            colorRect(playerXpos, playerYpos, SIZE, SIZE, 'red');
            playermove();
        }

        function playermove() { 
            if (rightKeyPressed) {
                playerXpos += playerXspeed;
            }
         
            if (leftKeyPressed) {
                playerXpos -= playerXspeed;
            }
         
            if (upKeyPressed) {
                playerYpos += playerYspeed;
            }
         
            if (downKeyPressed) {
                playerYpos -= playerYspeed;
            }
        }
        

        function keyPressed(evt) {
            if (evt.keyCode == RIGHT_KEY) {
                rightKeyPressed = true;
            }
            if (evt.keyCode == LEFT_KEY) {
                leftKeyPressed = true;
            }
            if (evt.keyCode == UP_KEY) {
                upKeyPressed = true;
            }
            if (evt.keyCode == DOWN_KEY) {
                downKeyPressed = true;
            }
        }

        function keyReleased(evt) {
            if (evt.keyCode == RIGHT_KEY) {
                rightKeyPressed = false;
            }
            if (evt.keyCode == LEFT_KEY) {
                leftKeyPressed = false;
            }
            if (evt.keyCode == UP_KEY) {
                upKeyPressed = false;
            }
            if (evt.keyCode == DOWN_KEY) {
                downKeyPressed = false;
            }
        }


        function colorRect(x, y, w, h, c) {
            canvasContext.fillStyle = c;
            canvasContext.fillRect(x, y, w, h);
        }

    </script>
</body>
