# Frozen-Bubble: SDL2
<p align="center">
  <img src="https://github.com/user-attachments/assets/c68db5c9-7e72-4d19-8e98-c598a3f5e54e">
</p>

A C++ / SDL2 port of the classic [Frozen Bubble 2](http://www.frozen-bubble.org/), reimplementing its gameplay, network multiplayer, and chain reaction system. Targets desktop (Linux/macOS/Windows), Android TV, and WebAssembly.

---

## Game Modes

### Single Player
Classic Frozen Bubble gameplay — 100 levels, scoring, chain reactions.

### 2-Player Local
Two players on the same keyboard:
- Player 1: Arrow keys + Up to fire
- Player 2: C/X/V + D to fire

### Network Multiplayer (2–5 players)
Play over LAN or internet using the included server. Supports chain reactions, malus (attack bubbles), win tracking, and 3–5 player layouts.

---

## Building

**Dependencies:**
- SDL2, SDL2_image, SDL2_mixer, SDL2_ttf
- [iniparser](https://github.com/ndevilla/iniparser)
- CMake 3.16+

```bash
cmake -B build
cmake --build build
```

The server binary (`fb-server`) is built automatically on Linux and macOS.

---

## Running a Server

```bash
./start-server.sh          # Start on default port 1511
./start-server.sh -p 1234  # Custom port
./start-server.sh -d       # Debug output
```

`start-server.sh` enables both TCP (direct connections) and UDP broadcast (LAN auto-discovery) by default.

---

## Network Play Quick Start

**Host:**
1. Start the server: `./start-server.sh`
2. Launch the game → **LAN Game** (auto-discovers) or **Net Game** (enter IP)
3. Create a game room and wait for players

**Join:**
1. Launch the game → **LAN Game** to auto-discover on your network
2. Or **Net Game** → enter the host's IP

Any player pressing Enter after a round ends automatically starts the next round for everyone.

---

## Public Server List

Community servers are listed in [`serverlist-1`](serverlist-1) — same format as the original `frozen-bubble.org` server list:

```
# host port
myserver.example.com 1511
```

Submit a PR to add your server. The game fetches this list automatically on startup.

---

## Android TV

See [`android/SETUP.md`](android/SETUP.md) for build instructions.

Controller mapping:

| Button | Action |
|---|---|
| D-pad Left/Right | Aim |
| A | Fire / Select |
| B | Back |
| Start | Pause |

---

## Credits

Original Frozen Bubble by [Glenn Sanson et al.](http://www.frozen-bubble.org/) — GPL licensed.
This port is independently developed and not affiliated with the original project.
