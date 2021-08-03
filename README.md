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

        function mainloop() {
            colorRect(0, 0, canvas.width, canvas.height, 'black');
            colorRect(playerXpos, playerYpos, SIZE, SIZE, 'red');
        }



        function keyPressed(evt) {
            console.log(evt.keyCode);
        }
        
        function keyReleased(evt) {
            
        }

        function colorRect(x, y, w, h, c) {
            canvasContext.fillStyle = c;
            canvasContext.fillRect(x, y, w, h);
        }
    </script>
</body>
