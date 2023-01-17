# 🌐 Hello World 



<p align="center">
<div id="header" align="center">
  <img src="https://i.pinimg.com/originals/ae/56/d1/ae56d10f023f455739a635e435732a94.gif" width="700"/>
</div>

 <canvas width="600" height="300" ></canvas>
  <h1>Snake game</h1>
  <p>Score : <span class="Score">0</span></p>
  <p>Level : <span class="level">0</span></p>
  <script>window.addEventListener("load", function () {
  let canvas = document.querySelector("#canvas");
  let ctx = canvas.getContext("2d");
  let player = {
    dir: "right",
    level: 1,
    size: 18,
    color: "blue",
    snake: []
  };
  let food = {};
  let isPlaying = true;
  GameInit();
  let step = function () {
    if (isPlaying) {
      draw();
      update();
    }
  };
  step();
  let gameStart = setInterval(step, 200);
  function update() {
    let current = {
      x: player.snake[0].x,
      y: player.snake[0].y,
      size: player.snake[0].size
    };
    if (player.dir == "right") {
      current.x += 20;
    } else if (player.dir == "left") {
      current.x -= 20;
    } else if (player.dir == "up") {
      current.y -= 20;
    } else if (player.dir == "down") {
      current.y += 20;
    }
    if (current.x > canvas.width) {
      current.x = 0;
    } else if (current.x < 0) {
      current.x = canvas.width;
    }
    if (current.y > canvas.height) {
      current.y = 0;
    } else if (current.y < 0) {
      current.y = canvas.height;
    }
    player.snake.unshift(current);
    player.snake.pop();
    for (let i = 1; i < player.snake.length; i++) {
      if (collision(player.snake[0], player.snake[i])) {
        GameOver();
      }
    }
    if (collision(player.snake[0], food)) {
      food.x = Math.floor(Math.random() * (canvas.width - 20));
      food.y = Math.floor(Math.random() * (canvas.height - 20));
      player.snake.push({
        x: player.snake[player.snake.length - 1].x - 20,
        y: player.snake[player.snake.length - 1].y,
        size: 18
      });
      player.score += 10;
      document.querySelector(".Score").textContent = player.score;
      if (player.score % 100 == 0) {
        player.level++;
        clearInterval(gameStart);
        gameStart = setInterval(step, 200 - player.level * 10);
      }
    }
    document.querySelector(".level").textContent = player.level;
  }
  function draw() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    colorRect(food.x, food.y, food.size, food.size, "orange");
    for (let i = player.snake.length - 1; i >= 0; i--) {
      colorRect(
        player.snake[i].x,
        player.snake[i].y,
        player.snake[i].size,
        player.snake[i].size,
        player.color
      );
    }
  }
  function colorRect(x, y, w, h, drawColor) {
    ctx.fillStyle = drawColor;
    ctx.fillRect(x, y, w, h);
  }
  function collision(a, b) {
    let w =
      a.x - b.x <= 0
        ? Math.abs(a.x - b.x) <= a.size
        : Math.abs(a.x - b.x) <= b.size;
    let h =
      a.y - b.y <= 0
        ? Math.abs(a.y - b.y) <= a.size
        : Math.abs(a.y - b.y) <= b.size;
    return w && h;
  }
  function GameOver() {
    alert("game over try again");
    isPlaying = false;
    GameInit();
    clearInterval(gameStart);
    gameStart = setInterval(step, 220 - player.level * 20);
  }
  function GameInit() {
    player.dir = "right";
    player.snake = [];
    player.score = 0;
    for (let i = 3; i > 0; i--) {
      player.snake.push({
        x: i * 20,
        y: canvas.height / 2 - 10,
        size: 18
      });
      player.score = 0;
      player.level = 1;
      document.querySelector(".Score").textContent = player.score;
      document.querySelector(".level").textContent = player.level;
    }
    food = {
      x: Math.floor(Math.random() * (canvas.width - 20)),
      y: Math.floor(Math.random() * (canvas.height - 20)),
      color: "orange",
      size: 20
    };
  }
  window.addEventListener("keydown", function (e) {
    let btns = {
      40: "down",
      39: "right",
      38: "up",
      37: "left"
    };
    if (btns[e.keyCode] !== undefined) {
      isPlaying = true;
      player.dir = btns[e.keyCode];
    } else {
      isPlaying = false;
    }
  });
});
  </script>

## 🎃  Ma Presentation 

Je suis Jonas j'ai 18 ans et chez Eden School en 2eme Année 


###  Mes Competences : 
![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)
![Git](https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white)
![Figma](https://img.shields.io/badge/figma-%23F24E1E.svg?style=for-the-badge&logo=figma&logoColor=white)
![CodePen](https://img.shields.io/badge/Codepen-000000?style=for-the-badge&logo=codepen&logoColor=white)


### En cours : 
![PHP](https://img.shields.io/badge/php-%23777BB4.svg?style=for-the-badge&logo=php&logoColor=white)
![MySQL](https://img.shields.io/badge/mysql-%2300f.svg?style=for-the-badge&logo=mysql&logoColor=white)

### A venir : 
![Solidity](https://img.shields.io/badge/Solidity-%23363636.svg?style=for-the-badge&logo=solidity&logoColor=white)
![C++](https://img.shields.io/badge/c++-%2300599C.svg?style=for-the-badge&logo=c%2B%2B&logoColor=white)
![Portfolio](https://img.shields.io/badge/Portfolio-%23000000.svg?style=for-the-badge&logo=firefox&logoColor=#FF7139)

### Comment me contacter ? 
<a href="mailto:jonascompper2@gmail.com">![Gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)
</a>
<a href="https://www.instagram.com/jonas.cppre/">![Instagram](https://img.shields.io/badge/Instagram-%23E4405F.svg?style=for-the-badge&logo=Instagram&logoColor=white)</a>

### Et si jamais :
<a href="https://paypal.me/RunaY0m0zuki">![PayPal](https://img.shields.io/badge/PayPal-00457C?style=for-the-badge&logo=paypal&logoColor=white)
</a>

### Amuse toi bien sur mon profil
