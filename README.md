
### [Makers Academy](http://www.makersacademy.com) - Week 11 & 12 Final Project
Paladin's Path (An Unreal Engine Game)
-

[Project Outline](#Outline) | [Specification](#Specification) | [User Stories](#Story) | [Approach & Game Progression](#Approach) | [Installation Instructions](#Installation) | [Testing](#Testing) | [See The Game](#Game)

## <a name="Outline">Project Outline</a>

For our final project, we're looking to build a turn-based battle game. Inspired by a previous Maker's project battle. We'll be attempting to build our game using the Unreal game engine, and implement the skills of TDD and agile development we've learned whilst at Maker's Academy.

We will ensure we have:
- Daily team standups and check-ins, end-of-day retrospectives, open communication on blocks or large problems, and pairing daily to tackle problems.
- A MVP created in Ruby that outlines the basic game mechanics and turn-based flow structure. 
- All our code hosted on GitHub, using Jenkins for CI/CD, and that we can deploy straight to the browser or [localhost](https://docs.unrealengine.com/en-US/Platforms/HTML5/GettingStarted/index.html) server from the unreal engine.
- High Coverage of game machanics in our unit and feature tests - Creating tests that cover a range of user experiences whilst playing our game, mapping out different scenarios for world navigation. winning and losing battles, and ensuring attack animations execute as expected.


## <a name="Specification">Specification</a>

### Requirements

- All game mechanics but be testable using Unreal's [Automation System Overview](https://docs.unrealengine.com/en-US/Programming/Automation/index.html) - Which will involve both feature and unit tests
- Players will be able to battle NPCs in a turn based style, using a variety of attacks
- Players and enemys will have a hit point counter, once that count reaches 0, the player or enemy dies
- When players die, the game will be reset
- Players will have 4 basic attacks at their disposal
- Attacks will be elemental by nature. Examples of elemental attacks are fire, water, air, earth, poison, and paralysis

### Additional Features

- VR Capablity for our game
- Multiple environments for the player to explore, all contained in the same level
- Multiple enemy types

## <a name="Story">User Stories</a>

```
As a player, so I can play a game of Unreality, 
I'd like to start a game with full hit points.

```

## <a name="Approach">Approach</a>



## <a name="Installation">Installation Instructions</a>

Clone the repository from github then change directory into it.

```
$ git clone https://github.com/BenSheridanEdwards/Makers_Unreality.git
```
Open the Unreal game engine and open the project by navigating the the Makers_Unreality folder and clicking the folder inside named, Unreality.

## <a name="Testng">Testing</a>

In this part of our README, we'll link to videos showcasing our tests.

## <a name="Game">Paladin's Path (See The Game)</a>

#### The World
[Story](#Story) | [BirdsEye Cinematic Trailer](#Birdseye) | [Map](#Map) 

#### The Hero

[Player Character](#Character) | [Physical Attacks](#PhysicalAttacks) | [Magical Attacks](#MagicalAttacks) | [Health Bar](#HealthBar)

#### The Enemies

[Golems](#Golems) | [Fire Golem](#FireGolem) | [Ice Golem](#IceGolem) | [Rock Golem](#RockGolem) | [Final Boss](#BossGolem)

####  Behind the Game (Blueprints / Game Code)

[Game Mechanics](#Mechanics) | [Level Design](#Level) | [Animations](@Animations) | [Character Skills](#Skills) | [Enemy AI](#EnemyAI)

---

### <a name="Story">Story</a>
  
##### In Paladin's path you'll move through an open-world with different environments for you to explore: 

![](https://github.com/BenSheridanEdwards/Makers_Final_Project_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-Collage.jpeg)

##### Along your path, you'll encounter enemies, called Golems. You'll fight multiple types of Golems during your quest:

![](https://github.com/BenSheridanEdwards/Makers_Final_Project_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/Golem%20Types.jpeg)
*Golems are magical being made of inert matter like rock, fire, and ice. That have been animated to life by mysterious forces.*

##### Your goal is to reach the Golem's stronghold castle in the distance, where the Golem leader awaits:

![](https://github.com/BenSheridanEdwards/Makers_Final_Project_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-Start-CastleView-Top.png)

##### As a Paladin, you have a sword and shield, and multiple spells to aid you on your journey to the Golem stronghold: 

<p align="center"><b><i>Sword Strike Combo</i></b></p>
<a href="https://github.com/BenSheridanEdwards/Makers_Final_Project_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/PaladinsPath-SwordAttack1Gif.gif"><div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Final_Project_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/PaladinsPath-SwordAttack1Gif.gif"/></div></a>
<br>
<article align="center"><b><i>Rock Spell</i></b></article>
<a href="https://github.com/BenSheridanEdwards/Makers_Final_Project_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/PaladinsPath-RockSpell.gif"><div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Final_Project_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/PaladinsPath-RockSpell.gif"/></div></a>


