# Assignment 2

Update Assignment one, by adding a level and world object


## 
- Pygame setup: window, clock, main loop
- Events + input handling
- Game state: title → playing → game over
- Update/draw separation and delta time (`dt`)
- Simple collision using `pygame.Rect`
- Score + high score saved to `save.json`

## Run

```bash
python -m pip install pygame
python main.py
```

## Controls
- Arrow keys / WASD: move
- Enter: start / restart
- Esc: quit

## Save data
Writes `data/save.json` (high score only). Delete it to reset.

## Changes:
- Added levels: Collecting 5 coins now increases the level and spawns an extra enemy.
- Added slow zone object: A new world object slows the player down whenever they step inside it.
- Adjusted movement inside slow zone: Player speed drops from 360 to 160 while in the zone to create a simple risk–reward tradeoff.


## Decision‑Change
- Slow Zone (new world object)
* What it does: When the player steps into the slow zone, their movement speed drops.  
* Why it matters: It makes the player think about their path so they don’t get stuck or caught by enemies while moving slower.  
* What the player learns: It introduces a simple risk/reward idea, going through the zone might help with collecting coins, but it also makes escaping enemies harder.

- New Level 
* What it does: After the player collects a certain number of coins (5), the game levels up and spawns an extra enemy.  
* Why it matters: It pushes the player to keep collecting coins while dealing with the game getting harder over time.  
* What the player learns: Difficulty ramps up gradually, so players learn how to handle more enemies as levels increase.

- Slow Zone location and Color Change per Level
* What it does: The slow zone changes location and color every time the level increases.  
* Why it matters: It gives a clear visual sign that the level changed or that the hazard is getting more serious.  
* What the player learns: Players start recognizing the hazard by color and can predict how it will affect their movement.


## Scope Note 
- This week focuses on the core arcade basics: clean movement, simple collisions, and a light progression system. Enemy behavior and level layouts stay simple so the game stays clear, fair, and easy to read during play.
- Player experience goal: tense, but always understandable.
