# Mechanics

## Movement

Movement is point and click style.
Abilities can include teleporting.

## Objects

Objects are either hardcoded or randomly generated.
Wearables such as armors and weapons are craftable. 
Weapons are made out of a base stats + mods. 
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

### Mods
### Damage
#### Defensive

| ID    | Effect                                        | Name       |
| ----- | --------------------------------------------- | ---------- |
| #1    | Max health +(15-25)%                          | Strong     |
| #2    | Health +(300-600)                             | 
| #3    | Fire damage protection +(20-35)%              |
| #4    | Cold damage protection +(20-35)%              |
| #5    | Electric damage protection +(20-35)%          |
| #6    | Damage reflects on ennemies +(5-8)%           |
| #7    | -(5-10)% movement +5% all damage protection   |

#### Offensive

| ID    | Effect                                        |
| ----- | --------------------------------------------- |
| #1    | Physical damage +(30-40)%                     |
| #2    | Electrical damage +(30-40)%                   |
| #3    | Cold damage +(30-40)%                         |
| #4    | Fire damage +(30-40)%                         |

### Movement

| ID    | Effect                                        |
| ----- | --------------------------------------------- |
| #1    | Movement speed +(15-20)%                      |

### Base mods

Items have base teks, but additional teks can be installed.

### Items

#### Armors

| Name              | Base mod 1           | Base mod 2           | HP         |
| ----------------- | -------------------- | -------------------- | ---------- |
| Basic             | #1                   | #6                   | 400        |
| Basic2            | #1                   | #6                   | 650        |
| Basic3            | #1                   | #7                   | 650        |
| Medium            | #6                   | #7                   | 650        |

#### Weapons

#### Randomizers

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

### Tek
Command or Passive

Name: Heat
Description: Accelerate Particle Movement


| Name       | Description         | Command Effect   | Passive Effect | Base | XP Curve | Stat Curve | Duration | 
| ---------- | ------------------- | ---------------- | -------------- | ---- | ------ |----- | -------- | 
| Heat       | Accelerate Particle | Burn Target      | Heat Absorb    | 0    | 0s       | 
| Cold       | Decelerate Particle | Freeze Target    | Cold Absorb    | 0    | 1s       | 
| Acid       | Corrosive Fluid     | Damage Over Time |         | 5m     | 0    | 1s       | 
| Spark      | Electricity         | 
| Shield     | Physical Shield     | Protect Damage   |


### Tek Combination Effects

| Name       | Effect   | Lvl 0    | Radius | Area | Duration | Target |
| ---------- | --------------|--------------|----------- | -------- | ----- |
| All        | Connected Command Tek can Targets All Enemmies            | Self   |
| Infuse     | On Weapon: Add Effect to Normal Attack Armor: add effect to protection   | Self   |
|            | Weapon: Damage Over Time                    | Self   |
| 

### Special Tek (Two effects in one, has a name)




#### Abilities tek

**offensive**

| Name       | Effect                                    | Cooldown | Radius | Area | Duration | Target |
| ---------- | ----------------------------------------- | -------- | ------ |----- | -------- | ------ |
| Teleport   | Teleport                                  | 10s      | 5m     | 0    | 0s       | Self   |
| Dash       | Dash                                      | 5s       | 5m     | 0    | 1s       | Self   |

**defensive**

| Name       | Effect                                    | Cooldown | Radius | Area | Duration | Target |
| ---------- | ----------------------------------------- | -------- | ------ |----- | -------- | ------ |
| Heal       | Instantly heal 100hp                      | 10s      | 10m    | 0    | 0s       | Single |
| Patch      | Heal 250hp over time                      | 10s      | 10m    | 0    | 30s      | Single |
| Fortify    | +40% to all resistances                   | 20s      | 10m    | 0    | 5s       | Single |
| Resolute   | +40% to damage                            | 20s      | 10m    | 0    | 5s       | Single |

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

## Actions

Abilities are activated using keyboard keys + clicking.

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
