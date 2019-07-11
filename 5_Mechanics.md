# Mechanics

## Movement

Movement is point and click style.
Abilities can include teleporting.

## Mods

### Damage

#### Defensive

| ID    | Effect                                        |
| ----- | --------------------------------------------- |
| #1    | Max health +(15-25)%                          |
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

### Active Abilities

#### Offensive

| Name       | Effect                                    | Cooldown | Radius | Area | Duration | Target |
| ---------- | ----------------------------------------- | -------- | ------ |----- | -------- | ------ |
| Teleport   | Teleport                                  | 10s      | 5m     | 0    | 0s       | Self   |
| Dash       | Dash                                      | 5s       | 5m     | 0    | 1s       | Self   |

#### Defensive

| Name       | Effect                                    | Cooldown | Radius | Area | Duration | Target |
| ---------- | ----------------------------------------- | -------- | ------ |----- | -------- | ------ |
| Heal       | Instantly heal 100hp                      | 10s      | 10m    | 0    | 0s       | Single |
| Patch      | Heal 250hp over time                      | 10s      | 10m    | 0    | 30s      | Single |
| Fortify    | +40% to all resistances                   | 20s      | 10m    | 0    | 5s       | Single |
| Resolute   | +40% to damage                            | 20s      | 10m    | 0    | 5s       | Single |

### Passive Abilities

| Name              | Effect                                                 |
| ----------------- | ------------------------------------------------------ |
| #1                | +50% radius to area                                    |
| #2                | Turn healing to damage and the over way around         |
| #3                | Reduce cooldown by 20%                                 |
| #4                | Divide ability stats by 2 and grant area 3m            |
| #5                | Apply slow 20% on damage                               |

### Base mods

Items have base teks, but additional teks can be installed.

### Items

#### Armors

| Name              | Base mod 1           | Base mod 2           |
| ----------------- | -------------------- | -------------------- |
| RandomName        | #1                   | #2                   |


#### Weapons

## Objects

Objects are either hardcoded or randomly generated.
Wearables such as armors and weapons are craftable. 
Weapons are made out of a base + mods. Allowing for the same weapon type to have different abilities.

### Tek / Object Augmentation - Skills / Effects

Objects (mostly wearables) have "slots" that can be filled by "tek objects".
Slots can be filled by special objects that add active/passive effects, skills can be combined with other tek effects.
The slot - tek object binding can be permanent or non-permanent.

Non-Permanent bindings can be removed and re-structured.
Permanent bindings have the chance of generating much stronger results - but it has a random element.

Tek can add boni aswell as mali.
Example: Heal Tek increases your HP, and adds passive regenration effect to armor. But lowers your attack dmg.

Tek Objects can gain XP when used and level up to create stronger combinations aswell as adding a grinding element.        |

## Actions

Abilities are activated using keyboard keys + clicking.

## Crafting

A **Workbench** allows to break an item into basic components or assemble one from them.
Crafting consumes energy and has random elements, so players have the possibility to consume any aboundant resource to obtain a better version of the craft.

### Recipes

An item is crafted from base resources

### Base resources

### Mods

1. Alien battery
A weird energy source
2. ploup

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
