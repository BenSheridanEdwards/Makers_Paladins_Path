# [Makers Academy](http://www.makersacademy.com) - Week 11 & 12 Final Project

## Paladin's Path (An Unreal Engine Game)

### [Project Outline](#Outline)
[Overview]() | [Approach]() | [Progression]() | [Features]()

### [Our Game](#Game)

[Story](#Story) | [Level Design](#Level) | [Hero](#Hero) | [Enemies](#Enemies)

### [Behind The Game (Unreal Blueprints)](#Code)

[Game Mechanics]() | [Hero Blueprints]() | [Enemy Blueprints]()

### [Download & Play](#Download)

---

## <a name="Outline">Project Outline</a>

<div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-PlayerStart..png" width="600"/></div>

### Overview

For our final project, our team decided to build a game that would allow us to utilise the programming skills we've learnt at Maker's Academy, whilst also exposing us to the game engine Unreal, a leading creation tool used by gaming companies across the globe. 

Our original goal with this project was to create a turn-based battle game where a hero fought against enemies of different types using elemental projectile spells. But as we approached the end of the first week, we decided to pivot the core mechanic of our game to the more contemporary open-world style of game - Where players could freely move around, encounter enemies throughout the world, and then could battle using a dynamic targeting system with a combination of physical and ranged attacks.

### Approach 

Maker's Academy teaches us to take a very methodical approach to building a program. Using test-driven development, we were able to visualise the features we wanted to create, create an environment to run our test, setup the variables needed, expect an outcome, and then work towards passing that test in the simpliest way possible. 

![Early Stage Test](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/Testing/BattleMechanics-EarlyStage/PaladinsPath-TestingDamageCollagePhoto.jpeg)
*An early stage view of us testing two core mechanics - projectiles and damage* 

We focused on using agile methodologies throughout our time working on this project, organising ourselves with daily stand-ups and retrospectives to ensure we were always aligned and priorising well at all times. We reviewed each others code before every merge, ensuring that all tests had passed and we had a high coverage of all features and edge cases.

### Progression

During our planning process we created a simple mockup of the map the player would tranverse. We planned on having 3 battle zones and a boss zone, indicated by the circles of sand on the left-hand map below. 

![Early Map vs Final Map](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-MapBeforevsAfter.jpeg)
*Map Creation: Day 1 Outline & Final Map*

Our final map on the right follows a very similar design pattern. Players start in the upper-central forested area and make their way through the smoke into a fire-lit cavern, the first battle zone we envisioned. After defeating serveral enemies in this zone, they move deeper into the rocky cavern to the next battle zone, where they encounter severval similar enemies but of a different type. The third battle zone is located amongst frozen wooden huts in the bottom-right of the map. This is the final zone and enemy type the player encounters before moving to the boss zone, inside the castle the player first sees in the distance when they start the game.

During our planning process, we also outlined many features we wanted to include in our game. I've listed them below, indicating those that are finished and implemented into the game, the bugs still present, and some additional features we'd love to implement in the future.

### Features
- [x] Third person battle game in an open-world
- [ ] Next feature

#### Bugs We're Squishing


#### Additional Features For The Future

- Enabling VR controls
- Enemies having multiple attacks
- More advanced enemy AI


## <a name="Game">Our Game, Paladin's Path</a>

#### The World
[Story](#Story) | [BirdsEye Cinematic Trailer](#Birdseye) | [Map](#Map) 

#### [Hero](#Character)

[Movement](#Movement) | [Dynamic Targeting](#Targeting) | [Physical Attacks](#PhysicalAttacks) | [Magical Attacks](#MagicalAttacks) | [Health Bar](#HealthBar)

### Enemies

[Golems](#Golems) | [Fire Golem](#FireGolem) | [Ice Golem](#IceGolem) | [Rock Golem](#RockGolem) | [Final Boss](#BossGolem)


---

### <a name="Story">Story</a>
  
In Paladin's path you'll move through an open-world with different environments for you to explore. Your goal is to reach the stronghold castle in the distance, where a powerful enemy awaits you:

![](https://github.com/BenSheridanEdwards/Makers_Final_Project_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-Start-CastleView-Top.png)

Along your path, you'll encounter enemies, called Golems. Golems are magical being made of inert matter like rock, fire, and ice. That have been animated to life by mysterious forces.

### <a name="Level">Level Design</a>

Click the preview below to see our full one-minute cinematic trailer on [YouTube](https://youtu.be/R4Vh61J5KaI):

<a href="https://youtu.be/R4Vh61J5KaI"><div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/PaladinsPath-CinematicView-1.gif"/></div></a>

In Paladin's Path, you'll be guided through multiple environments as you make your way through our world:

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-BirdsEye%20Markup.png)

1. A bright sunny forest, home to rock golems.
2. A scotched cave, home to fire golems.
3. A frozen cavern, home to rock and ice golems. 
4. A small snowy village, overrun by Ice golems.

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



## <a name="Enemies">Enemies</a>

### Golems

[Fire Golem](#FireGolem) | [Ice Golem](#IceGolem) | [Rock Golem](#RockGolem) | [Final Boss](#BossGolem)

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-GolemCollage.png)
