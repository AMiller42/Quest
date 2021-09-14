# Quest

The commands are different types of challenges, like monsters or terrain.

You can increase your strength to perform more difficult tasks.

If you are not strong enough for a battle, you will be killed and will respawn at home or at an inn, keeping your gold and equipment.

There are different types of conditionals, based on strength, gold, or stack values.

Input is taken whenever you spawn/respawn, and it is added to your bag.

Charms are used as variables, and every charm that holds a nonzero value gives you 1 strength.

Once you are finished with any non-movement/conditional command, treat it as '+' for movement.


## Commands:
### Spawning:
| Icon | Meaning | Function                                                                             |
|:----:|:-------:| ------------------------------------------------------------------------------------ |
| `#`  | Home    | This is your spawn, and your respawn point if you die.                               |
| `i`  | Inn     | Pay 10 gold to change your respawn point. If you don't have enough, it does nothing. |

**Return to your spawn point alive to empty your bag and print the contents.**

### Movement:
| Icon | Meaning    | Function                                                           |
|:----:|:----------:| ------------------------------------------------------------------ |
| `-`  | H. Road    | Horizontal road for traveling.                                     |
| `\|` | V. Road    | Vertical road for traveling.                                       |
| `+`  | C. Road    | Corner road for turning corners or making junctions.               |
| `u`  | Up Road    | Road that only allows northward travel.                            |
| `d`  | Down Road  | Road that only allows southward travel.                            |
| `l`  | Left Road  | Road that only allows westward travel.                             |
| `r`  | Right Road | Road that only allows eastward travel.                             |
| `y`  | Road Fork  | Randomly move in one available direction, except the way you came. |

### Conditionals:
| Icon | Meaning       | Function                                                                  |
|:----:|:-------------:| ------------------------------------------------------------------------- |
| `f`  | Fire Lake     | Can cross if your strength is at least X, otherwise go to the right/left. |
| `t`  | Bridge Troll  | Can cross if you have at least X gold, otherwise go to the right/left.    |
| `p`  | Number Puzzle | Can cross if the top of the bag is 0, otherwise go to the right/left.     |

### Stack Manipulation:
| Icon  | Meaning       | Function                                                                      |
|:-----:|:-------------:| ----------------------------------------------------------------------------- |
| `0-9` | Num Lit       | Store a number in your bag (aka stack).                                       |
| `$`   | Shuffle       | Move the top of your bag to the bottom.                                       |
| `@`   | Drop          | Discard the top of your bag.                                                  |
| `!`   | Transmutation | Pay 2 gold to overwrite the top of your bag with the second item in your bag. |

### Smithing:
| Icon     | Meaning    | Function                                                                                                                         |
|:--------:|:----------:| -------------------------------------------------------------------------------------------------------------------------------- |
| `s`      | Blacksmith | Pay 15 gold to create a charm slot. If you don't have enough, it does nothing.                                                   |
| `ABCXYZ` | Set Charms | Store the top of your bag in the charm; if the charm doesn't exist, make it if you have a free charm slot, otherwise do nothing. |
| `abcxyz` | Get Charms | Get the value from the charm and put it in your bag; if the charm doesn't exist, or is empty, do nothing.                        |

### Output:
| Icon | Meaning        | Function                                           |
|:----:|:--------------:| -------------------------------------------------- |
| `m`  | Message        | Send the top of your bag to STDOUT as a character. |
| `n`  | Number Message | Send the top of your bag to STDOUT as a number.    |

### Battles:
| Icon | Meaning    | Function  | Requires   | Rewards            |
|:----:|:----------:|:---------:|:----------:|:------------------:|
| `^`  | Spike Trap | mak u ded | notin      | u ded              |
| `L`  | Lich       | a ** b    | 5 strength | a * b gold, max 20 |
| `D`  | Dragon     | a % b     | 4 strength | a * b gold, max 15 |
| `G`  | Goblin     | a / b     | 3 strength | a * b gold, max 12 |
| `K`  | Knight     | a * b     | 3 strength | a * b gold, max 10 |
| `W`  | Wolf       | a - b     | 2 strength | a + b gold, max 5  |
| `S`  | Slime      | a + b     | 1 strength | a + b gold, max 4  |
