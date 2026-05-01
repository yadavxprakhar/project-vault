# Chess Game App

## 📌 Overview
A two-player chess game application built with vanilla JavaScript featuring a fully interactive chessboard, legal move validation, turn-based gameplay, and move history. Players take turns moving pieces using drag-and-drop or click-to-select mechanics, with the game enforcing standard chess rules including check, checkmate, and stalemate detection.

## ✨ Features
- Interactive 8x8 chessboard with all standard pieces
- Turn-based gameplay (White vs Black)
- Legal move validation (prevents illegal moves)
- Move history tracking with algebraic notation
- Capture detection and piece removal
- Check and checkmate detection
- Highlight valid moves when selecting a piece
- Game status indicator (whose turn, check, checkmate)
- Reset/New Game button
- Option to flip board perspective
- Save game state to LocalStorage (optional)
- Timer for each player (optional)
- Undo last move functionality (optional)

## 🛠️ Tech Stack
- **Frontend**: HTML5, CSS3, Vanilla JavaScript (ES6+)
- **Chess Logic**: [chess.js](https://github.com/jhlywa/chess.js) (lightweight chess library for move validation and game state)
- **Board UI**: [chessboard.js](https://chessboardjs.com/) or custom CSS Grid implementation
- **Styling**: CSS Grid/Flexbox for board layout, optional animations for piece movement
- **Storage**: LocalStorage for game history and saved games
- **Icons**: Unicode chess symbols (♔♕♖♗♘♙) or PNG/SVG piece images

## 📊 Difficulty Level
**Beginner** - Ideal for learning game state management, 2D array manipulation, and event handling. Using chess.js library handles complex rule validation, allowing focus on UI/UX and application logic rather than chess engine programming.

## 🎯 Expected Outcomes
After completing this project, you will:
- Master 2D array manipulation and grid-based game logic
- Understand game state management and turn-based systems
- Implement drag-and-drop or click-based movement mechanics
- Work with external JavaScript libraries (chess.js)
- Handle complex conditional logic (valid moves, check detection)
- Practice DOM manipulation and dynamic element creation
- Learn algebraic chess notation (e.g., e2-e4, Nf3)
- Implement undo/redo functionality using stack data structures
- Understand event delegation for dynamic board squares
- Create responsive layouts for game interfaces

## 🔥 Optional Enhancements
- **AI Opponent**: Integrate Stockfish.js or simple minimax algorithm for single-player mode
- **Move Sounds**: Add audio effects for piece movement, captures, and check
- **Animations**: Smooth piece movement transitions using CSS transforms
- **Pawn Promotion**: Modal to select piece (Queen, Rook, Bishop, Knight)
- **Castling & En Passant**: Visual indicators for special moves
- **Notation Display**: Professional-style move list sidebar (1. e4 e5 2. Nf3)
- **Export/Import**: Save games as PGN (Portable Game Notation) files
- **Online Multiplayer**: Add Socket.io for real-time two-player over network
- **Move Hints**: Highlight suggested moves for beginners
- **Themes**: Multiple board colors (wood, green, blue) and piece styles
- **Mobile Responsive**: Touch-friendly interface for phones/tablets
- **Opening Database**: Show popular openings as player makes moves

## 📸 Example/Demo
![Chess Game Preview](https://via.placeholder.com/800x400?text=Chess+Game+App+Preview)