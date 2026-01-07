# Tic Tac Toe Game

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A clean, interactive browser-based Tic Tac Toe game built with vanilla HTML, CSS, and JavaScript. Features a responsive design, smooth animations, and instant win detection.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Demo](#demo)
- [Getting Started](#getting-started)
- [Game Rules](#game-rules)
- [Project Structure](#project-structure)
- [Technologies Used](#technologies-used)
- [Code Explanation](#code-explanation)
- [Customization](#customization)
- [Browser Compatibility](#browser-compatibility)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Overview

This is a classic Tic Tac Toe game where two players take turns marking spaces in a 3×3 grid. The player who succeeds in placing three of their marks in a horizontal, vertical, or diagonal row wins the game. This implementation features a clean, responsive design with smooth animations and instant win detection.

## Features

- ✅ **Two-Player Gameplay**: Classic X vs O gameplay for two human players
- 🏆 **Win Detection**: Automatic detection of all 8 winning combinations
- 🤝 **Draw Detection**: Recognizes when the game ends in a tie
- 🔄 **Reset Functionality**: Quick reset button to start a new game
- 📱 **Responsive Design**: Works seamlessly on desktop, tablet, and mobile devices
- 🎨 **Visual Feedback**: Hover effects and clear game status messages
- 🖱️ **Click Prevention**: Prevents clicking on already filled cells
- 🎯 **Clean UI**: Simple, elegant interface with smooth interactions
- ⚡ **Fast Performance**: Lightweight and instant response
- 💻 **No Dependencies**: Pure vanilla JavaScript, no frameworks required

## Demo

### Game States

1. **Initial State**: Empty 3×3 grid ready for gameplay
2. **Playing**: Players alternate between X and O
3. **Win State**: Winner announced with message
4. **Draw State**: Tie game message displayed
5. **Reset**: Fresh board ready for new game

## Getting Started

### Prerequisites

All you need is a modern web browser:
- Chrome 60+ (recommended)
- Firefox 55+
- Safari 11+
- Edge 79+
- Opera 47+

### Installation

1. **Clone or download this repository**:
   ```bash
   git clone https://github.com/yourusername/tic-tac-toe.git
   cd tic-tac-toe
   ```

2. **Open `index.html` in your web browser**:
   ```bash
   # On macOS
   open index.html
   
   # On Windows
   start index.html
   
   # On Linux
   xdg-open index.html
   ```

### Alternative Methods

- **Double-click** the `index.html` file
- **Drag and drop** the file into your browser
- **Use a local development server** (recommended for development):
  ```bash
  # Using Python
  python -m http.server 8000
  
  # Using Node.js (http-server)
  npx http-server
  
  # Using VS Code Live Server extension
  Right-click index.html → Open with Live Server
  ```

### File Structure

Ensure all three files are in the same directory:
```
tic-tac-toe/
├── index.html      # Main HTML structure
├── styles.css      # Styling and layout
├── script.js       # Game logic and functionality
└── README.md       # Project documentation
```

## Game Rules

### Basic Rules

1. The game is played on a 3×3 grid
2. Player 1 is **X**, Player 2 is **O**
3. Players take turns placing their mark in empty squares
4. The first player to get 3 marks in a row wins (horizontal, vertical, or diagonal)
5. If all 9 squares are filled and no player has 3 in a row, the game is a **draw**
6. Click "Reset Game" to start a new game at any time

### Winning Combinations

There are **8 possible winning combinations**:

**Rows (Horizontal)**:
- Top row: [0, 1, 2]
- Middle row: [3, 4, 5]
- Bottom row: [6, 7, 8]

**Columns (Vertical)**:
- Left column: [0, 3, 6]
- Middle column: [1, 4, 7]
- Right column: [2, 5, 8]

**Diagonals**:
- Top-left to bottom-right: [0, 4, 8]
- Top-right to bottom-left: [2, 4, 6]

### Grid Layout

```
 0 | 1 | 2
-----------
 3 | 4 | 5
-----------
 6 | 7 | 8
```

## Project Structure

### index.html

The HTML file provides the structure:
- **Container**: Main wrapper for centered layout
- **Title**: "Tic Tac Toe" heading with underline
- **Board**: 3×3 grid with 9 clickable cells (data-index 0-8)
- **Reset Button**: Button to restart the game
- **Message**: Display area for win/draw announcements
- **Script**: Links to external JavaScript file

### styles.css

The CSS file includes:
- **Body Styling**: Centered flexbox layout with light gray background
- **Grid Layout**: CSS Grid for 3×3 board (100px cells with 5px gap)
- **Cell Styling**: White background, dark borders, centered text
- **Hover Effects**: Gray background on cell hover
- **Button Styling**: Red-themed button with rounded corners
- **Message Styling**: Large red text for game status
- **Typography**: Arial font, 2em font size for X and O marks

### script.js

The JavaScript file implements:
- **DOM Selection**: Selecting board, cells, message, and reset button
- **Game State**: Current player, game active status, board state array
- **Winning Conditions**: Array of 8 possible winning combinations
- **Event Handlers**: Click handlers for cells and reset button
- **Game Logic**:
  - `handleCellClick()`: Processes cell clicks and updates board
  - `checkResult()`: Checks for wins or draws
  - `resetGame()`: Resets game state and clears board
- **Player Switching**: Alternates between X and O

## Technologies Used

### Core Technologies

- **HTML5**: Semantic markup and structure
- **CSS3**: Styling, Grid layout, hover effects, and responsive design
- **JavaScript (ES6+)**: Game logic, DOM manipulation, and event handling

### Key Concepts Demonstrated

#### HTML
- Semantic HTML structure
- Data attributes (`data-index`)
- Event-driven architecture

#### CSS
- **CSS Grid**: For perfect 3×3 layout
- **Flexbox**: For centering and alignment
- **Hover Effects**: Visual feedback
- **Responsive Units**: Scalable design

#### JavaScript
- **DOM Manipulation**: `querySelector`, `querySelectorAll`
- **Event Listeners**: `addEventListener` for user interactions
- **Array Methods**: `includes()`, `forEach()`
- **Conditional Logic**: Win/draw detection
- **State Management**: Tracking game state
- **Template Literals**: For dynamic messages

## Code Explanation

### Game State Management

```javascript
let currentPlayer = 'X';           // Tracks current player (X or O)
let gameActive = true;             // Controls if game accepts moves
let gameState = ['', '', '', '', '', '', '', '', ''];  // Board state
```

### Win Detection Algorithm

```javascript
const winningConditions = [
    [0, 1, 2], [3, 4, 5], [6, 7, 8],  // Rows
    [0, 3, 6], [1, 4, 7], [2, 5, 8],  // Columns
    [0, 4, 8], [2, 4, 6]              // Diagonals
];

function checkResult() {
    for (let i = 0; i < winningConditions.length; i++) {
        const [a, b, c] = winningConditions[i];
        if (gameState[a] && gameState[a] === gameState[b] && gameState[a] === gameState[c]) {
            // Win detected
        }
    }
}
```

### Cell Click Logic

```javascript
function handleCellClick(event) {
    const clickedCellIndex = parseInt(event.target.getAttribute('data-index'));
    
    // Prevent clicking filled cells or inactive game
    if (gameState[clickedCellIndex] !== '' || !gameActive) {
        return;
    }
    
    // Update state and display
    gameState[clickedCellIndex] = currentPlayer;
    event.target.textContent = currentPlayer;
    
    checkResult();
}
```

## Customization

### Changing Colors

Edit `styles.css`:

```css
/* Background colors */
body {
    background-color: #yourColor;  /* Page background */
}

.cell {
    background-color: #yourColor;  /* Cell background */
    border: 2px solid #yourColor;  /* Cell borders */
}

.cell:hover {
    background-color: #yourColor;  /* Hover effect */
}

/* Button colors */
button {
    background-color: #yourColor;
    border: 2px solid #yourColor;
}

/* Message color */
#message {
    color: #yourColor;
}
```

### Changing Player Symbols

Modify the display in `script.js`:

```javascript
// Change from X/O to custom symbols
function handleCellClick(event) {
    // ...existing code...
    
    // Replace this line:
    clickedCell.textContent = currentPlayer;
    
    // With custom symbols:
    clickedCell.textContent = currentPlayer === 'X' ? '✕' : '○';
    // Or: clickedCell.textContent = currentPlayer === 'X' ? '🔴' : '🔵';
}
```

### Adjusting Cell Size

Edit `styles.css`:

```css
.board {
    grid-template-columns: repeat(3, 150px);  /* Larger cells */
    grid-template-rows: repeat(3, 150px);
    gap: 10px;  /* Larger gap */
}

.cell {
    width: 150px;
    height: 150px;
    font-size: 3em;  /* Larger symbols */
}
```

### Adding Sound Effects

1. **Add audio elements** to `index.html`:
   ```html
   <audio id="moveSound" src="move.mp3"></audio>
   <audio id="winSound" src="win.mp3"></audio>
   <audio id="drawSound" src="draw.mp3"></audio>
   ```

2. **Play sounds** in `script.js`:
   ```javascript
   function handleCellClick(event) {
       // ...existing code...
       document.getElementById('moveSound').play();
   }
   
   function checkResult() {
       if (roundWon) {
           document.getElementById('winSound').play();
       } else if (!gameState.includes('')) {
           document.getElementById('drawSound').play();
       }
   }
   ```

### Adding Animations

Add to `styles.css`:

```css
/* Fade-in animation for cells */
.cell {
    animation: fadeIn 0.3s ease-in;
}

@keyframes fadeIn {
    from { opacity: 0; transform: scale(0.8); }
    to { opacity: 1; transform: scale(1); }
}

/* Winning animation */
.cell.winner {
    background-color: #4caf50;
    animation: pulse 0.5s ease-in-out;
}

@keyframes pulse {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.1); }
}
```

### Highlighting Winning Line

Add to `script.js`:

```javascript
function checkResult() {
    for (let i = 0; i < winningConditions.length; i++) {
        const [a, b, c] = winningConditions[i];
        if (gameState[a] && gameState[a] === gameState[b] && gameState[a] === gameState[c]) {
            // Highlight winning cells
            cells[a].classList.add('winner');
            cells[b].classList.add('winner');
            cells[c].classList.add('winner');
            
            message.textContent = `Player ${currentPlayer} wins!`;
            gameActive = false;
            return;
        }
    }
}
```

### Creating a Larger Board (4×4)

1. **Update HTML** (add 7 more cells):
   ```html
   <div class="board">
       <!-- 16 cells total (0-15) -->
   </div>
   ```

2. **Update CSS**:
   ```css
   .board {
       grid-template-columns: repeat(4, 100px);
       grid-template-rows: repeat(4, 100px);
   }
   ```

3. **Update JavaScript**:
   ```javascript
   let gameState = Array(16).fill('');
   
   const winningConditions = [
       // Rows
       [0,1,2,3], [4,5,6,7], [8,9,10,11], [12,13,14,15],
       // Columns
       [0,4,8,12], [1,5,9,13], [2,6,10,14], [3,7,11,15],
       // Diagonals
       [0,5,10,15], [3,6,9,12]
   ];
   ```

## Browser Compatibility

### Fully Supported Browsers

| Browser | Minimum Version | Status | Notes |
|---------|----------------|---------|-------|
| Chrome | 60+ | ✅ Fully Supported | Best performance |
| Firefox | 55+ | ✅ Fully Supported | Excellent compatibility |
| Safari | 11+ | ✅ Fully Supported | iOS compatible |
| Edge | 79+ | ✅ Fully Supported | Chromium-based |
| Opera | 47+ | ✅ Fully Supported | Full feature support |

### Limited Support

| Browser | Version | Status | Issues |
|---------|---------|---------|--------|
| Internet Explorer | 11 | ⚠️ Limited | CSS Grid partial support |
| Safari | 10 | ⚠️ Limited | Some CSS features missing |

### Testing Recommendations

Test the game on:
- Desktop browsers (Chrome, Firefox, Safari)
- Mobile browsers (iOS Safari, Chrome Mobile)
- Tablet devices
- Different screen sizes using browser DevTools

```bash
# Chrome DevTools
F12 → Toggle Device Toolbar (Ctrl+Shift+M)
Test on: iPhone SE, iPad, Desktop
```

## Future Enhancements

### Planned Features

- [ ] **Single Player Mode (AI)**
  - Easy difficulty (random moves)
  - Medium difficulty (blocking strategy)
  - Hard difficulty (minimax algorithm)

- [ ] **Score Tracking**
  - Track wins for Player X and Player O
  - Display win/loss/draw statistics
  - Session-based scoreboard

- [ ] **Animations & Effects**
  - Winning line animation
  - Cell placement animations
  - Confetti effect for wins
  - Smooth transitions

- [ ] **Sound Effects**
  - Move placement sounds
  - Win celebration sound
  - Draw notification sound
  - Background music toggle

- [ ] **Visual Themes**
  - Dark mode / Light mode toggle
  - Color scheme selector
  - Custom player symbols
  - Animated backgrounds

- [ ] **Advanced Features**
  - Undo/Redo moves
  - Game history replay
  - Timer per move
  - Turn indicator
  - Player name customization

- [ ] **Multiplayer Options**
  - Local multiplayer (current)
  - Online multiplayer (WebSocket)
  - Room-based games
  - Chat functionality

- [ ] **Board Variations**
  - 4×4 grid (4 in a row to win)
  - 5×5 grid (5 in a row to win)
  - Ultimate Tic Tac Toe

- [ ] **Mobile Enhancements**
  - Touch gesture improvements
  - Haptic feedback
  - Progressive Web App (PWA)
  - Offline functionality

- [ ] **Accessibility**
  - Keyboard navigation
  - Screen reader support
  - High contrast mode
  - Focus indicators

## Contributing

Contributions are welcome! Here's how you can help:

### How to Contribute

1. **Fork the repository**
2. **Create a feature branch**:
   ```bash
   git checkout -b feature/AmazingFeature
   ```
3. **Commit your changes**:
   ```bash
   git commit -m "Add some AmazingFeature"
   ```
4. **Push to the branch**:
   ```bash
   git push origin feature/AmazingFeature
   ```
5. **Open a Pull Request**

### Contribution Guidelines

- **Code Style**: Follow existing JavaScript and CSS conventions
- **Testing**: Test across multiple browsers before submitting
- **Documentation**: Update README for new features
- **Commits**: Keep commits atomic and descriptive
- **Comments**: Add comments for complex logic
- **Responsive**: Ensure changes work on mobile devices

### Areas for Contribution

- Bug fixes and improvements
- New features from enhancement list
- Performance optimizations
- Accessibility improvements
- Documentation updates
- Test coverage
- UI/UX enhancements

## License

This project is licensed under the MIT License:

```
MIT License

Copyright (c) 2025

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## Acknowledgments

- Inspired by the classic Tic Tac Toe game
- Built as a learning project for web development fundamentals
- Thanks to the open-source community for inspiration

## Contact & Support

### Get Help

- **Issues**: [Report bugs or request features](https://github.com/yourusername/tic-tac-toe/issues)
- **Discussions**: [Ask questions or share ideas](https://github.com/yourusername/tic-tac-toe/discussions)
- **Email**: your.email@example.com

### Connect

- **GitHub**: [@yourusername](https://github.com/yourusername)
- **Portfolio**: [yourwebsite.com](https://yourwebsite.com)

---

<div align="center">

**Enjoy the game!** 🎮

Made with ❤️ by [Your Name]

⭐ Star this repo if you found it helpful!

[Report Bug](https://github.com/yourusername/tic-tac-toe/issues) · [Request Feature](https://github.com/yourusername/tic-tac-toe/issues) · [Documentation](https://github.com/yourusername/tic-tac-toe/wiki)

</div>