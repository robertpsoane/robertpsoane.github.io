---
layout: project
title: "Conway's Game of Life"
subtitle: "This simulation of Conway's Game of Life was hacked together over a weekend to gain exposure to React.  It is surprisingly satisfying to sit and play with!" # This forms the basis of a description of the project
date: 2021-02-28 09:14:13 -0000

githuburl: "https://github.com/robertpsoane/game-of-life/"
liveurl: "https://robertpsoane.github.io/game-of-life/"
project-img: "/img/projects/game-of-life/GameofLife.png"

img-1: "/img/projects/game-of-life/semifinal.png"
---

## Conway's Game of Life

Conway's Game of Life (aka Life) was a zero player game created by John Conway. The idea is to simulate life in a 2d grid with a set of simple rules:

- A live cell with less than 2 living neighbours dies.
- A live cell with 2 or 3 live neighbours survives.
- A live cell with 4+ live neighbours dies.
- A dead cell with 3 live neighbours comes back to life.

## The Game

<img src="{{ page.img-1 | prepend: site.baseurl | replace: '//', '/' }}" style="display: block; margin-left: auto; margin-right: auto; width: 75%;">
<span class="caption text-muted"><b>Figure 1:</b>The game depicting a <em>Gosper Glider Gun</em></span>

The game can be found <a href="https://robertpsoane.github.io/game-of-life/"> here</a>. I built it in React over the course of the weekend, initially as a very simple game embedded in a basic web page, after which I redesigned the UI to look a bit more modern. The original version of the game can be found <a href="https://robertpsoane.github.io/game-of-life-v1">here</a>.

There are a number of well-known named patterns that can be produced with the game, which give interesting results. A selection of these can be placed on the board from the patterns menu.

## The Original Game

Here is a demo of my original design before I redesigned it.

<center>
<iframe width="560" height="315" src="https://www.youtube.com/embed/eY2q6-ABlIk" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</center>
