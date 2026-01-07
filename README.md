# Tic Tac Toe Game

A clean and interactive browser-based Tic Tac Toe game built with HTML, CSS, and JavaScript.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Getting Started](#getting-started)
- [Game Rules](#game-rules)
- [Project Structure](#project-structure)
- [Technologies Used](#technologies-used)
- [Customization](#customization)
- [Browser Compatibility](#browser-compatibility)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [License](#license)

## Overview

This is a classic Tic Tac Toe game where two players take turns marking spaces in a 3×3 grid. The player who succeeds in placing three of their marks in a horizontal, vertical, or diagonal row wins the game. This implementation features a clean, responsive design with smooth animations and instant win detection.

## Features

- **Two-Player Gameplay**: Classic X vs O gameplay for two human players
- **Win Detection**: Automatic detection of winning combinations
- **Draw Detection**: Recognizes when the game ends in a tie
- **Reset Functionality**: Quick reset button to start a new game
- **Responsive Design**: Works seamlessly on desktop, tablet, and mobile devices
- **Visual Feedback**: Clear indication of current player and game status
- **Clean UI**: Simple, elegant interface with smooth interactions

## Getting Started

### Prerequisites

All you need is a modern web browser:
- Chrome (recommended)
- Firefox
- Safari
- Edge

### Installation

1. Clone or download this repository:
```bash
git clone https://github.com/yourusername/tic-tac-toe.git
cd tic-tac-toe
```

2. Open `index.html` in your web browser:
```bash
# On Mac
open index.html

# On Windows
start index.html

# On Linux
xdg-open index.html
```

Alternatively, you can:
- Double-click the `index.html` file
- Drag and drop the file into your browser
- Use a local development server (like Live Server in VS Code)

### File Structure

Ensure all three files are in the same directory:
```
tic-tac-toe/
├── index.html      # Main HTML structure
├── styles.css      # Styling and layout
└── script.js       # Game logic
```

## Game Rules

1. The game is played on a 3×3 grid
2. Player 1 is X, Player 2 is O
3. Players take turns placing their mark in empty squares
4. The first player to get 3 marks in a row (horizontally, vertically, or diagonally) wins
5. If all 9 squares are filled and no player has 3 in a row, the game is a draw
6. Click "Reset Game" to start a new game at any time

### Winning Combinations

There are 8 possible winning combinations:
- **Rows**: (0,1,2), (3,4,5), (6,7,8)
- **Columns**: (0,3,6), (1,4,7), (2,5,8)
- **Diagonals**: (0,4,8), (2,4,6)

## Project Structure

### index.html

The HTML file provides the structure:
```html
- Container for the game
- Title header
- 3×3 game board (9 cells)
- Reset button
- Message display area
```

### styles.css (Expected)

The CSS file should include:
```css
- Layout and grid styling
- Cell hover effects
- Color scheme
- Typography
- Responsive design rules
- Button styling
- Win/draw message styling
```

### script.js (Expected)

The JavaScript file should implement:
```javascript
- Game state management
- Player turn logic
- Click event handlers
- Win condition checking
- Draw condition checking
- Board reset functionality
- Message display updates
```

## Technologies Used

- **HTML5**: Semantic markup and structure
- **CSS3**: Styling, layout, and responsive design
- **JavaScript (ES6+)**: Game logic and interactivity

### Key Concepts

- **DOM Manipulation**: Direct interaction with HTML elements
- **Event Listeners**: Handling user clicks and interactions
- **Array Methods**: Managing game state and checking win conditions
- **Conditional Logic**: Determining game outcomes
- **CSS Grid/Flexbox**: Creating responsive layouts

## Customization

### Changing Colors

Edit `styles.css` to customize the color scheme:
```css
/* Primary colors */
--primary-color: #your-color;
--secondary-color: #your-color;
--background-color: #your-color;

/* Player colors */
--player-x-color: #your-color;
--player-o-color: #your-color;
```

### Changing Player Symbols

Modify `script.js` to use different symbols:
```javascript
const PLAYER_X = '✕';  // Change to any character
const PLAYER_O = '○';  // Change to any character
```

### Adding Sound Effects

Add audio elements to `index.html`:
```html
<audio id="moveSound" src="move.mp3"></audio>
<audio id="winSound" src="win.mp3"></audio>
```

Play sounds in `script.js`:
```javascript
document.getElementById('moveSound').play();
```

### Board Size

To change the board size, you'll need to:
1. Add/remove cells in `index.html`
2. Update CSS grid in `styles.css`
3. Modify win conditions in `script.js`

## Browser Compatibility

| Browser | Minimum Version | Status |
|---------|----------------|---------|
| Chrome | 60+ | ✅ Fully Supported |
| Firefox | 55+ | ✅ Fully Supported |
| Safari | 11+ | ✅ Fully Supported |
| Edge | 79+ | ✅ Fully Supported |
| Opera | 47+ | ✅ Fully Supported |
| IE | 11 | ⚠️ Limited Support |

## Future Enhancements

Potential features to add:

- [ ] **Single Player Mode**: Play against AI with difficulty levels
- [ ] **Score Tracking**: Keep track of wins, losses, and draws
- [ ] **Animations**: Add winning line animations
- [ ] **Sound Effects**: Audio feedback for moves and wins
- [ ] **Themes**: Multiple color themes or dark mode
- [ ] **Online Multiplayer**: Play with friends over the internet
- [ ] **Game History**: Undo/redo moves
- [ ] **Timer**: Add time limits per move
- [ ] **Larger Boards**: Support for 4×4 or 5×5 grids
- [ ] **Achievements**: Unlock badges for winning streaks

## Development

### Setting Up Development Environment

1. Install a code editor (VS Code recommended)
2. Install a local development server:
```bash
npm install -g live-server
```

3. Run the development server:
```bash
live-server
```

### Code Structure Best Practices

```javascript
// Game State
const gameState = {
    board: Array(9).fill(null),
    currentPlayer: 'X',
    gameActive: true
};

// Separate concerns
function handleCellClick(event) { }
function checkWinner() { }
function resetGame() { }
function updateDisplay() { }
```

## Contributing

Contributions are welcome! Here's how you can help:

1. Fork the repository
2. Create a feature branch:
```bash
git checkout -b feature/YourFeature
```

3. Commit your changes:
```bash
git commit -m "Add YourFeature"
```

4. Push to the branch:
```bash
git push origin feature/YourFeature
```

5. Open a Pull Request

### Contribution Guidelines

- Follow existing code style
- Test thoroughly across browsers
- Update documentation for new features
- Keep commits focused and descriptive

## License

This project is licensed under the MIT License - see below for details:

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

## Contact & Support

- **Issues**: Report bugs or request features via GitHub Issues
- **Questions**: Open a discussion in the repository
- **Email**: your.email@example.com

---

**Enjoy the game!** 🎮