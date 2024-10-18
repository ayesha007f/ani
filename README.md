<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Stickman Dance</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="stage">
        <div class="stickman">
            <div class="head"></div>
            <div class="body"></div>
            <div class="left-arm"></div>
            <div class="right-arm"></div>
            <div class="left-leg"></div>
            <div class="right-leg"></div>
        </div>
    </div>

    <audio id="music" src="maps.mp3" autoplay loop></audio>
    
    <button onclick="startDance()">Start Dance</button>

    <script src="script.js"></script>
</body>
</html>
body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
    background-color: #f0f0f0;
    font-family: Arial, sans-serif;
}

.stage {
    width: 200px;
    height: 400px;
    background-color: #fff;
    position: relative;
}

.stickman {
    position: absolute;
    bottom: 20px;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    flex-direction: column;
    align-items: center;
}

.head {
    width: 50px;
    height: 50px;
    border: 5px solid black;
    border-radius: 50%;
}

.body {
    width: 5px;
    height: 100px;
    background-color: black;
}

.left-arm, .right-arm {
    width: 50px;
    height: 5px;
    background-color: black;
    position: absolute;
    top: 50px;
}

.left-arm {
    transform: rotate(-30deg);
    transform-origin: left;
}

.right-arm {
    transform: rotate(30deg);
    transform-origin: right;
}

.left-leg, .right-leg {
    width: 5px;
    height: 70px;
    background-color: black;
    position: absolute;
    bottom: 0;
}

.left-leg {
    transform: rotate(30deg);
    transform-origin: top;
}

.right-leg {
    transform: rotate(-30deg);
    transform-origin: top;
}
let stickman = document.querySelector('.stickman');

function startDance() {
    let music = document.getElementById('music');
    music.play();
    
    stickman.classList.add('dance');
}

setInterval(() => {
    let leftArm = document.querySelector('.left-arm');
    let rightArm = document.querySelector('.right-arm');
    let leftLeg = document.querySelector('.left-leg');
    let rightLeg = document.querySelector('.right-leg');
    
    // Arm Dance Animation
    leftArm.style.transform = leftArm.style.transform === 'rotate(-30deg)' ? 'rotate(-90deg)' : 'rotate(-30deg)';
    rightArm.style.transform = rightArm.style.transform === 'rotate(30deg)' ? 'rotate(90deg)' : 'rotate(30deg)';
    
    // Leg Dance Animation
    leftLeg.style.transform = leftLeg.style.transform === 'rotate(30deg)' ? 'rotate(70deg)' : 'rotate(30deg)';
    rightLeg.style.transform = rightLeg.style.transform === 'rotate(-30deg)' ? 'rotate(-70deg)' : 'rotate(-30deg)';
}, 500);  // Change 500 for faster/slower dancing

