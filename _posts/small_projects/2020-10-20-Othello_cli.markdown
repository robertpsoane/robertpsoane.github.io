---
layout: project
title: "Othello (CLI)"
subtitle: "A working Othello player using a Mini Max algorithm with Alpha Beta pruning.  Written as a weekend project after a discussion about minimax algorithms at uni.." # This forms the basis of a description of the project
date: 2020-10-20 13:14:13 -0000

githuburl: "https://github.com/robertpsoane/othello-cli/"

project-img: '/img/projects/Othello/othello-cli.jpg'
---

I built this simple Othello game with a mini-max 'AI' player after a conversation with a lecturer about the algorithm.  It is text based, and has a very basic, very simple interface, however it seems relatively good at beating me at 8x8 or 6x6 Othello.  That said, I have no experience playing Othello so that isn't necessarily a great achievement.

Some future improvements which could be made include:
- A GUI
- Difficulty levels for the 'AI'
- Refactoring the code - it was very much hacked together in a couple of days, and I do not claim for one minute that the code is any good.  If I take this further I would definitely give it a re-write.  I would probably use OOP, and structure it in a way that I could set 2 'AI's against each other if I wanted.

This project is complete and has been replaced by a GUI project using pygame.

## Play

Game can be played in 8x8 and 6x6 mode.  6x6 is faster.  Simply change the line `DIMS = ` (line 40 in the code) between 6 and 8 to change the board size.

Basic Welcome Screen:
```
Welcome to Othello.  Please select an option:
A - Play against the computer
B - Play against a friend
Q - Quit Game
```

Board and move selection screen for the 6x6 game.
```
Black's turn:
  A B C D E F
1 . . . . . .
2 . . . . . .
3 . . b w . .
4 . . w b . .
5 . . . . . .
6 . . . . . .
Please input a move in the following form: A1, or P for pass
```
Note, the game is not case sensitive.

## Play vs Computer
- Computer uses minimax algorithm to play the game.
- Currently scored based on number of available moves, with a weighting given to certain squares:
```
def scoreBoard(board, player, opponent):
    player_score = len(generateMoveList(board, player, opponent))*3
    opponent_score = len(generateMoveList(board, opponent, player))*3

    if (player_score == 0) and (opponent_score == 0):
        # Have reached game end
        winner = decideWinner(board)
        winner = winner[0]
        if winner[0].lower() == player:
            return 300
        elif winner[0].lower == opponent:
            return -300
        else:
            return 0

    for i in range(DIMS):
        for j in range(DIMS):
            if board[i][j] == player:
                player_score += GRADING_STRATEGY[i][j]
            if board[i][j] == opponent:
                opponent_score += GRADING_STRATEGY[i][j]

    return player_score - opponent_score
```
Using the following grading strategy (for 6x6, similar matrix produced for 8x8):
```
[[10, -2, 1, 1, -2, 10],
[-2, -2, 1, 1, 1, -2],
[1, 1, 1, 1, 1, 1],
[1, 1, 1, 1, 1, 1],
[-2, -2, 1, 1, -2, -2],
[10, -2, 1, 1, -2, 10]]
```

## 2 Player Mode
- Two player mode allows two players on same computer to play


