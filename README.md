# [Makers Academy](http://www.makersacademy.com) - Week 11 & 12 Final Project

## Paladin's Path (An Unreal Engine Game)

[Project Outline](#Outline) | [Specification](#Specification) | [User Stories](#Story) | [Approach & Game Progression](#Approach) | [Installation Instructions](#Installation) | [Testing](#Testing) | [See The Game](#Game)

<div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/PaladinsPath-CinematicView-1.gif"/></div>

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
$ git clone https://github.com/BenSheridanEdwards/Makers_Paladins_Path.git
```
Open the Unreal game engine and open the project by navigating the the Makers_Unreality folder and clicking the folder inside named, Unreality.

## <a name="Testng">Testing</a>

In this part of our README, we'll link to videos showcasing our tests.

# <a name="Game">Paladin's Path (See The Game)</a>

#### The World
[Story](#Story) | [BirdsEye Cinematic Trailer](#Birdseye) | [Map](#Map) 

#### [The Hero](#Character)

[Movement](#Movement) | [Dynamic Targeting](#Targeting) | [Physical Attacks](#PhysicalAttacks) | [Magical Attacks](#MagicalAttacks) | [Health Bar](#HealthBar)

#### The Enemies

[Golems](#Golems) | [Fire Golem](#FireGolem) | [Ice Golem](#IceGolem) | [Rock Golem](#RockGolem) | [Final Boss](#BossGolem)

####  Behind the Game (Blueprints / Game Code)

[Game Mechanics](#Mechanics) | [Level Design](#Level) | [Animations](@Animations) | [Character Skills](#Skills) | [Enemy AI](#EnemyAI)

---

### <a name="Story">Story</a>
  
##### In Paladin's path you'll move through an open-world with different environments for you to explore: 

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-HeroCollage.jpeg)

##### Your goal is to reach the stronghold castle in the distance, where a powerful enemy awaits you:

![](https://github.com/BenSheridanEdwards/Makers_Final_Project_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-Start-CastleView-Top.png)

##### Along your path, you'll encounter enemies, called Golems. You'll fight multiple types of Golems during your quest:

![](https://github.com/BenSheridanEdwards/Makers_Final_Project_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/Golem%20Types.jpeg)
*Golems are magical being made of inert matter like rock, fire, and ice. That have been animated to life by mysterious forces.*


### <a name="Birdseye">Birdseye Cinematic Trailer</a>

Click the preview below to see our full one-minute cinematic trailer on [YouTube](https://youtu.be/R4Vh61J5KaI):

<a href="https://youtu.be/R4Vh61J5KaI"><div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/PaladinsPath-CinematicView-1.gif"/></div></a>


### <a name="Map">Map</a>

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-BirdsEye.png)



### <a name="Character"> Player Character - The Paladin</a>

#### Next we're going to take you through the core game mechanics and inputs you have availble whilst playing as our hero:

##### <a name="Movement">Player Movement</a>

You can move around with either A(Left),W(Up),S(Down),D(Right) or the directional arrows in the bottom right corner of your keyboard. You can also jump by pressing the space bar. 

![Movement Video]()

The blueprint behind this is shown below, these come by default when creating a third person character using the Unreal Game Engine, with the exception of *Find target with Axis Input*, which we'll talk about next:

![Game Movement Blueprint](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/GameMechanics/PlayerMechanics-GameInputControlsBlueprint.png)

##### <a name="Targeting">Dynamic Targeting</a>

Our game also features dynamic targeting, which allows a player to lock-on to the nearest enemy using T and switch targets left or right using the Q and E keys respectively.

![Targeting Video]()

Targeted enemies are shown by a glowing red ring at the targets feed

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/GameMechanics/PlayerMechanics-DynamicTargetingMechanic.png)

All credit for this targeting system goes to Grzegorz Szewczyk, whose targeting system we purchased on the Unreal MarketPlace. The red targeting ring is our own addition.  

You'll find Grzegorz's dynamic targeting system [here](https://www.unrealengine.com/marketplace/en-US/product/dynamic-targeting). 

### <a name="PhysicalAttacks">Physical Attacks</a>

##### As a Paladin, you have a sword and shield, and can deal devestating combo attacks: 

<p align="center"><b><i>Sword Strike Combo</i></b></p>
<a href="https://github.com/BenSheridanEdwards/Makers_Final_Project_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/PaladinsPath-SwordAttack1Gif.gif"><div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Final_Project_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/PaladinsPath-SwordAttack1Gif.gif"/></div></a>
<br>

### <a name="MagicalAttacks">Magical Attacks<a/>
  
##### As a Paladin, you're also blessed with magic, and command fire, ice, and earth spells:

<p align="center"><b><i>Fire Magic</i></b></p>

<p align="center"><b><i>Ice Magic</i></b></p>

<p align="center"><b><i>Earth Magic</i></b></p>
<a href="https://github.com/BenSheridanEdwards/Makers_Final_Project_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/PaladinsPath-RockSpell.gif"><div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Final_Project_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/PaladinsPath-RockSpell.gif"/></div></a>


## Behind the Game (Blueprints / Game Code)

### Game Mechanics


