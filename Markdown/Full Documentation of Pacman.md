# <p align="center"><strong>THIS PROJECT IS A WORK IN PROGRESS!</strong></p>
<br><br><br>
# <p align="center">Full Documentation of _Pacman_</p>

## Table of Contents
<br>

- [History](#history)
- [Gameplay](#gameplay)
- [The Ghosts](#the-ghosts)
- [The Player](#the-player)
- [Game Elements](#game-elements)
- [Oddities](#oddities)


<br><hr><br>

## History

&emsp;&emsp;

<br><hr><br>

## Gameplay

&emsp;&emsp;

<br><hr><br>

## The Ghosts

&emsp;&emsp;In Pacman, four colored ghosts chase the player and attempt to defeat them by colliding with them. The algorithm that does this _is_ reliant on decision making, making it more of an artificial intelligence, but its not as diverse as it sounds. Rather than all four opponents being tied to a unique AI, each one uses the same decision making process. The aspect of their design that makes them behave different is their _target_.

Each ghost has a unique tile position they target depending on certain conditions of the game; including their _current state_ and Pacman's position.

### Different Ghost Modes/States
<br>

**Chase Mode**: the ghosts update the target tiles as normal in an attempt to catch Pacman.<br>

**Scatter Mode**: the ghosts scatter to specific tiles in the corners of the map in order to give the player a break. However, they will still defeat Pacmaan upon collision. Each level begins in Scatter Mode.<br>

**Frightened Mode**: the ghosts are vulnerable to Pacman and no longer rely on targets, instead relying on RNG to determine which eligible direction to turn in. Upon touching Pacman, they enter _Eaten Mode_.<br>

**Eaten Mode**: the ghosts retreat to their "Ghost Pen", as nothing but floating eyes, in order to regenerate their bodies. Their target is the location above the pen. They are harmless to Pacman.<br>

**Idle Mode**: Within the "Ghost Pen", they hover up and down, completely unable to be touched by Pacman. Once they leave idle mode, they never return unless the level restarts or a new level is started.<br>

##### Naming convention: [(_RetroGameMechanicsExplained_, Youtube 2019)](#work-cited), with the exception of _Idle Mode_.
<br>


<p align="center"><img src="
https://github.com/MichaelWarmbier/Pacman_GML/blob/main/Documents/ModeInfographic.png?raw=true"></p>

##### <p align="center">Infographic of all the different modes and events that change them.</p>

## Scatter Mode by Level

&emsp;&emsp;Each level follows certain rules that determine when the ghosts are allowed to enter Chase Mode and Scatter Mode. Whenever a ghost switchs between these Modes, they will turn around. This is one of two exceptions where a ghost may turn around. Below is a graph showing the durations of each mode cycle:

Level      | Scatter     | Chase     | Scatter    | Chase      | Scatter      | Chase      | Scatter      | Chase |
|----------|-------------|-----------|------------|------------|--------------|------------|--------------|-------|
1 | 7s | 20s | 7s | 20s | 5s | 20s | 5s | Forever
2 - 4 | 7s | 20s | 7s | 20s | 5s | 17m 13s 140ms | 60ms | Forever
5+ | 5s | 20s | 5s | 20s | 5s | 17m 17s 140ms | 60ms | Forever

##### Chart Creation: [(_RetroGameMechanicsExplained_, Youtube 2019)](#work-cited)
<br>

This chart shows that the four first cycles between these two modes last a specific amount of time. Afterwards, the ghosts are stuck infinitely in chase mode. The fourth scatter mode is also extremely short, being about one frame of time.

<br>

### Ghost Movement AI

&emsp;&emsp;Every frame that one of the ghosts is in a state other than _Idle Mode_ or _Frightened Mode_ and is aligned with a tile, they rely on a deterministic function to make decision for them to decrease the distance from them and their target as much as possible when advancing. 

To start, each ghost will check four directions around them; up, down, left and right. If the direction is not behind their current direction of movement, or facing direction, and if the tile immediately in that direction is non-collidable (not considered a wall), then it is considered eligable.

After determining eligability, each immediate tile in the given direction has its position utilized in conjunction with the position of the ghosts target in order to calculate distance using the distance formula:
<br><br>

> <font size="6"><p align="center">Distance = √[ (x₂ - x₁)² - (y₂ - y₁)² ]</p></font>

<br>
In addition, each direction has a priority in descending order should any of the distance be equal: up, right, down, left. Once a direction is decided, the ghost changes to face that direction and starts incrementing its position accordingly.
<br><br>

### Shadow - "Blinky"

&emsp;&emsp;Blinky contains the simplest algorithm, with his target in Chase Mode being _Pacman_ himself. This makes him the most aggression ghost. Excluding one exception, Blinky will _always_ be able to find Pacman while in chase mode.

Blinky's Scatter Mode target is the top-right corner of the game's screen, causing him to circle that corner while he's in this mode.

<p align="center"><img src="https://camo.githubusercontent.com/2b643850ac373a95e32cd29518f698b01025f243decf894094b1daefc581229b/68747470733a2f2f692e696d6775722e636f6d2f576e4c6464476c2e676966"></p>

##### <p align="center">Blinky's movement AI.</p>

This simulation was made in _GameMaker 2_. Unlike the original arcade version of _Pacman_, ghosts update their movement every frame (rather than every tile). A visualization of their position relative to their target as well as a valid-movement indiciator was added for better visualization.

<br>

### Speedy - "Pinky"

&emsp;&emsp;Pinky's target in Chase Mode is intended to be four tiles in front of the direction that Pacman's faces. However, at least on the original arcade version, due to an oversight this behavior breaks when Pacman faces upwards. In this scenario, a byte-overflow error causes Pinky's target to be both four tiles in front of Pacman, and four tiles to his left.

Pinky's design is intended to allow her to ambush Pacman in conjunction with other ghosts, namely Blinky. Her target tile in Scatter Mode is the top-left corner.

<p align="center"><img src="https://camo.githubusercontent.com/047cbf1ac6ddc07a762bf93729d4f4fe80d18ee83470d4e4c0afd76d808f0247/68747470733a2f2f692e696d6775722e636f6d2f556163463430462e676966"></p>

##### <p align="center">Pinky's movement AI.</p>

<br>

### Bashful - "Inky"

&emsp;&emsp;Inky has arguably the most complex algorithm. In Chase Mode, an intermediate tile positioned two tiles in front of Pacman's facing position is chosen. The target is then determined by rotating the vector from the intermediate tile to Blinky 180°. This means that Inky's position is not only dependant on Pacman, but Blinky as well.

Like with Pinky, Inky's intermediate tile will offset itself by two to the left if Pacman faces upwards. Inky's design is befitting of his name, as he does not approach Pacman willingly as much as the other ghosts. His Scatter Mode target is the bottom-right corner.

<p align="center"><img src="https://camo.githubusercontent.com/4e5efa096eecab6adece232ecce26d69533dd8548a9d90656d313f913b76963a/68747470733a2f2f692e696d6775722e636f6d2f53544857524a742e676966"></p>

##### <p align="center">Inky's movement AI.</p>

In this specific visualization, a white line was added to show the vector involved in the calculation.

<br>

### Pokey - "Clyde"

&emsp;&emsp;Clyde's Chase Mode movement begins the same as Blinky. That is, his target will be Pacman himself. However, if Clyde reaches a position of less than eight tiles always from Pacman, his target will switch to his Scatter Mode target, which is the bottom-left corner. This is befitting to his name, as Clyde often approaches Pacman and then runs away. This also means that if Pacman is near the bottom-left corner, Clyde will approach him regardless as he's in the way of his target.

<p align="center"><img src="https://camo.githubusercontent.com/735f5220c91ba3f4b79b36d7c85a7c206f64fced16d73964b23c0c7c35a5a5d9/68747470733a2f2f692e696d6775722e636f6d2f574b6e43744f692e676966"></p>

##### <p align="center">Clyde's movement AI.</p>

<br><hr><br>

## The Player

&emsp;&emsp;

<br><hr><br>

## Game Elements

&emsp;&emsp;

<br><hr><br>

## Oddities

<p align="center"><img src="https://camo.githubusercontent.com/8d20e14ef42f498fb9607cc00ce72ba19c36e4f5216a3b3a4ed7882aa1efa98e/68747470733a2f2f692e696d6775722e636f6d2f794a33554458492e676966"></p>

##### <p align="center">The infamous infinite survivability glitch.</p>

&emsp;&emsp;

<br><hr><br>

## Work Cited

<br><br>

### “Pac-Man Ghost AI Explained.” _RetroGameMechanicsExplained_, YouTube, 13 July 2019, <br>
### &emsp;https://www.youtube.com/watch?v=ataGotQ7ir8&amp;t=664s. 
 