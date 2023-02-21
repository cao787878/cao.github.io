# cao.github.io 
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
    <meta name="viewport" content="initial-scale=1,maximum-scale=1,user-scalable=no" />
    <title>YOUR PAGE TITLE</title>
    <style>
      .container {
        text-align: center;
        font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
        display: block;
        max-width: 300px;
        margin: auto;
      }
      .timer {
        color: red;
        font-weight: bold;
        font-size: 150%;
      }
      p {
        font-size: 18px;
        margin: 10px;
      }
      .bold {
        font-weight: bold;
      }
      img {
        max-width: 250px;
        padding: 8px;
      }
      .button {
        background-color: green;
        color: white;
        padding: 18px;
        border-radius: 10px;
        max-width: 80%;
        margin: auto;
        font-size: 125%;
      }
      h1 {
        margin-bottom: 5px;
        margin-top: 5%;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <h1>An Awesome Headline</h1>
      <img src="https://via.placeholder.com/250" />
      <p>What the user has to do on the next page...</p>
      <p class="bold">WHY THIS TIMER IS HERE:</p>
      <p class="timer" id="timer">5:00</p>
      <div class="button bold" onclick="go()">CTA TO CLICK</div>
    </div>
    <script>
      function go() {
        window.onbeforeunload = null;
        window.location = 'https://yourtrackinglink/click';
      }
      var timeoutHandle;
      function countdown(minutes) {
        var seconds = 60;
        var mins = minutes;
        function tick() {
          var counter = document.getElementById('timer');
          var current_minutes = mins - 1;
          seconds--;
          counter.innerHTML = current_minutes.toString() + ':' + (seconds < 10 ? '0' : '') + String(seconds);
          if (seconds > 0) {
            timeoutHandle = setTimeout(tick, 1000);
          } else {
            if (mins > 1) {
              setTimeout(function () {
                countdown(mins - 1);
              }, 1000);
            }
            if (counter.innerHTML === '0:00') {
              counter.innerHTML = t;
              counter.classList.remove('b');
            }
          }
        }
        tick();
      }
      countdown(5);
    </script>
  </body>
</html>