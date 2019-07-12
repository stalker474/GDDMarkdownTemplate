# Mechanics
## Character

Properties:

| Name              | Description       |
| ----------------- | ----------------- |
| HP                | Life Points       |
| DMG               | Melee Damage      |
| ACC               | Ranged Damage     |
| SPD               | Movement & Attack |
| INI               | Queue Position (async)                  |
| DEF               | Physical Defense (Ballistic & Melee                  |
| DEF HEAT          | Heat Defense                    |
| DEF COLD          | Cold Defense                  |
| DEF ACID          |                   |
| DEF ELEC          |                   | 
| DEF LASR          |                   |


#### SPECIAL DEFS Explanation HEAT, COLD, ACID, ELEC, LASR

Assume Damage is 100 Points.

DEF < 0% 
  Add % Amount to DMG
  ( HEAT DEF -20% means Final Heat Damage is 120 Points )
  
DEF >= 0% && DEF <= 100%
  Subt % Amount from DMG
  ( HEAT DEF 20% means Final Heat Damage is 80 Points )
  
DEF < 100%
  Subt % Amount from DMG
  ( HEAT DEF 120% means Healed by 20 Points )
  


## Status Effects
Status Effects can be activated by Tek and use the Teks level as calculation

| Name              | Duration | Effects Calc      |
| ----------------- | -------- | ----------------------- | -------- |
| BURNING           | DOT + HEAT DMG - self DEF HEAT |          |
| FROZEN            | DOT + COLD        |          |
| ACIDIC            | DOT + ACID                  |
| HEALING           | DOT + MEDIC NANOBOTS        |
| REGENERATING|                   |
| BROKEN (heat,cold,acid,elec,lasr) | |
| SHIELDED (heat, cold, acid, elec, lasr) |  |


## Items

Objects are either hardcoded or randomly generated.
Wearables such as armors and weapons are craftable. 
Weapons are made out of a base stats + optional tek modkits. 
Allowing for the same weapon type to have different abilities.
Weapons and Armor behavior can be altered using 'Tek'.

There are 3 Base Weapon Types:

- Melee Weapons (Range, Speed)
- Ranged Weapons (Range, Speed, Caliber?)
- Activate Tek (Computer? Gauntlet?)

Armor:

- Head
- Body
- Hands

#### Weapons

Weapon Properties
| Name              | Description       |
| ----------------- | ----------------- |
| HP                | Life Points       |

#### Armors

| Name              | Base mod 1           | Base mod 2           | HP         |
| ----------------- | -------------------- | -------------------- | ---------- |
| Basic             | #1                   | #6                   | 400        |
| Basic2            | #1                   | #6                   | 650        |
| Basic3            | #1                   | #7                   | 650        |
| Medium            | #6                   | #7                   | 650        |



#### Drop / Craft Randomizers

Randomizers can be activated on the workbench and apply mods on an item.

1. Alien battery
A weird energy source, adds one random mod on the item without the need for a mod slot, rerolls all mod stats. Modding is locked forever.

2. Desinfector
Removes all but base mods from the item

3. Flash
Rerolls all mods stats

4. Supercharge
Adds a random mod on the item, requires one mod slot.


### Tek / Object Augmentation - Skills / Effects

Objects (mostly wearables) have "slots" that can be filled by "tek objects".
Slots can be filled by special objects that add active/passive effects, skills can be combined with other tek effects.
The slot - tek object binding can be permanent or non-permanent.

Non-Permanent bindings can be removed and re-structured.
Permanent bindings have the chance of generating much stronger results - but it has a random element.

Tek can add boni aswell as mali.
Example: Heal Tek increases your HP, and adds passive regenration effect to armor. But lowers your attack dmg.

Tek Objects can gain XP when used and level up to create stronger combinations aswell as adding a grinding element. 


### Tek Scaling

Most Tek has a quadratic XP curve but offers linear growth 
from MIN to MAX value.

Assume 0 to 10 Levels.

COLD & ARMOR:
COLD DEF +8%
COLD DEF FINAL = COLD DEF BASE * LVL


| LVL       | XP Cost   | COLD & AMOR   |
| --------- | --------- | ------------- |
| 1         | 4         | COLD DEF +8%  |
| 2         | 8         | COLD DEF +16% |
| 3         | 16        | COLD DEF +24% |
| ...       | ...       | ...           |
| 10        | 2048      | COLD DEF +80% |



### Command Tek

| Name       | Description         | Command Effect      | Passive Effect  | Weapon | Armor | 
| ---------- | ------------------- | ------------------- | --------------  |  | -------- | 
| ExoScel    | Increase Melee DMG  | / | 15-45% Heat Def     | 0s       | 
| Heat       | Accelerate Particle | Burn Target 90% Dmg | 15-45% Heat Def     | 0s       | 
| Cold       | Decelerate Particle | Freeze Target       | Cold Absorb     | 0    | 1s       | 
| Acid       | Corrosive Fluid     | Ignore Armor    |                 | 0    | 1s       | 
| Spark      | Electricity         | 
| Shield     | Physical Shield     | Protect Damage   |
| Revenge | | |
|


#### Support tek

| Name              | Effect                                                 | Duration |
| ----------------- | ------------------------------------------------------ | -------- |
| Enlarger beam     | +50% radius to area                                    | 0s       |
| Twister           | Turn healing to damage and the over way around         | 0s       |
| Faster caster     | Reduce cooldown by 20%                                 | 0s       |
| Zone              | Divide ability stats by 2 and grant area 3m            | 0s       |
| Pacifier          | Apply slow 20% on damage                               | 0s       |
| Burner            | Applies 50 fire tick damage                            | 5s       |
| Freezer           | Applies 50 cold tick damage                            | 5s       |
| Shocker           | Applies 50 electric tick damage                        | 5s       |
| Extra battery     | +50% to tick duration                                  | 0s       |
| Alien battery     | +80% to tick duration, random effect                   | 0s       |
| Trigger    | ... over time       | /



### Dual Slot Tek

| Name       | Effect   | Lvl 0    | Radius | Area | Duration | Target |
| ---------- | --------------|--------------|----------- | -------- | ----- |
| All        | Connected Command Tek can Targets All Enemmies            | Self   |
| Infuse     | On Weapon: Add Effect to Normal Attack Armor: add effect to protection   | Self   |
|            | Weapon: Damage Over Time                    | Self   |
| 


### Dual Slot Combination Matrix

|            | Heat | Cold | Radius | Area | Duration | Target |
| ---------- | --------------|--------------|----------- | -------- | ----- |
| Heat       | Connected Command Tek can Targets All Enemmies            | Self   |
| Infuse     | On Weapon: Add Effect to Normal Attack Armor: add effect to protection   | Self   |
|            | Weapon: Damage Over Time                    | Self   |
| 

### Tek Modkit
Tek Mods are generated / predefined sets of effects added to weapons and armor
that define the base properties of a weapon,
they cant be altered by the user

| ID    |  Prefix  | Suffix | Effect         |
| ----- | -------- | ------ | -------------- | --------------------------------------------- |
| #1    | Doctors  | /        | Max health +(15-25)%                          |
| #2    |  /       |  of Life | Health +(300-600)                             | 
| #3    |  Name    |  | Fire damage protection +(20-35)%              |
| #4    |  Name    -----   |   | Cold damage protection +(20-35)%              |
| #5    |  Name    -----   |   | Electric damage protection +(20-35)%          |
| #6    |  Name     -----   |  | Damage reflects on ennemies +(5-8)%           |
| #7    |  Name    -----   |   | -(5-10)% movement +5% all damage protection   |
| #8    | Physical damage +(30-40)%                     |
| #9    | Electrical damage +(30-40)%                   |
| #10   | Cold damage +(30-40)%                         |
| #11   | Fire damage +(30-40)%                         |
| #12   | Movement speed +(15-20)%                      |


## Actions

Use Range / Melee or Tek Command Executer.

## Crafting

A **Workbench** allows to apply mods on an item.
Crafting consumes energy and has random elements, so players have the possibility to consume any aboundant resource to obtain a better version of the craft.
An item has up to 2 base mods + N crafted mods (depends on crafter levels)

### Base resources

- Randomizers
- Energy

## Talking

Talking to online players can be done through voice or chat or quick voice commands.
Talking to offline players can be done by right clicking their avatar and selecting "message", or by referring to them in chat.
Offline players will receive the message on their companion app.

## Combat

Combat is a real time group engagement.
It can be either offensive during exploration, or defensive if the Cargo is under attack.
Player characters have defensive and offensive capabilities based on their class, stats, and equipment. Some are passive, some are active. The combat mechanism should really look like any point and click combat such as LoL.

### Defense

During Phase 2, bandits and scavengers can attack the Cargo to steal resources. Players must try and defend the ship.
For that, some players can stay at the ship during the phase. Players also have the ability to set up traps and automatic defense systems.

### Offense

During ship exploration, the team may encounter survivors. Most of them can be hostile.
