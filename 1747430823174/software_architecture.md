# Software Architecture Document for Full-Screen Tetris Game

## 1. Introduction
This document outlines the software architecture for the full-screen Tetris game as per the product requirements document. The focus is on a simple, single-page frontend application that utilizes the Local Storage API for data persistence.

## 2. Architecture Overview
The architecture consists of a single-page web application built with HTML5, CSS3, and JavaScript. The game will utilize the Phaser.js framework for canvas rendering and game management. Local Storage is used to store player scores and settings.

### Technology Stack:
- **Frontend**: HTML5, CSS3, JavaScript
- **Game Framework**: Phaser.js
- **Data Storage**: Local Storage API in the browser

## 3. Components

### 3.1 Game Engine (Phaser.js)
- **Rendering**: Handle the rendering of game graphics, including Tetris pieces and backgrounds.
- **Game Mechanics**: Manage gameplay, including piece movement, rotation, collision detection, and line-clearing logic.

### 3.2 User Interface
- **HTML/CSS Layout**: Structures the layout for the game, including HUD elements such as score, level display, and next piece preview.
- **Responsive Design**: Use media queries to adapt to various screen sizes ensuring full-screen capability.

### 3.3 Game Modes
- Implement three modes: Classic, Timed, and Endless.
- Each mode will have customized gameplay logic, utilizing the core mechanics of Tetris.

### 3.4 Scoring System
- Create a function to calculate scores based on lines cleared and maintain the current game score.
- Use Local Storage to persist high scores and retrieve them when the game loads.

### 3.5 Audio Management
- Manage background music and sound effects through HTML5 Audio API.
- Include options in the settings menu to mute or adjust audio levels.

### 3.6 Local Storage Management
- **High Score Management**: Store and retrieve high scores within the Local Storage.
- Implement functions to save player scores when a game ends, and retrieve them for display on the high score leaderboard.

## 4. Game Flow
1. **Start Screen**: 
   - Display “Play”, “Instructions”, and “High Scores”.
   - Button handlers trigger the game initialization or show game instructions.
   
2. **Game Initialization**: 
   - Start the game loop using Phaser.js.
   - Load and prepare assets including Tetris pieces and audio files.

3. **Gameplay Loop**: 
   - Handle user inputs for controls (arrow keys / swipe gestures).
   - Update game state through the game engine (piece falling, line-clearing).
   - Incorporate scoring calculations and high score storage.

4. **Game Over Screen**: 
   - Display final score, options to “Restart” or “Exit”.
   - Trigger necessary functions to save the score in Local Storage.

## 5. User Interface Organization
- **Score Display**: Located at the top with dynamic updates during play.
- **Next Piece Preview**: Positioned to provide visual feedback on upcoming pieces.
- **Level Indicator**: Updates as players reach higher levels within the game.

## 6. Responsiveness and Accessibility
- Use flexible layouts and adaptable canvas sizes.
- Include options for color blindness (different shapes or patterns on pieces) to enhance accessibility.

## 7. Performance Optimization
- Ensure smooth rendering by limiting the complexity of graphics.
- Use sprite sheets for Tetris pieces to improve loading times and performance.

## 8. Milestones
- Week 1-2: UI Design and Initial Game Functionality Development
- Week 3-5: Core Game Mechanics and Gameplay Testing
- Week 6: Integration of Audio Elements and Performance Tuning
- Week 7: Deployment of High Score Functionality
- Week 8: Final Testing and Bug Fixing

## 9. Conclusion
This architecture document provides a clear, structured approach to developing a full-screen Tetris game using frontend technologies. By adhering to the outlined components and ensuring data persistence using Local Storage, the development team can create an engaging, well-performing game for a wide audience, fulfilling all product requirements outlined in the PRD.