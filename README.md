# [Makers Academy](http://www.makersacademy.com) - Week 11 & 12 Final Project

## Paladin's Path - An Open-World Battle Game (Made With Unreal Engine 4)

### [Project Outline](#Outline)
[Overview](#Overview) | [Approach](#Approach) | [Progression](#Progression) | [Features](#Features)

### [Our Game](#Game)

[Story](#Story) | [Level Design](#Level) | [Player Hero](#Hero) | [Enemy Golems](#Golems)

### [Behind The Game (Unreal Blueprints)](#Blueprints)

[Hero Blueprints](#GolemBP) | [Golem Blueprints](#GolemBP)

### [Cinematic Trailer](#Trailer)

---

# <a name="Outline">Project Outline</a>

<div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-PlayerStart..png" width="600"/></div>

## <a name="Overview">Overview</a>

For our final project, our team decided to build a game that would allow us to utilise the programming skills we learnt at Maker's Academy, whilst also exposing us to the game engine Unreal, a leading creation tool used by gaming companies across the globe.

Our original goal with this project was to create a turn-based battle game, where a hero fought against enemies using elemental projectile spells. But as we approached the end of the first week, we decided to pivot the core mechanic of our game to the more contemporary open-world style of game - Where players could freely move around, encounter enemies in different environments throughout the world, and then battle using a dynamic targeting system with a combination of physical and ranged attacks.

## <a name="Approach">Approach</a> 

Maker's Academy teaches us to take a very methodical approach to building a program. Using test-driven development, we were able to visualise the features we wanted to create, create an environment to run our test, setup the variables needed, expect an outcome, and then work towards passing that test in the simplest way possible. 

![Early Stage Test](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/Testing/BattleMechanics-EarlyStage/PaladinsPath-TestingDamageCollagePhoto.jpeg)
*An early-stage view of us testing two core mechanics - projectiles and damage* 

We focused on using agile methodologies throughout the project, organising ourselves with daily stand-ups and retrospectives to ensure we were always aligned and prioritising well at all times. We reviewed each others code before every merge, ensuring that all our tests were passing and we had high coverage of all our features and user edge cases.

## <a name="Progression">Progression</a> 

During our planning process, we created a simple mockup of the map the player would traverse. We planned on having 3 battle zones and a boss zone, indicated by the circles of sand on the left-hand map below. 

![Early Map vs Final Map](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-MapBeforevsAfter.jpeg)
*Map Creation: Day 1 Outline & Final Map*

Our final map on the right follows a very similar design pattern. Players start in the upper-central forested area and make their way through the smoke into a fire-lit cavern, the first battle zone we envisioned. After defeating several enemies in this zone, they move deeper into the rocky cavern to the next battle zone, where they encounter several similar enemies but of a different type. The third battle zone is located amongst frozen wooden huts in the bottom-right of the map. This is the final zone and enemy type the player encounters before moving to the boss zone, inside the castle the player first sees in the distance when they start the game.

During our planning process, we also outlined many features we wanted to include in our game, which I've listed below. The list shows all the features we hoped to implement into our game, and this list will be updated regularly to indicate the features that are finished and implemented into the game, the bugs still present, and some additional features we'd love to implement in the future.

## <a name="Features">Features</a> 

#### Core Level & Game Mechanics
- [x] Open-World Map with multiple environments
- [x] Health System for players and enemies
- [x] Magical attack spells that vary in effectiveness against different types of enemies
- [x] Dynamic Targeting allowing players to lock-on to nearby enemies and switch between targets. 
- [x] Player respawns upon death

#### Player
- [x] Player health bar that changes colour and size depending on the amount of remaining health points
- [x] Players can cast magical attack spells inspired by the elements of Fire, Ice, and Rock
- [x] Players have a physical attack that deals a fixed amount of damage
- [x] Players can use a physical combo sword attack (Animation)
- [ ] Combo attacks multiply attack damage
- [x] Different attack animations for physical and ranged attacks
- [x] Blended movement and attack animations

#### Enemies 
- [x] Enemies have AI that allows them to move randomly within a designated area 
- [x] Enemies have AI that allows them to follow a patrol path of set points in a designated area
- [x] Enemies have AI that allows them to see the player when they're in the enemies line of sight
- [x] Enemies chase and attack the player upon detecting them
- [x] Enemies have a simple physical attack that deals a fixed amount of damage

#### Bugs We're Squishing

- [ ] Combo attacks not working as expected in terms of damage output
- [ ] Overlap with a dead enemy body causes them the mesh to stand upright and then fall

#### Additional Features For The Future

- Player has different animations for each spell
- Enemies have multiple attacks
- Enemies have more advanced AI - More senses, able to raise alarms, and alert other enemies when the player has been detected
- Enabling VR controls

# <a name="Game">Our Game, Paladin's Path</a>

[Story](#Story) | [Level Design](#Level) | [Paladin Hero](#Hero) | [Enemy Golems](#Golems)

## <a name="Story">Story</a>
  
In Paladin's path, you'll move through an open-world with different environments for you to explore. Your goal is to reach the stronghold castle in the distance, where a powerful enemy awaits you:

<a href="https://github.com/BenSheridanEdwards/Makers_Final_Project_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-Start-CastleView-Top.png"><div align="center"><img width="700"  src="https://github.com/BenSheridanEdwards/Makers_Final_Project_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-Start-CastleView-Top.png"/></div></a>

Along your path, you'll encounter enemies, called Golems. Golems are magical being made of inert matter like rock, fire, and ice. That have been animated to life by mysterious forces.

## <a name="Level">Level Design</a>

In Paladin's Path, you'll be guided through multiple environments as you make your way through our world:

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/PaladinsPath/Gallery%20(Images)/BirdseyeViews/PaladinsPath-BirdseyeMap-Markup.png)

1. The Forest
2. Fiery Cavern
3. Dark Cave
4. Snowy Village
5. Castle Stronghold

## <a name="Hero">Player Hero, Paladin</a>

[Movement](#Movement) | [Targeting](#Targeting) | [Health](#HealthBar) | [Physical Attacks](#PhysicalAttacks) | [Magical Attacks](#MagicalAttacks) | [Death & Respawn](#Death)

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-HeroCollage.png)

### <a name="Movement">Movement</a>

You can move around with either A(Left), W(Up), S(Down), D(Right) or the directional arrows on your keyboard. You can also jump by pressing the space bar. 

<a href="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-Movement.gif"><div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-Movement.gif"/></div></a>

### <a name="Targeting">Targeting</a>

The player can also use dynamic targeting, which allows a player to lock-on to the nearest enemy using (T), and switch targets left or right using the (Q) and (E) keys respectively.

<a href="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-DynamicTargeting.gif"><div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-DynamicTargeting.gif"/></div></a>

<p align="center">Targeted enemies are shown by a glowing red ring at the targets feet</p>

### <a name="Heatlh">Health</a>

The hero starts out with 100 health points. Golem attacks deal 10 damage, so decrease your health by 10% for every hit. As your health points decrease, the health bar next to the hero's head will both deplete and change colour from green to amber to red.

<a href="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-HealthBar.gif"><div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-HealthBar-New.gif"/></div></a>

### <a name="PhysicalAttacks">Physical Attacks</a>

As a Paladin, you have a sword to defend yourself against the enemies you face on your journey:

#### Sword Slash 

A single slash of your sword is an effective way to deal damage to your enemies. A single slash deals 20 damage points.

<a href="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-SwordSlash.gif"><div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-SwordSlash.gif"/></div></a>

<p align="center">Press [4] to slash with your sword</p>

#### Sword Slash Combo

Sword slashes can be chained together to multiply their attack power. 3 successful sword slashes will add 40 bonus damage points to your attack.

<a href="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-SwordSlashCombo.gif"><div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-SwordSlashCombo.gif"/></div></a>


<p align="center">Quickly press [4] three times to unleash your sword slash combo attack</p>

### <a name="MagicalAttacks">Magical Attacks<a/>
  
As a Paladin, you can also use magic. You have three spells, fireball, ice shard, and boulder.

#### Fireball

Fireball is a fire-type attack that hurls a ball of fire at your target, dealing 20 damage points. Fireball is weak against earth-type enemies, dealing a reduced 15 damage points, and strong against water-type enemies, dealing a boosted 30 damage points.

<a href="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-FireballSpell.gif"><div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-FireballSpell.gif"/></div></a>


<p align="center">Press [1] to cast Fireball</p>

#### Ice Shard

Ice Shard is a water-type attack that shoots a high-speed shard of ice at your target, dealing 20 damage points. Ice shard is weak against fire-type enemies, dealing a reduced 15 damage points, and strong against earth-type enemies, dealing a boosted 30 damage points.

<a href="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-IceShardSpell.gif"><div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-IceShardSpell.gif"/></div></a>

<p align="center">Press [2] to cast Ice Shard</p>

#### Boulder

Boulder is an earth-type attack that hurls a rock straight at your target, dealing 20 base damage. Boulder is weak against water-type enemies, dealing a reduced 15 damage points, and strong against fire-type enemies, dealing a boosted 30 damage points.

<a href="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-BoulderSpell.gif"><div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-BoulderSpell.gif"/></div></a>

<p align="center">Press [3] to cast Boulder</p>

### <a name="Death">Death & Respawn</a>

In Paladin's Path, when you die, you immediately respawn at the beginning of the level, ready to continue your journey. 

<a href="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-Death.gif"><div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/GameMechanics/PlayerMechanics-Death.gif"/></div></a>

## <a name="Golems">Enemy Golems</a>

[Golem Types](#GolemTypes) | [Golem AI](#GolemAI)

### <a name="GolemTypes">Golems Types</a>

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-GolemCollage.png)

Along Paladin's Path, you'll encounter a variety of different environments where you'll meet different type of golems. Recognising each type is important, as each of your spells deals varying damage depending on the type of golem you're facing.

#### Fire Golem

![Image of Fire Golem](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-FireGolem-FireCave.png)

A Fire Golem's skin is made of molten rock, softened from the heat emanating from their bodies. Because of this, the hero's boulder spell is very effective at disfiguring their bodies shape as well as smothering their flames. The hero's ice shard, however, spell melts before it can pierce it's skin, causing it to less effective. 

![Image of Fiery Caverns & Marked Map](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-FieryCaverns-Birdseye.png)

Fire Golems are found in the fiery caverns between the forest and caves of Paladin's Path. 

#### Ice Golem

![Image of Ice Golem - Tagged](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-IceGolem-IceHuts.png)

An Ice Golem's skin is made of thick shards of ice. Because of this, the hero's fireball spell is very effective at melting their bodies, turning them to slush. The hero's boulder spell, however, freezes before impact and shatters against their dense icy bodies, causing it to less effective. 

![Image of Snowy Village & Marked Map](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-IceArea-Castle.png)

Ice Golems are found in the snowy village between the caves and castle in Paladin's Path.

#### Rock Golem

![Image of Rock Golem - Tagged](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-RockGolem-Forest.png)

A Rock Golem's skin is made of dense boulders that grind against one another as it moves. When the hero's ice shard spell freezes these boulders just before the moment of impact, allowing the force of impact of the shards to shatter the boulder to pieces making it a very effective spell against them. The hero's fireball spell, however, doesn't have anything to burn or melt on their rocky bodies, causing it to less effective. 

![Image of Caves & Marked Map](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/PaladinsPath-Cave-Birdseye.png)

Rock Golems are found in the dark caves between the fiery caverns and snowy village in Paladin's Path. 

### <a name="GolemAI">Golems AI</a>

Golems out in the world are known to have in one of two different ways. They either move randomly within an area or move between spots on a patrol path.

When a Golem sees the hero, they immediately begin chasing the hero, and when they're in range, they attack!

# <a name="Blueprints">Behind The Game (Unreal Blueprints)</a>

[Hero Blueprints](#HeroBP) | [Golem Blueprints](#GolemBP) | [Golem AI](#GolemAI)

## <a name="HeroBP">Hero Mechanics</a> 

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/PaladinsPath/Gallery%20(Images)/Blueprints/HeroBlueprints/Hero-Viewport.png)

### Player Movement

![Game Movement Blueprint](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/GameMechanics/PlayerMechanics-GameInputControlsBlueprint.png)

### Dynamic Targeting

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/GameMechanics/PlayerMechanics-DynamicTargetingMechanic.png)

All credit for this targeting system goes to Grzegorz Szewczyk, whose targeting system we purchased on the Unreal Marketplace. The red targeting ring is our own addition.  

You'll find Grzegorz's dynamic targeting system [here](https://www.unrealengine.com/marketplace/en-US/product/dynamic-targeting). 

### Physical Attacks

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/GameMechanics/PlayerMechanics-MeleeAttacks.png)

### Magical Attacks

In our blueprints, our spells are separated into their respective skills of fire, ice, and rock. Each playing an animation when cast, and then releasing the spell towards the direction the player is facing.

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery%20(Images)/GameMechanics/PlayerMechanics-SpellAttacksBlueprint.png)

Launching the spell projectile

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/PaladinsPath/Gallery%20(Images)/Blueprints/HeroBlueprints/HeroFunction-SkillSpawn.png)

### Death Animation

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/PaladinsPath/Gallery%20(Images)/Blueprints/HeroBlueprints/HeroMechanics-Death.png)

### Receiving Physical Damage

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/PaladinsPath/Gallery%20(Images)/Blueprints/HeroBlueprints/HeroFunction-GetMagicalDamage.png)

### Receiving Magical Damage

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/PaladinsPath/Gallery%20(Images)/Blueprints/HeroBlueprints/HeroFunction-GetPhysicalDamage.png)

### Health Bar

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/PaladinsPath/Gallery%20(Images)/Blueprints/HeroBlueprints/HeroFunction-AdjustHealthBar.png)

## <a name="GolemBP">Golem Mechanics</a> 

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/PaladinsPath/Gallery%20(Images)/Blueprints/GolemBlueprints/Golem-Viewport.png)

### Melee Attack

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/PaladinsPath/Gallery%20(Images)/Blueprints/GolemBlueprints/GolemMechanics-MeleeAttack.png)

### Receive Physical Damage

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/PaladinsPath/Gallery%20(Images)/Blueprints/GolemBlueprints/GolemFunctions-GetPhysicalDamage.png)

### Receive Magical Damage 

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/PaladinsPath/Gallery%20(Images)/Blueprints/GolemBlueprints/GolemFunctions-GetMagicalDamage.png)

### Death Animation

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/PaladinsPath/Gallery%20(Images)/Blueprints/GolemBlueprints/GolemMechanics-Death.png)

## <a name="GolemAI">Golem AI</a>

### Golem Behaviour Tree
![Golem AI](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/PaladinsPath/Gallery%20(Images)/Blueprints/GolemBlueprints/GolemBlueprints-AI-BehaviourTree.png)

### Moving around the world randomly

![https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/PaladinsPath/Gallery%20(Images)/Blueprints/GolemBlueprints/GolemBlueprints-AI-FindRandomLocation.png]

### Patrol Path

#### Follow patrol path

![FollowPatrolPath](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/PaladinsPath/Gallery%20(Images)/Blueprints/GolemBlueprints/GolemBlueprints-AI-FollowPatrolPath.png)

#### Find next path point

![FindPathPoint](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/PaladinsPath/Gallery%20(Images)/Blueprints/GolemBlueprints/GolemBlueprints-AI-FindPathPoint.png)

#### Incrementing to the next path point once a path point has been reached

![IncrementPathIndex](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/PaladinsPath/Gallery%20(Images)/Blueprints/GolemBlueprints/GolemBlueprints-AI-IncrementPathIndex.png)

#### Decrementing down the same patrol path backwards once the patrol path has been completed

![DecrementPathIndex](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/PaladinsPath/Gallery%20(Images)/Blueprints/GolemBlueprints/GolemBlueprints-AI-DecrementPathIndex.png)

#### Loop back to the patrol path start once completed

![LoopPath](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/PaladinsPath/Gallery%20(Images)/Blueprints/GolemBlueprints/GolemBlueprints-AI-LoopPath.png)

### Finding and chasing the player

#### Detecting the player

![CanSeePlayer](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/PaladinsPath/Gallery%20(Images)/Blueprints/GolemBlueprints/GolemBlueprints-AI-PlayerDetection.png)

#### Finding their location

![FindPlayerLocation](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/PaladinsPath/Gallery%20(Images)/Blueprints/GolemBlueprints/GolemBlueprints-AI-FindPlayerLocation.png)

#### Chase the player

![ChasePlayer](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/PaladinsPath/Gallery%20(Images)/Blueprints/GolemBlueprints/GolemBlueprints-AI-ChasePlayer.png)

### Attacking the player when in range

#### Detecting if the player is in range

![](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/PaladinsPath/Gallery%20(Images)/Blueprints/GolemBlueprints/GolemBlueprints-AI-IsPlayerInRange.png

#### Melee Attack

![MeleeAttack](https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/PaladinsPath/Gallery%20(Images)/Blueprints/GolemBlueprints/GolemBlueprints-AI-MeleeAttack.png)

# <a name="Trailer">Cinematic Trailer</a>

Check out our one-minute cinematic trailer on [YouTube](https://youtu.be/R4Vh61J5KaI):

<a href="https://youtu.be/R4Vh61J5KaI"><div align="center"><img src="https://github.com/BenSheridanEdwards/Makers_Paladins_Path/blob/MVPBattle/Gallery(Gifs)/PaladinsPath-CinematicView-1.gif"/></div></a>

If you know a way to host our game online for free so everyone can play, message me on [LinkedIn](https://www.linkedin.com/in/bensheridanedwards/)
