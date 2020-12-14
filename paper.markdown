# CSD205 - Discrete Mathematics Term Paper

| Topic            | Conway's Game of Life                                                                                     |
| :--------------- | :-------------------------------------------------------------------------------------------------------- |
| **Submitted On** | **December 12, 2020**                                                                                     |
| **Submitted By** | **Ramya Karna (1910110308) <br> Sameer Pashikanti (1910110339) <br> Vikram Karthikay Putha (1910110445)** |

---

## Conway's Game of Life

<div style="display:flex;justify-content:center;flex-direction:column;align-items:center;margin-bottom:10px">
<img style="height:400px;width:100%;object-fit:cover;margin-bottom:5px;"
src="https://www.wired.com/wp-content/uploads/2010/07/LifeHTML5.png" alt="Conway's Game of Life">
</div>

### Abstract

In the following paper, we will be discussing the mathematical implications and ramifications surrounding Conway's Game of Life. 

---

### Introduction

The Game of Life is a zero player game, developed by John Conway in 1970. The game is played on an infinite grid of square cells, and its evolution is only determined by its initial state and *The Rules of Life*:

1. Cells with 0 or 1 neighbors die of loneliness
1. Cells with 2 or 3 neighbors survive
1. Cells with 4 or more neighbors die of overcrowding 
1. Cells with exactly 3 neighbors, come back to life

<div style="display:flex;justify-content:center;flex-direction:column;align-items:center;margin-bottom:10px">
<img style="max-height:350px;max-width:100%;object-fit:cover;margin-bottom:5px;"
src="https://healeycodes.com/8b3e14dae1b57fa03caa478eaf866de3/conwaysgameoflife.gif", alt="Conway's Game of Life Animated">
<small><em>
Conway's Game of Life
</em></small></div>


The Game of Life was initially played out by hand with pens and graph paper- but like everything else, modelling this on a computer made it much easier for exploring patterns. 

[Click here to see an implementation of The Game of Life](cgal.html)

It starts with a grid with the size of your screen and each cell is either on or off. As the game progresses, the cells change states and patterns emerge- or do they?


---

### Set up of the Game

Apart from being the basic structural, functional and biological unit of life, a *cell* is also the building block of the Game of Life. The game is run by placing a number of filled cells on an infinite two-dimensional grid- each of which can be in different "states", on or off. The grid is initialized to some pattern, the cells each obey defined rules and change states over time according to those rules. After initialization of the grid, the universe continues to evolve through timesteps, specifically known as generations in this case. Each generation then switches cells on or off depending on the state of the cells that surround it. Each cell is either alive or dead- on or off. And it's current standing depends on its neighbours. 

The initial pattern constitutes the *seed* of the system. The first generation comes to life by applying the rules simultaneously to every cell in the seed. In a split second (or less), the births and deaths occur. The discrete moment at which the births and deaths occur is referred to as a *tick*. The further generations are created by continually letting the cells interact with each other bounded by the *rule set*.

---

### The Rules of Life

Conway's Game of Life is governed by this primary rule set:

* **Birth** 
a cell that is dead at time $t$ will be alive at time $t + 1$ if exactly $3$ of its $8$ neighbours were alive at time $t$

* **Death** : a cell can die by: 
  * **Overcrowding**
     if a cell is alive at time $t$ and $4$ or more of its neighbours are also alive at time $t$, the cell will be dead at time $t + 1$
  * **Exposure**
    if a live cell at time $t$ has only $1$ live neighbour or no live neighbours, it will be dead at time $t + 1$

* **Survival**
a cell survives from time $t$ to time $t + 1$ if and only if $2$ or $3$ of its neighbours are alive at time $t$

---

### Evolution of the Game

Although it is said that one should never mistake pattern for meaning, in the case of the Game of Life, we might be proving ourselves wrong. The game continues to be quite fascinating, generating a lot of interest in discovering the emerging patterns within. 
We can categorize the patterns observed on the basis of their behavioural complexity- ranging from mundane *still lives* to ones that become extinct. 
We observe that Conway's rules are quite easy if we want to go forward from one generation to the next, but to do it in reverse- to try and find out what the previous generation was from a snapshot of the current generation proves to be much more cumbersome. 


#### Still life
A still life is a pattern that does not change from one generation to the next, or an oscillator with unit period.
The most common variety of still life is the **block**. Blocks are used as the constituents of many complex devices, like the *Gosper Glider Gun*, that we discuss later. The next most common still life is the **beehive**. A beehive is created in non-interacting sets of four, the formation being known as a *honey farm*.

<div style="display:flex;justify-content:center;flex-direction:column;align-items:center;margin-bottom:15px">
<img style="max-height:350px;max-width:100%;object-fit:cover;margin-bottom:-5px;"
src="https://iq.opengenus.org/content/images/2019/03/staticGameofLife.png", alt="Still Lifes">
<small><em>
Still Lifes
</em></small></div>


Following the hive, we have the **loaf**, and a **bi-loaf** is a pair of loaves found together. On further pairing, we have what is called a **bakery**. 

The patterns above are among commonly occurring patterns that are stable 

<div style="display:flex;justify-content:center;flex-direction:column;align-items:center;margin-bottom:10px">
<img style="max-height:300px;max-width:100%;object-fit:cover;margin-bottom:5px;"
src="https://user-images.githubusercontent.com/63326129/101979337-45d60100-3c82-11eb-8067-4c5e2e59d954.png", alt="Stable Configuration">
<small><em>
A Stable Configuration involving Still Lifes
</em></small></div>


The most intriguing part of still life, we found to be the *eaters*. Still lifes can be utilized to modify or destroy other objects. A still life becomes an eater when it can be used to absorb some other pattern, and return to its original state after the collision. An example of eater that has the ability to absorb several varieties of spaceships is the **fish-hook**, and another device that is similar but doesn't quite 'eat' the pattern is a **reflector**, that is capable of altering the direction of an incoming spaceship. 

---small line

In the quest to find out whether there exist patterns in which the number of cells grow infinitely, Conway offered a prize of $50 to anyone who could prove or disprove the existence of an *infinite* form. A group of researchers from MIT, led by Bill Gosper, came forward with their discovery of a life form, termed a **glider gun**. The glider gun is a pattern that 'fires' a new glider every 30 generations. The population of living cells grows forever as each new glider adds five new live cells to the original form. 

// glider gun image

## I'M SICK OF PATTERNS SOMEONE ELSE TAKE OVER PLS

---

### Discrete Math (think of a heading)

Apart from just appearing hypnotic, these patterns can also be organized to perform functional operations. **Spaceships**, a term for streams of gliders, can be considered as signals that have causal effects on interaction with other patters. These interactions can be further organized to establish basic computational procedures like *logic gates* and simple memory counters.

A *Turing machine* is a hypothetical machine that can simulate any computer algorithm, no matter how complicated. In the theory of computation, many major complexity classes can be characterized by an appropriately restricted Turing machine, for instance the major P versus NP classes. 

The above properties imply that the Game of Life can be considered *Turing complete*, making it theoritically equivalent to a 'Universal Turing Machine'. This essentially translates to the Game of life having the ability to possess unlimited computational power in the absence of time and memory constraints, however improbable sounding. 

---
---

### todo :star:
- [ ] conclusion
- [ ] logic gate 
- [ ] roll numbers
- [ ] math
- [ ] watch the vids and inerpret
- [ ] theorem of mathematical logic 
- [ ] halting
- [ ] his death and legacy
- [ ] the invention of LC
- [ ] problem set and solvable set
- [ ] effective calculabitiyt



---

[The Art of Code - Dylan Beattie](https://youtu.be/6avJHaC3C2U?t=272)

[Implementation of CGOL](cgol.html)

---