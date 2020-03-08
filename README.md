# [Makers Academy](http://www.makersacademy.com) - Week 11 & 12 Final Project

## Paladin's Path (An Unreal Engine Game)

[Project Outline](#Outline) | [Specification](#Specification) | [User Stories](#Story) | [Installation Instructions](#Installation) | [The Game](#Game) | [Testing](#Testing) 

<div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/PaladinsPath-CinematicView-1.gif"/></div>

## <a name="Outline">Project Outline</a>

### Overview

For our final project, we all came together to build a game that would allow us to utilise the programming skills we learnt at Makers whilst also exposing us to one of the gaming industries leading game creation engine, Unreal.

Our original goal with this project was to create a turn-based battle game where a hero faught against enemies of different types using elemental projectile spells. But as we approached the end of the first week, we decided to pivot our game to the more comtempoary open-world style of game, where players could freely move around, encountered enemies throughout the world, and then could battle using a dynamic targeting system and a range of different attacks. 

![Early Map Outline]()
*An early stage map outlining a path for our hero*

### Approach 

Maker's Academy teaches us to take a very methodical approach to building a program. Using test-driven development, we were able to visualise the features we wanted to create, create an environment for the test, setup the variables needed for the test, expect an outcome, and then work towards passing that test in the simpliest way possible. 

![Early Stage Test](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/Testing/BattleMechanics-EarlyStage/PaladinsPath-TestingDamageCollage.jpeg)
*An early stage view of us testing the core mechanics of projectiles and damage of our battle game* 

We will ensure we have:
- Daily team standups and check-ins, end-of-day retrospectives, open communication on blocks or large problems, and pairing daily to tackle problems.
- A MVP created in Ruby that outlines the basic game mechanics and turn-based flow structure. 
- All our code hosted on GitHub, using Jenkins for CI/CD, and that we can deploy straight to the browser or [localhost](https://docs.unrealengine.com/en-US/Platforms/HTML5/GettingStarted/index.html) server from the unreal engine.
- High Coverage of game machanics in our unit and feature tests - Creating tests that cover a range of user experiences whilst playing our game, mapping out different scenarios for world navigation. winning and losing battles, and ensuring attack animations execute as expected.


## <a name="Specification">Specification</a>

### Initial Requirements

- All game mechanics but be testable using Unreal's [Automation System Overview](https://docs.unrealengine.com/en-US/Programming/Automation/index.html) - Which will involve both feature and unit tests
- Players will be able to battle NPCs in a turn based style, using a variety of attacks
- Players and enemys will have a hit point counter, once that count reaches 0, the player or enemy dies
- When players die, the game will be reset
- Players will have 4 basic attacks at their disposal
- Attacks will be elemental by nature. Examples of elemental attacks are fire, water, air, earth, poison, and paralysis

### Final Requirements

### Additional Features we'd love to add

- Enabling VR controls
- Enemies having multiple attacks
- More advanced enemy AI

## <a name="Story">User Stories</a>

```
As a player, so I can play a game of Unreality, 
I'd like to start a game with full hit points.

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

## <a name="Testng">Testing</a>
