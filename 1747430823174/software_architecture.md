# Software Architecture Document for Full-Screen Pong Game

## 1. Introduction
This document outlines the simple and easy-to-implement software architecture for the Full-Screen Pong Game as specified in the Product Requirements Document (PRD). The game will be developed using modern web technologies focusing solely on the frontend, utilizing the HTML5 Canvas API for rendering and local storage for any required data persistence.

## 2. System Overview
The Full-Screen Pong Game will feature:
- A full-screen experience with a black background.
- Two-player controls using keyboard inputs.
- A minimalistic user interface with a start screen, instructions, and game display.
- Local storage to remember the last configured winning score.

## 3. Architecture Components

### 3.1 Technology Stack
- **Frontend**: HTML5, CSS3, JavaScript
- **Canvas API**: Used for rendering the game graphics
- **Local Storage API**: Used to persist game settings like winning score

### 3.2 Application Structure
- **HTML Structure**:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pong Game</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div id="start-screen">
        <h1>Pong</h1>
        <button id="play-button">Play</button>
        <button id="instructions-button">Instructions</button>
    </div>
    <canvas id="game-canvas"></canvas>
    <div id="end-screen">
        <h2 id="winner"></h2>
        <button id="play-again-button">Play Again</button>
    </div>
    <div id="instructions">
        <h2>Instructions</h2>
        <p>Player 1: W (up), S (down)</p>
        <p>Player 2: ↑ (up), ↓ (down)</p>
        <button id="back-to-start-button">Back to Start</button>
    </div>
    <script src="script.js"></script>
</body>
</html>
```

- **CSS Styles** (`styles.css`):
```css
body {
    margin: 0;
    background-color: black;
    color: white;
    font-family: Arial, sans-serif;
}
#game-canvas {
    display: none; /* Hidden by default */
}
#start-screen, #end-screen, #instructions {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
}
```

### 3.3 Game Logic
- **Game States**:
  - Start Screen
  - Gameplay
  - End Screen
  - Instructions

- **Main JavaScript Functionality** (`script.js`):
  - Declare global variables for canvas, paddles, ball, scores, and control keys.
  - Initialize the game state and handle rendering through the Canvas API.
  - Control the paddles based on keypress events.
  - Implement the game loop using `requestAnimationFrame` for smooth rendering (targeting 60 FPS).
  - Show scores and manage game states (winning conditions and transitions).

#### Pseudocode Example for Game Loop:
```javascript
function gameLoop() {
    // Clear canvas
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    
    // Update game state
    updatePaddles();
    updateBall();
    checkCollision();
    drawGameElements();
    
    // Request next frame
    requestAnimationFrame(gameLoop);
}
```

### 3.4 Local Storage Feature
- Capture the winning score and persist it using local storage.
- Implement a function to retrieve and store player preferences at the start.
```javascript
function setWinningScore(score) {
    localStorage.setItem('winningScore', score);
}

function getWinningScore() {
    return parseInt(localStorage.getItem('winningScore')) || 5; // Default score is 5
}
```

## 4. User Interface
- Use modal dialogues or overlays for the instructions and results, maintaining a focus on gameplay.
- Ensure clear visibility of paddles and score against the black background.

## 5. Testing Strategy
- Implement basic unit tests for each game component using the browser's console for logging.
- Perform manual testing during development and user acceptance testing (UAT) with casual gamers.

## 6. Conclusion
This architecture outlines a straightforward and effective approach to developing the Full-Screen Pong Game, focusing on the core requirements for user engagement, functionality, and maintainability. By following this architecture, the development team can deliver a nostalgic gaming experience while ensuring ease of implementation and overall clarity.

By utilizing the Canvas API, local storage, and clean coding practices, this architecture provides a solid foundation to build an interactive and enjoyable game for the target audience.