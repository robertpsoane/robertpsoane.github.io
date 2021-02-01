---
layout: project
title: "Othello (GUI)"
subtitle: "This side project was to produce a fully functional GUI Othello engine. This was initially set as a challenge during an MSc tutorial to produce an Othello engine using minimax. I built a working engine (initially in the command line) and have since produced a GUI for it." # This forms the basis of a description of the project
date: 2020-12-02 13:14:13 -0000

githuburl: "https://github.com/robertpsoane/Othello/"

project-img: '/img/projects/Othello/othello_gui.png'
---


This side project was to produce a fully functional GUI Othello engine. This was initially set as a challenge during an MSc tutorial to produce an Othello engine using minimax. I built a working engine (initially in the command line) and have since produced a GUI for it.

When I redesigned it using a GUI, I decided to attempt to implement MVC, as a way of learning MVC. This could also make it easier to further extend the game in future.

## How To Play
The aim and of the game is simple - to have the most discs of your colour on the board at the end of the game.
The rules are also relatively simple.  On your turn you can play one disc on any square which is adjacent to an opponents disc, providing it is possible to 'draw a straight line' between your disc, and another of your discs, with all squares inbetween the two discs of your colour occupied by your opponents colour.

### Tactics
While this sounds relatively simple, there are some general strategy points worth considering:
- The corners are the strongest positions, as they cannot be taken.  If you can place a piece on a corner, do so.
- The next strongest positions are the squares along the edges.
- Avoid placing any pieces one step in from a corner if you can help it, as this often makes it easier for your opponents to claim the corner
- Try to minimise the number of moves your opponent can make, while maximising the number of moves you can make.

### Game Modes
This game comes with 3 game modes:
- Play as Black: Play as black against the computer playing as white
- Play as White: Play as white against the computer playing as black
- Play PvP: Two players playing at the same board at the same computer

## The engine
The engine is playing using a minimax strategy (currently set at depth 5).
It attempts to follow the tactics listed above.  It does this by minimising future moves for its opponent, while maximising them for itself, then applying a points-based grading strategy to the board for each leaf of the tree.
The grading strategy is as follows:
```
[   [10, -2, 2, 2, 2, 2, -2, 10],
    [-2, -2, 1, 1, 1, 1, 1, -2],
    [2, 1, 1, 1, 1, 1, 1, 2],
    [2, 1, 1, 1, 1, 1, 1, 2],
    [2, 1, 1, 1, 1, 1, 1, 2],
    [2, 1, 1, 1, 1, 1, 1, 2],
    [-2, -2, 1, 1, 1, 1, -2, -2],
    [10, -2, 2, 2, 2, 2, -2, 10]]
```
    
The points are centered around 0, with a positive score meaning the engine has
the advantage, and a negative score meaning the player has an advantage.
