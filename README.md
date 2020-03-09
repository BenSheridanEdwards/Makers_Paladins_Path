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

#### Core Level & Game Mechanics
- [x] Open-World Map with multiple environments
- [x] Health System for players and enemies
- [x] Spells vary in effectiveness against different types of enemies
- [x] Dynamic Targeting allowing players to lock-on to nearby enemies and switch between targets. 
- [x] Player respawns upon death

#### Player
- [x] Player health bar that changes colour and size depending on the amount of remaining health points
- [x] Players can cast spells of Fire, Ice, and Rock
- [x] Players have a physical sword attack that deals a fixed amount of damage
- [x] Different attack animations for physical and ranged attacks 
- [x] Players can use a physical combo sword attack (Animation)
- [ ] Combo attacks multiply attack damage 
- [ ]

#### Enemies 
- [x] Enemies have AI that allows them to move randomly within a designated area 
- [x] Enemies have AI that allows them to follow a patrol path of set points in a designated area
- [x] Enemies have AI that allows them to see the player when they're in the enemies line of sight.=
- [x] Enemies chase and attack the player upon detecting them
- [x] Enemies have a simple physical attack that deals a fixed amount of damage

#### Bugs We're Squishing

- [ ] Combo attacks not working as expected in terms of damage output
- [ ] Overlap with a dead enemy body causes them the mesh to stand upright and then fall down .

#### Additional Features For The Future

- Player has different animations for each spell
- Enemies have multiple attacks
- Enemies have more advanced AI - More senses, able to raise alarms, and alert other enemies when the player has been detected
- Enabling VR controls



## <a name="Game">Our Game, Paladin's Path</a>

[Story](#Story) | [Level Design](#Level) | [Hero](#Hero) | [Enemies](#Enemies)

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

[Movement](#Movement) | [Health Bar](#HealthBar) | [Dynamic Targeting](#Targeting) | [Attacks](#Attacks) |

Next we're going to take you through the core game mechanics and inputs you have availble whilst playing as our hero:

#### <a name="Movement">Player Movement</a>

You can move around with either A(Left),W(Up),S(Down),D(Right) or the directional arrows in the bottom right corner of your keyboard. You can also jump by pressing the space bar. 

##### <a name="Targeting">Dynamic Targeting</a>

The player can also use dynamic targeting, which allows a player to lock-on to the nearest enemy using (T), and switch targets left or right using the (Q) and (E) keys respectively.

![Targeting Video](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-DynamicTargetingGif.gif)
*Targeted enemies are shown by a glowing red ring at the targets feed*

### <a name="PhysicalAttacks">Physical Attacks</a>

##### As a Paladin, you have a sword and shield, and can deal devestating combo attacks

Using the (4) key you can deal you can swing your sword to hit an enemy with 20 damage points per hit. 

<p align="center"><b><i>Sword Slash</i></b></p>
<a href="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-SwordSlash.gif"><div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-SwordSlash.gif"/></div></a>
<br>



### <a name="MagicalAttacks">Magical Attacks<a/>
  
As a Paladin, you can also use magic. You have three spells, a fireball spell, an ice shard spell, and a boulder spell

<p align="center"><b><i>Fireball</i></b></p>

Fireball is a fire-type attack that hurls a ball of fire at your target, dealing 20 damage points. Fireball is weak against earth-type enemies, dealing a reduced 15 damage points, and strong against water-type enemies, dealing a boosted 30 damage points.

<a href="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-FireballSpell.gif"><div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-FireballSpell.gif"/><i>Press [1] to cast Fireball</i></div></a>
<i>Press [1] to cast Fireball</i>

<p align="center"><b><i>Ice Shard</i></b></p>

Ice shard is a water-type attack that shoots a high speed shard of ice at your target, dealing 20 damage points. Ice shard is weak against fire-type enemies, dealing a reduced 15 damage points, and strong against earth-type enemies, dealing a boosted 30 damage points.

<a href="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-IceShard.gif"><div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-IceShard.gif"/></div></a>

<p align="center"><b><i>Boulder</i></b></p>

Boulder is a earth-type attack that hurls a rock straight at your target, dealing 20 base damage. Boulder is weak against water-type enemies, dealing a reduced 15 damage points, and strong against fire-type enemies, dealing a boosted 30 damage points.

<a href="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-BoulderSpell.gif"><div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-BoulderSpell.gif"/></div></a>

### <a name="Heatlh">Health Bar</a>

The hero starts out with 100 health points. Golem attacks deal 10 damage, so decrease your health by 10% for every hit. So your health points decrease, the health bar next to the heros head will both deplete and change colour from green to amber to red.

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-HealthBarGif.gif)

## <a name="Enemies">Enemies</a>

### Golems

[Fire Golem](#FireGolem) | [Ice Golem](#IceGolem) | [Rock Golem](#RockGolem) | [Final Boss](#BossGolem)

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-GolemCollage.png)





---


The blueprint behind this is shown below, these come by default when creating a third person character using the Unreal Game Engine, with the exception of *Find target with Axis Input*, which we'll talk about next:

![Game Movement Blueprint](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/GameMechanics/PlayerMechanics-GameInputControlsBlueprint.png)

---

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/GameMechanics/PlayerMechanics-DynamicTargetingMechanic.png)

All credit for this targeting system goes to Grzegorz Szewczyk, whose targeting system we purchased on the Unreal MarketPlace. The red targeting ring is our own addition.  

You'll find Grzegorz's dynamic targeting system [here](https://www.unrealengine.com/marketplace/en-US/product/dynamic-targeting). 

---

Below is the blueprint for our physical attacks, showing how we save combos and calculate damage:

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/GameMechanics/PlayerMechanics-MeleeAttacks.png)

In our blueprints, our spells are separated into their respective skills of fire, ice, and rock. Each playing an animation when cast, and then releasing the spell towards the direction the player is facing.

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/GameMechanics/PlayerMechanics-SpellAttacksBlueprint.png)
