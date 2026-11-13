# Asteroids

A recreation of the classic Asteroids arcade game built with Python and Pygame as part of a guided project on [Boot.dev](https://www.boot.dev/).

The goal is to survive by navigating a spaceship through an asteroid field, shooting asteroids, and avoiding collisions.

This project helped me practice object-oriented programming, game loops, collision detection, and working with the Pygame library.

## Features

- Player-controlled spaceship with movement and rotation
- Shooting mechanics with a cooldown between shots
- Randomly spawning asteroids
- Asteroids that split into smaller, faster asteroids when shot
- Collision detection between the player, asteroids, and projectiles
- Game over when the player collides with an asteroid
- Frame-independent movement using delta time

## Controls

| Key | Action |
|-----|--------|
| W | Move forward |
| S | Move backward |
| A | Rotate left |
| D | Rotate right |
| Space | Shoot |

## Built With

- **Python** - Programming language
- **Pygame** - Game development library
- **uv** - Python dependency and project management

## Getting Started

### Prerequisites

Make sure you have Python and [uv](https://docs.astral.sh/uv/) installed.

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/DerekWEmerson/Asteroids.git
   ```

2. Navigate into the project directory:

   ```bash
   cd YOUR_REPOSITORY
   ```

3. Install dependencies:

   ```bash
   uv sync
   ```

4. Run the game:

   ```bash
   uv run main.py
   ```

## How the Game Works

### Player Movement

The player controls a triangular spaceship that can rotate and move forward or backward.

Movement uses Pygame's `Vector2` class to calculate direction based on the ship's rotation.

### Shooting

Pressing Space creates a projectile that travels in the direction the spaceship is facing.

A 0.3-second cooldown limits how frequently the player can shoot.

### Asteroid Spawning

Asteroids spawn from random edges of the screen approximately every 0.8 seconds.

Each asteroid is assigned a random size, speed, and direction.

### Asteroid Splitting

When a projectile hits an asteroid:

1. The asteroid is destroyed.
2. If it is larger than the minimum radius, two smaller asteroids are created.
3. The new asteroids travel in different directions at 1.2 times the original speed.
4. Asteroids at the minimum radius disappear when shot.

### Collision Detection

The game checks for collisions between asteroids, the player, and projectiles.

If an asteroid collides with the player, the game ends and prints "Game over!" in the terminal.

## Project Structure

```text
asteroids/
├── main.py            # Main game loop and collision handling
├── player.py          # Player movement, rotation, and shooting
├── asteroid.py        # Asteroid movement and splitting
├── asteroidfield.py   # Random asteroid spawning
├── shot.py            # Projectile behavior
├── circleshape.py     # Base class for circular game objects
├── constants.py       # Game settings and configuration
├── logger.py          # Game event logging
├── pyproject.toml     # Project configuration and dependencies
├── uv.lock            # Dependency lockfile
└── README.md          # Project documentation
```

## What I Learned

Through this project, I practiced:

- **Object-oriented programming:** Using classes and inheritance to organize game objects.
- **Game loops:** Updating and drawing objects continuously using Pygame.
- **Vector mathematics:** Using vectors for movement, rotation, and projectile direction.
- **Collision detection:** Handling interactions between game objects.
- **Sprite groups:** Organizing game objects for updating, drawing, and collision checking.
- **Delta time:** Keeping movement consistent regardless of frame rate.
- **Project organization:** Separating game logic into multiple Python modules.

## Acknowledgments

This project was completed as part of the guided Asteroids project on [Boot.dev](https://www.boot.dev/).

Thanks to Boot.dev for providing the project instructions and learning resources.
