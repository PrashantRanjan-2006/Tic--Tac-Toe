# Tic--Tac-Toe

A browser-based **Tic Tac Toe** project with multiple play modes:

- **Two Player (local)** on the same device
- **Play vs Computer** with difficulty levels (`easy`, `medium`, `hard`)
- **Online Multiplayer** using Socket.IO matchmaking

The project combines a static frontend (HTML/CSS/JavaScript) with a lightweight Node.js server for multiplayer support.

---

## Features

- Classic 3×3 Tic Tac Toe board
- Turn-based gameplay with clear turn indicators
- Win detection (rows, columns, diagonals)
- Draw/tie detection
- Reset/replay controls
- Difficulty selection for AI mode:
  - Easy (random moves)
  - Medium (basic win/block logic)
  - Hard (minimax-based move selection)
- Real-time online matchmaking and move sync (Socket.IO)
- Responsive UI with animations, sounds, and confetti effects

---

## Tech Stack

### Frontend

- HTML5
- CSS3
- Vanilla JavaScript

### Backend

- Node.js
- Express
- Socket.IO

---

## Repository Structure

This repository contains:

- `README.md` (this file)
- `Tic-Tac-Toe-master/` (main application source)

Inside `Tic-Tac-Toe-master/`:

```text
Tic-Tac-Toe-master/
├── index.js                    # Express + Socket.IO server
├── package.json                # Node scripts and dependencies
├── html/
│   ├── index.html              # Landing page (mode selection)
│   ├── twoPlayer.html          # Local two-player mode
│   ├── computer.html           # Player vs computer mode
│   ├── multiplayer.html        # Online multiplayer mode
│   └── assets/
│       ├── script/             # Game/client logic
│       ├── style/              # CSS styles
│       ├── img/                # Logo/assets
│       └── tune/               # Sound effects/music
└── readme.md                   # Original project-level readme
```

---

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (recommended: current LTS)
- npm (comes with Node.js)

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/PrashantRanjan-2006/Tic--Tac-Toe.git
   ```

2. Move into the project app directory:

   ```bash
   cd Tic--Tac-Toe/Tic-Tac-Toe-master
   ```

3. Install dependencies:

   ```bash
   npm install
   ```

### Run the App

Start the server:

```bash
npm start
```

Open your browser and visit:

```text
http://localhost:3000
```

---

## Game Modes

### 1) Two Player (Local)

- Two users play on the same screen.
- X starts first, then O alternates.
- Game ends on win or tie, with reset available.

### 2) Play Against Computer

- Human player is X, computer is O.
- Select one difficulty level:
  - **Easy**: random available move
  - **Medium**: tries to win, otherwise blocks player
  - **Hard**: minimax strategy

### 3) Online Multiplayer

- Enter a name and join matchmaking.
- Server pairs two waiting players in real time.
- Moves are synchronized through Socket.IO events.
- If opponent disconnects mid-game, remaining player is declared winner.

---

## How to Play

1. Open the app and choose a mode.
2. Click/tap an empty cell to place your mark.
3. First to align 3 marks horizontally, vertically, or diagonally wins.
4. If all cells fill without a winner, match is a draw.
5. Use reset/lobby options to start again.

---

## Available npm Scripts

From `Tic-Tac-Toe-master/`:

- `npm start` — starts the Express/Socket.IO server (`index.js`)
- `npm test` — placeholder script (currently returns “no test specified”)

---

## Multiplayer Event Flow (High Level)

Server (`index.js`) handles:

- `new-player` → queues or matches players
- `player-move` → forwards move to opponent
- `disconnect` → notifies opponent and updates waiting state

Client-side networking is implemented in:

- `html/assets/script/client.js`
- `html/assets/script/multiplayer.js`

---

## Contributing

Contributions are welcome.

1. Fork this repository
2. Create a feature branch:

   ```bash
   git checkout -b feature/your-feature
   ```

3. Commit your changes:

   ```bash
   git commit -m "Add your feature"
   ```

4. Push your branch and open a Pull Request

---

## License

No root-level license file is currently included in this repository.

If you want clear usage terms, add a `LICENSE` file (for example, MIT).
