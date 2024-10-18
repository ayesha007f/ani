<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Stickman Dance</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>Stickman Dance</h1>
    <div id="stickman">
        <div class="head"></div>
        <div class="body"></div>
        <div class="left-arm"></div>
        <div class="right-arm"></div>
        <div class="left-leg"></div>
        <div class="right-leg"></div>
    </div>
</body>
</html>
body {
    text-align: center;
    background-color: #f0f0f0;
    font-family: Arial, sans-serif;
}

#stickman {
    position: relative;
    width: 60px;
    height: 150px;
    margin: 50px auto;
}

.head {
    width: 30px;
    height: 30px;
    border: 3px solid black;
    border-radius: 50%;
    position: absolute;
    top: 0;
    left: 15px;
}

.body {
    width: 6px;
    height: 60px;
    background-color: black;
    position: absolute;
    top: 30px;
    left: 27px;
}

.left-arm, .right-arm {
    width: 50px;
    height: 6px;
    background-color: black;
    position: absolute;
    top: 35px;
}

.left-arm {
    transform-origin: right;
    left: -50px;
}

.right-arm {
    transform-origin: left;
    right: -50px;
}

.left-leg, .right-leg {
    width: 6px;
    height: 50px;
    background-color: black;
    position: absolute;
    top: 90px;
}

.left-leg {
    transform-origin: top right;
    left: 10px;
}

.right-leg {
    transform-origin: top left;
    right: 10px;
}

/* Keyframes for dancing animation */
@keyframes danceMove {
    0%, 100% {
        transform: rotate(0);
    }
    25% {
        transform: rotate(20deg);
    }
    50% {
        transform: rotate(-20deg);
    }
    75% {
        transform: rotate(20deg);
    }
}

/* Animate arms and legs */
.left-arm, .right-arm, .left-leg, .right-leg {
    animation: danceMove 1s infinite;
}
