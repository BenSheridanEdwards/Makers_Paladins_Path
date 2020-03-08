# [Makers Academy](http://www.makersacademy.com) - Week 11 & 12 Final Project

## Paladin's Path (An Unreal Engine Game)

### [Project Outline](#Outline)
| [Overview]() | [Approach]() | [Progression]() | [Features]() |

### [Our Game](#Game)

| Story | Level Design | [Hero](#Hero) | [Enemies](#Enemies) |

### [Download & Play](#Download)

## <a name="Outline">Project Outline</a>

<div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-PlayerStart..png" width="600"/></div>

### Overview

For our final project, we all came together to build a game that would allow us to utilise the programming skills we learnt at Makers, whilst also exposing us to one of the gaming industries leading game creation tool, Unreal.

Our original goal with this project was to create a turn-based battle game where a hero faught against enemies of different types using elemental projectile spells. But as we approached the end of the first week, we decided to pivot our game to the more comtempoary open-world style of game, where players could freely move around, encountered enemies throughout the world, and then could battle using a dynamic targeting system and a range of different attacks. 

![Early Map vs Final Map](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-MapBeforevsAfter.jpeg)
*Map Creation: Day 1 Outline & Final Map*

### Approach 

Maker's Academy teaches us to take a very methodical approach to building a program. Using test-driven development, we were able to visualise the features we wanted to create, create an environment for the test, setup the variables needed for the test, expect an outcome, and then work towards passing that test in the simpliest way possible. 

![Early Stage Test](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/Testing/BattleMechanics-EarlyStage/PaladinsPath-TestingDamageCollagePhoto.jpeg)
*An early stage view of us testing the core mechanics of projectiles and damage of our battle game* 

We also used agile methodologies, organising ourselves with daily stand-ups and retrospectives to ensure we were aligned and priorising well at all times. We reviewed each others code before every merge ensuring that all tests had passed.

## <a name="Specification">Our Game Specification</a>

### Initial Requirements

- Players are able to battle enemies in a turn based style
- When an enemy is encountered, the player and enemies within a certain radius are transported to an arena where they will be unable to move, and will take turns attacking with the enemies.
- Players have 4 basic attacks at their disposal: a basic sword attack, and three spells of earth, fire, and ice.
- Players and enemys have a set number of health points, when their health points reach zero, they die.
- When players die, the player respawns at the start location
- When enemies die, it initiates a death animation, and they can't be targeted in subsequent turns
- Players who succeed against all of the opponents in a battle will be transported back to their location on the map to continue their journey 

### Final Requirements

- Players are able to explore an open-world map, moving along a path where they'll encounter enemies of varing types.
- When players encounter an enemy, they can lock-on to their nearest target and change targets left or right.
- Players can attack enemies with sword, fire, rock, and ice attacks.
- Depending on the type of attack and type of enemy, attacks can deal varing amounts of damage.

### Additional Features we'd love to add

- Enabling VR controls
- Enemies having multiple attacks
- More advanced enemy AI

## <a name="Story">User Stories</a>

```
As a player of Paladin's Path,
Throughout the game,
I'd like to be able to move my character around in all directions.

As a player of Paladin's Path,
When I encounter enemies,
I'd like to target them and see an indication that i'm succcessfully locked-on to a target.
```

## <a name="Installation">Installation Instructions</a>

Clone the repository from github then change directory into it.

```
$ git clone https://github.com/BenSheridanEdwards/Makers_Paladins_Path.git
```
Open the Unreal game engine and open the project by navigating the the Makers_Unreality folder and clicking the folder inside named, Unreality.

In this part of our README, we'll link to videos showcasing our tests.

# <a name="Game">Paladin's Path (See The Game)</a>

#### The World
[Story](#Story) | [BirdsEye Cinematic Trailer](#Birdseye) | [Map](#Map) 

#### [Hero](#Character)

[Movement](#Movement) | [Dynamic Targeting](#Targeting) | [Physical Attacks](#PhysicalAttacks) | [Magical Attacks](#MagicalAttacks) | [Health Bar](#HealthBar)

#### Enemies

[Golems](#Golems) | [Fire Golem](#FireGolem) | [Ice Golem](#IceGolem) | [Rock Golem](#RockGolem) | [Final Boss](#BossGolem)


---

### <a name="Story">Story</a>
  
##### In Paladin's path you'll move through an open-world with different environments for you to explore: 

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-HeroCollage.png)

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

![Targeting Video](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-DynamicTargetingGif.gif)

Targeted enemies are shown by a glowing red ring at the targets feed

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/GameMechanics/PlayerMechanics-DynamicTargetingMechanic.png)

All credit for this targeting system goes to Grzegorz Szewczyk, whose targeting system we purchased on the Unreal MarketPlace. The red targeting ring is our own addition.  

You'll find Grzegorz's dynamic targeting system [here](https://www.unrealengine.com/marketplace/en-US/product/dynamic-targeting). 

### <a name="PhysicalAttacks">Physical Attacks</a>

##### As a Paladin, you have a sword and shield, and can deal devestating combo attacks

Using the 4 key you can deal between 1-3 strikes in a single attack. 

<p align="center"><b><i>Sword Strike Combo</i></b></p>
<a href="https://github.com/BenSheridanEdwards/Makers_Final_Project_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/PaladinsPath-SwordAttack1Gif.gif"><div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Final_Project_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/PaladinsPath-SwordAttack1Gif.gif"/></div></a>
<br>

*A single strike deals 20 damage to an enemy golem, but chained together in rapid succession the damage is multipled.*

Below is the blueprint for our physical attacks, showing how we save combos and calculate damage:

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/GameMechanics/PlayerMechanics-MeleeAttacks.png)


### <a name="MagicalAttacks">Magical Attacks<a/>
  
##### As a Paladin, you're also blessed with magic, and command fire, ice, and earth spells:

<p align="center"><b><i>Fire Magic</i></b></p>

<a href="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanicsFireSpellGif.gif"><div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanicsFireSpellGif.gif"/></div></a>

<p align="center"><b><i>Ice Magic</i></b></p>

<a href="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-IceSpellGif.gif"><div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-IceSpellGif.gif"/></div></a>

<p align="center"><b><i>Earth Magic</i></b></p>
<a href="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-RockSpellGif.gif"><div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-RockSpellGif.gif"/></div></a>

In our blueprints, our spells are separated into their respective skills of fire, ice, and rock. Each playing an animation when cast, and then releasing the spell towards the direction the player is facing.

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/GameMechanics/PlayerMechanics-SpellAttacksBlueprint.png)

### <a name="Heatlh">Health Bar</a>

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-HealthBarGif.gif)

## <a name="Golems">Golems</a>

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-GolemCollage.png)
