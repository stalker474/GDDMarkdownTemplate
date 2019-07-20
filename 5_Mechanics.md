# Mechanics
## Character

Properties:

| Name              | Description                                        |
| ----------------- | -------------------------------------------------- |
| HP                | Life Points                                        |
| DMG               | Melee Damage                                       |
| ACC               | Ranged Damage                                      |
| SPD               | Movement & Attack                                  |
| INI               | Queue Position (async)                             |
| DEF               | Physical Defense (Ballistic & Melee                |
| LUCK              |                                                    |
| DEF HEAT          | Heat Defense                                       |
| DEF COLD          | Cold Defense                                       |
| DEF ACID          | Acid Defense                                       |
| DEF ELEC          | Electricity Defense                                | 
| DEF LASR          | Laser Defense                                      |


#### SPECIAL DEFS Explanation HEAT, COLD, ACID, ELEC, LASR

Assume Damage is 100 Points.

```DEF < 0%``` 
Add % to DMG
HEAT DEF -20% means Final Heat Damage is 120 Points
  
  
```DEF >= 0% && DEF <= 100%```
Subtract % from DMG
( HEAT DEF 20% means Final Heat Damage is 80 Points )
  
```DEF < 100%```
Add % to HP
( HEAT DEF 120% means Healed by 20 Points )


## Status Effects
Status Effects can be activated by Tek and use the Teks level as calculation.

Status Effects can have Levels and its level is calculated by the LOWEST level of the 
components that triggered it

Duration Increases with LVL

Example:

| Name              | trigger Chance   | Effect                                                                     | 
| ----------------- | ---------------- | -------------------------------------------------------------------------- |
| BURNING           | 10% * LVL        | init: ADD DMG HEAT = ACC * 20% * LVL; trigger: DMG HEAT = ACC * 10% * LVL  |
| FROZEN            | 10% * LVL        | init: ADD DMG COLD = ACC * 10% * LVL; trigger: SKIPTURN                    |
| CORROSION         | 10% * LVL        | init: ADD DMG ACID = ACC * 20% * LVL; trigger: DMG ACID = ACC * 20% * LVL  |
| HEALING           | 10% * LVL        | init: ADD HP = ACC * 15% * LVL;                                            |
| REGENERATING      | 10% * LVL        | init: ADD HP = ACC * 20% * LVL; trigger: DMG ACID = ACC * 10% * LVL        |
| BROKEN            | /                | init: SUB DEF (HEAT, COLD, etc.) = ACC * 5% * LVL                          |
| SHIELDED          | /                | init: ADD DEF (HEAT, COLD, etc.) = ACC * 5% * LVL                          |
| VENGEFUL          | /                | special: attack/command with 90% damage on taking damage                   |
| SACRIFICE         | /                | special: take damage for other players 50% chance + luck                   |


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

### Slots
Slots host Tek on equipable items.

Slot properties:
 - Single: Host a Single Tek Object.
 - Dual: Combination of two Teks. Unlocks new Effects.
 - Offense: Enables Offensive Tek
 - Defense: Enables defense Tek
 - Empty: User defineable Tek
 - Mod: Generated / Non user defined


#### Example:
"Rusty Sword" lvl 5
Mod Slots: up to 3 mod slots
Empty Slots: User Offense Tek Slots: 3 single() () ()

"Rusty Sword" lvl 10
Mod Slots: up to 5 locked mod slots offense AND defense
Empty Slots: User Offense Tek Slots: 3 single / 1 dual : () () () ()=() 


### Tek

Objects (mostly wearables) have "slots" that can be filled by "tek objects".
Slots can be filled by special objects that add active/passive effects, skills can be combined with other tek effects.
The slot - tek object binding can be permanent or non-permanent.

Non-Permanent bindings can be removed and re-structured.
Permanent bindings have the chance of generating much stronger results - but it has a random element.

Tek can add boni aswell as mali.
Example: Heal Tek increases your HP, and adds passive regenration effect to armor. But lowers your attack dmg.

Tek Objects can gain XP when used and level up to create stronger combinations aswell as adding a grinding element. 


#### Slot Randomizers
Triggered by drops and by crafting.

1. Alien battery
A weird energy source, adds one random mod on the item without the need for a mod slot, rerolls all mod stats. Modding is locked forever.

2. Desinfector
Removes all open slot tek

3. Mod Flash
Flashes a specific Mod with level, adds a suffix or prefix "Doctors" Gun, Sword "of Pain"

4. Lucky Flash
Flashes Random Mods and Modslots

5. Supercharge
Adds a random mod on the item, requires one mod slot.



### Tek Scaling

Most Tek has a quadratic XP curve but offers linear growth 
from MIN to MAX value.

Assume 0 to 10 Levels.

COLD & OFFENSE:
COLD DEF +8%
COLD DEF FINAL = COLD DEF BASE * LVL

COLD & DEFENSE:
COLD DEF +8%
COLD DEF FINAL = COLD DEF BASE * LVL


| LVL       | XP Cost   | COLD & AMOR   |
| --------- | --------- | ------------- |
| 1         | 4         | COLD DEF +8%  |
| 2         | 8         | COLD DEF +16% |
| 3         | 16        | COLD DEF +24% |
| ...       | ...       | ...           |
| 10        | 2048      | COLD DEF +80% |


### Base Tek List

Example:
Command HEAT LVL 3 
= HEAT DAMAGE 9% * 3 + 9% chance of BURNING status

| Name       | Description         | Command Effect      | Passive Effect  | Offense Slot         | Defense Slot         | 
| ---------- | ------------------- | ------------------- | --------------  | -------------------- | -------------------- | 
| HEAT       | Accelerate Particle | BURNING             | /               | +5 % DMG HEAT * LVL  | +5 % DEF HEAT * LVL  | 
| COLD       | Decelerate Particle | FROZEN              | /               | +5 % DMG COLD * LVL  | +5 % DEF COLD * LVL  | 
| ACID       | Corrosive Fluid     | CORROSION           | /               | +5 % DMG ACID * LVL  | +5 % DEF ACID * LVL  | 
| SPARK      | Electricity         | ELECTORCUTE         | /               | +5 % DMG ELEC * LVL  | +5 % DEF ELEC * LVL  | 
| SHIELD     | Physical Shield     | Status: SHIEDED     | /               | /                    | +5 % DEF DMG * LVL   | 
| REVENGE    | Retaliate           | Status: VENGEFUL    | /               | /                    | /                    | 
| EXOSKEL    | Increase Melee DMG  | /                   | /               | 0                    | 1s                   | 
| HP         | Increase HP         |                     | /               | 0                    | 1s                   | 
| NANOBOTS   | Add Range to status tek |                 | /               | 0                    | 1s                   | 
| REFLECTOR  | Add Range to status tek |                 | /               | 0                    | 1s                   | 
| DEFLECTOR  | Add Range to status tek |                 | /               | 0                    | 1s                   | 



### Dual Slot Tek

| Name       | Description         | Command Effect      | Passive Effect  | Offense Slot         | Defense Slot         | 
| ---------- | ------------------- | ------------------- | --------------  | -------------------- | -------------------- | 
| All        | ------------------- | ------------------- | --------------  | -------------------- | -------------------- | 
| Infuse     | ------------------- | ------------------- | --------------  | -------------------- | -------------------- | 


### Dual Slot Combination Matrix

|            | Heat | Cold | Radius | Area | Duration | Target |
| ---------- | ---- | ---- | ------ | ---- | -------- | ------ |
| Heat       | /    | /    | Radius | Area | Duration | Target |
| Cold       | /    | /    | Radius | Area | Duration | Target |
|            | Heat | Cold | Radius | Area | Duration | Target |
|            | Heat | Cold | Radius | Area | Duration | Target |

### Tek Modkit
Mods are generated / predefined sets of Tek added to weapons and armor.
that define the base properties of a weapon,
they cant be altered by the user

Example Generation:

Flash:
Craft the same weapon but add a Specific Tek Mod Prefab

Lucky Flash:

Roll: # of Slot (1-4)
Roll: Mod 1 Content, Mod 1 Level
Roll: Mod 2 Content, Mod 2 Level
etc.


### Tek Modkit List

| Name              | Effect                                                 | Suffix/Prefix |
| ----------------- | ------------------------------------------------------ | ------------- |
| Enlarger beam     | +50% radius to area                                    | 0s            |
| Twister           | Turn healing to damage and the over way around         | 0s            |
| Faster caster     | Reduce cooldown by 20%                                 | 0s            |
| Zone              | Divide ability stats by 2 and grant area 3m            | 0s            |
| Pacifier          | Apply slow 20% on damage                               | 0s            |
| Burner            | APPLY BURNING LVL 5                                    |               |
| Extra battery     | +50% to tick duration                                  | Energized...  |
| Alien battery     | +80% to tick duration, random effect                   | Alien...      |
| Doctors           | HP TEK LVL 5 && APPLY REGENERATING LVL 5               | Doctors...    |
| Fire Shield       | Fire damage protection +(20-35)%                       | ...of Fire    |
| Deflector Matrix  | REFLECT LVL 5                                          | ...of Fire    |
 


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
