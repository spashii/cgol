# CSD205 - Discrete Mathematics Paper

| Topic            | Conway's Game of Life                                                                                     |
| :--------------- | :-------------------------------------------------------------------------------------------------------- |
| **Submitted On** | **December 14, 2020**                                                                                     |
| **Submitted By** | **Ramya Karna (1910110308) <br> Sameer Pashikanti (1910110339) <br> Vikram Karthikay Putha (1910110445)** |

---

# Conway's Game of Life

<div style="display:flex;justify-content:center;flex-direction:column;align-items:center;margin-bottom:10px">
<img style="height:200px;width:100%;object-fit:cover;margin-bottom:5px;"
src="https://www.wired.com/wp-content/uploads/2010/07/LifeHTML5.png" alt="Conway's Game of Life">
</div>

---

### Table of Contents

S. No | Topic
:---: | ---
1.    | [Abstract](#abstract)
2.    | [Introduction](#introduction)
3.    | [Setup of the Game](#setup-of-the-game)
4.    | [The Rules of Life](#the-rules-of-life)
5.    | [Evolution of the Game](#evolution-of-the-game)

---

### Abstract

In the following paper, we will be discussing the mathematical implications and ramifications surrounding Conway's Game of Life. While studying the simple rules that make up this game, we attempt to analyse deep connections with various domains of mathematics. Through this paper, we aim to introduce the reader to the Game of Life as inaugarated by John Conway and look briefly into few mathematical problems along the way.

---

### Introduction

The Game of Life is a zero player game, developed by John Conway in 1970. The game is played on an infinite grid of square cells, and its evolution is only determined by its initial state and *The Rules of Life*:

1. Cells with 0 or 1 neighbors die of loneliness
1. Cells with 2 or 3 neighbors survive
1. Cells with 4 or more neighbors die of overcrowding 
1. Cells with exactly 3 neighbors, come back to life

<div style="display:flex;justify-content:center;flex-direction:column;align-items:center;margin-bottom:10px">
<img style="max-height:350px;max-width:100%;object-fit:cover;margin-bottom:5px;"
src="https://healeycodes.com/8b3e14dae1b57fa03caa478eaf866de3/conwaysgameoflife.gif" alt="Conway's Game of Life Animated">
<small><em>Conway's Game of Life</em></small></div>

The Game of Life was initially played out by hand with pens and graph paper- but like everything else, modelling this on a computer made it much easier for exploring patterns and developing its mathematics further. 

[Click here to see an implementation of The Game of Life](cgol.html)

It starts with a grid with the size of your screen and each cell is either on or off. As the game progresses, the cells change states and patterns emerge- or do they?

---

### Setup of the Game

Apart from being the basic structural, functional and biological unit of life, a **cell** is also the building block of the Game of Life. The game is run by placing a number of filled cells on an infinite two-dimensional grid- each of which can be in different **states**, on or off. The grid is initialized to some pattern, the cells each obey defined rules and change states over time according to those rules. After initialization of the grid, the universe continues to evolve through timesteps, specifically known as **generations** in this case. Each generation then switches cells on or off depending on the state of the cells that surround it, known as its **neighbors**. 

The initial pattern constitutes the **seed** of the system. The first generation comes to life by applying the rules simultaneously to every cell in the seed. In a split second (or less), the births and deaths occur. The discrete moment at which the births and deaths occur is referred to as a **tick**. The further generations are created by continually letting the cells interact with each other bounded by the rule set.

John Conway and his colleagues, brainstormed many variations of the rules, the whole discussion boiled down to this:  if the birth rule was too strong – everything expanded. If the death rules were too strong – everything died. It turned out to be quite hard to balance the rules. Con**way** found a **way**.

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

Given an input grid, one cannot determine whether the board would stablize in any given number of moves. This introduces us to one of the most important problems in computability theory, **the halting problem**. Even John Conway himself could not look at a board and determine the status of the game in the next generation and whether the game would end or not. There simply isn't any algorithmic way to determine the result of the game.

Although it is said that one should never mistake pattern for meaning, in the case of the Game of Life, we might be proving ourselves wrong. The game continues to be quite fascinating, generating a lot of interest in discovering the emerging patterns within. 
We can categorize the patterns observed on the basis of their behavioural complexity- ranging from mundane **still lives** to ones that become extinct. 
We observe that Conway's rules are quite easy if we want to go forward from one generation to the next, but to do it in reverse- to try and find out what the previous generation was from a snapshot of the current generation proves to be much more cumbersome. 


#### Still life
A still life is a pattern that does not change from one generation to the next, or an oscillator with unit period.
The most common variety of still life is the **block**. Blocks are used as the constituents of many complex devices, like the *Gosper Glider Gun*, that we discuss later. The next most common still life is the **beehive**. A beehive is created in non-interacting sets of four, the formation being known as a *honey farm*.

<div style="display:flex;justify-content:center;flex-direction:column;align-items:center;margin-bottom:15px">
<img style="max-height:350px;max-width:100%;object-fit:cover;margin-bottom:-5px;"
src="https://iq.opengenus.org/content/images/2019/03/staticGameofLife.png" alt="Still Lifes">
<small><em>
Still Lifes
</em></small></div>


Following the hive, we have the **loaf**, and a **bi-loaf** is a pair of loaves found together. On further pairing, we have what is called a **bakery**. 

The patterns above are among commonly occurring patterns that are stable 

<div style="display:flex;justify-content:center;flex-direction:column;align-items:center;margin-bottom:20px">
<img style="max-height:300px;max-width:100%;object-fit:cover;margin-bottom:5px;"
src="https://user-images.githubusercontent.com/63326129/101979337-45d60100-3c82-11eb-8067-4c5e2e59d954.png", alt="Stable Configuration">
<small><em>
A Stable Configuration involving Still Lifes
</em></small></div>


The most intriguing part of still life, we found to be the **eaters**. Still lifes can be utilized to modify or destroy other objects. A still life becomes an eater when it can be used to absorb some other pattern, and return to its original state after the collision. An example of eater that has the ability to absorb several varieties of spaceships is the **fish-hook**, and another device that is similar but doesn't quite 'eat' the pattern is a **reflector**, that is capable of altering the direction of an incoming spaceship. 

<div style="display:flex;justify-content:center;flex-direction:column;align-items:center;margin-bottom:10px">
<img style="max-height:350px;max-width:100%;object-fit:cover;margin-bottom:5px;"
src="https://user-images.githubusercontent.com/63326129/102098257-fabc1980-3e4c-11eb-9cb0-cb222343d8a3.gif" alt="">
<small><em>
An eater
</em></small></div>

In the quest to find out whether there exist patterns in which the number of cells grow infinitely, Conway offered a prize of $50 to anyone who could prove or disprove the existence of an *infinite* form. A group of researchers from MIT, led by Bill Gosper, came forward with their discovery of a life form, termed a **Glider Gun**. The glider gun is a pattern that 'fires' a new glider every 30 generations. The population of living cells grows forever as each new glider adds five new live cells to the original form. 

<div style="display:flex;justify-content:center;flex-direction:column;align-items:center;margin-top:40px;margin-bottom:20px">
<div>
<img style="max-height:300px;max-width:45%;object-fit:cover;margin-bottom:10px;margin-right:20px"
src="https://vignette.wikia.nocookie.net/emergentuniverse/images/d/d0/Game_of_life_animated_glider_2.gif/revision/latest/scale-to-width-down/340?cb=20120305021401", alt="">
<img style="max-height:300px;max-width:45%;object-fit:cover;margin-bottom:10px;"
src="https://upload.wikimedia.org/wikipedia/commons/e/e5/Gospers_glider_gun.gif", alt="">
</div>
<small><em>
A Glider and a Glider Gun
</em></small></div>

The discovery of these structures was crucial in further discoveries of more intricate and mobile structures. People started calling them **spaceships**.

<p align="center"><iframe width="560" height="315" src="https://www.youtube.com/embed/C2vgICfQawE?start=69" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe><p>

---

### Discrete Math (think of a heading)

Apart from just appearing hypnotic, these patterns can also be organized to perform functional operations. **Spaceships**, a term for streams of gliders, can be considered as signals that have causal effects on interaction with other patters. These interactions can be further organized to establish basic computational procedures like *logic gates* and simple memory counters.

A *Turing machine* is a hypothetical machine that can simulate any computer algorithm, no matter how complicated. In the theory of computation, many major complexity classes can be characterized by an appropriately restricted Turing machine, for instance the major P versus NP classes. 

The above properties imply that the Game of Life can be considered *Turing complete*, making it theoritically equivalent to a 'Universal Turing Machine'. This essentially translates to the Game of life having the ability to possess unlimited computational power in the absence of time and memory constraints, however improbable sounding. 

---
### Logic Gates
We have seen that still lifes, and patterns formed by the Game of Life can be used to generate and destroy signals- take for instance, the glider consumer and glider generator. 
// insert glider cons and gen.

From this, we get our one, and our zero. When we have a one and a zero, we have what is known is binary logic. If we have binary logic, we can make logic gates. 

<div style="display:flex;justify-content:center;flex-direction:column;align-items:center;margin-bottom:10px">
<img style="max-height:350px;max-width:100%;object-fit:cover;margin-bottom:5px;"
src="http://article.sapub.org/image/10.5923.j.ijis.20160601.02_009.gif", alt="Logic Gates">
</div>

While trying to implement logic gates using the Game, we come across these three requirements:
* Some kind of electrical pulses to represent input
* Wires to transmit the electrical pulses
* Devices to process the given input and compute the Boolean output

USing gliders, we can encode these utilizing components from the Game of Life:
* I/O pulses $=>$ Gliders
* Wires $=>$ Glider movement trajectories
* Processing devices $=>$ Glider collisions

We also implement some glider guns, that play no role in the production of input, but they help in executing collision, or deflecting the path of the glider stream to enhance the collision, termed *process guns*.
Just like process guns, *eaters* are used to destroy some gliders that do not help in determining the output.
From the above findings, we see that a stream of gliders can encode any data.
For instance, take 
101: glider - no glider - glider

We handled the input so far- and our work seems to manipulate our input when it is true fairly easily. However, we must also program the gliders to propagate only if the input is true- or stop when the input is false. This can be done via coupling the glider gun with a block- the still life we learnt about in the previous section; a glider is eliminated by a block during collision.

Essentially, in an input stream, a glider indicates a true pulse, and a *missing* glider indicates a false pulse. 

---
###Legacy

John Conway passed away in April 2020 due to COVID-19 complications. His work continues to be celebrated, being the most written about 
John Conway's work on the Game of Life opened up several avenues in the field of mathematical research- primarily the subject of 'cellular automata'. 

In an interview, on being asked if he hated the Game of Life, despite being proud of his achievement, he still believed that it overshadowed every other aspect of his mathematical work- or life, in general. 
Conway worked on several branches of mathematics:  combinatorial game theory, group theory, knot theory and geometric topology. 


---

### todo :star:
- [ ] conclusion
- [x] logic gate 
- [x] roll numbers
- [ ] math
- [ ] watch the vids and inerpret
- [ ] theorem of mathematical logic 
- [ ] halting
- [x] his death and legacy
- [ ] the invention of LC
- [ ] problem set and solvable set
- [ ] effective calculabitiyt



---

[The Art of Code - Dylan Beattie](https://youtu.be/6avJHaC3C2U?t=272)

[Implementation of CGOL](cgol.html)

---