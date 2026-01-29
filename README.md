# Assignment 1

Make changes to theCodeBase: [text](https://gitlab.com/csteach323-488/source/-/tree/master/week1/examples/01-intro-arcade)


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
- Restructure project directories: src/ data/ assets/ tests/
- Added player lives (3) and a lost-life pause state 
- Reset player, enemies, and coin positions after a life is lost
- Paused enemy movement during the lost-life pause

## Playtest Notes
- Lives count correctly decrements and resets on game restart
- Enemies and coins reposition reset after life lost
- Pause after a life is lost , prompt a message and waits for Enter to continue or quit

## Tuning Log (3 changes)
 1) player Lives: 
        Before: only one attempt
        After : 3 attempts 
        Effect: Make the game more forgiving 
 2) Lost Life pause:
        Before: game goes to the end directly and started over again
        After : Pause prompt, players and coin reset
        Effect: give player a chance to continue after collision, brake before the next attempt
3) Enemy position reset after loosing a life:
    Before: continue from the last collision positions
    After : positions reset randomly 
    Effect: prevent unfair collision upon start 

## Scope Note 
- This week’s version includes: one level with 3 attempts instead of unfair instant death leads to the end of the game
- Out of scope: Improve UI. However, requires focusing more on the interface, but currently the game still lacks  meaningful logic to be reflected on the interface
- Next player experience goal: and add Levels to make the game more exciting and harder as player evolve into higher levels.
# COMP488-A2