# RHHS Survival Game Technical Document

This is the coding documentations. If you add some part of code to the game, please be sure to add it to this document.  

There is also a general design documentation available. You can find that document in the same GitHub repo.

## Table of Contents

1. [Entity Stats](#stats)
2. [Ability System](#abilit)
3. [Item System](#items)
4. [Battle System](#battle)
5. [Navigation](#nav)

<a name="stats"></a>

## Entity Stats

### ActiveStatBlock.cs

TThe ActiveStatBlock holds data for a series of stats and modifiers for these stats. This allows for constantly changing stats and the tracking of an original base value. This technically contains pre-initialized stat blocks and modifiers, but should be set manually using SetBaseStats()

#### Start()

Sets the basic stats for a battle entitiy. All of the base stats are one. Edit the following line of code to change base stats:

```csharp
baseStats = new StatBlock(1, 1, 1, 1, 1, 1, 1, 1);
```

The follwowing line of code sets the stats of the battle entity to baseStats:

```chsarp
modifiers = new StatModBlock(baseStats);
```

### StatBlock.cs

This is used to create stat blocks. stat blocks are data structures which contain information about a battle entity's stats.

#### StatBlock()

When this constructor is called, all the stats are set to base level (1). If you want to change the base stat for any of the stats, edit the followng lines of code:

```csharp
public StatBlock()
{
    health = 1;
    energy = 1;
    strength = 1;
    special = 1;
    defense = 1;
    resistance = 1;
    specialDefense = 1;
    specialResistance = 1;
}
```

#### StatBlock(double, double, double, double, double, double, double, double )

This constructor is used to create stat blocks with speceifc stat values. THe code for this part is straight forward:

```csharp 
public StatBlock(double hp, double en, double str, double spe, double def, double res, double sDef, double sRes) {
    health = hp;
    energy = en;
    strength = str;
    special = spe;
    defense = def;
    resistance = res;
    specialDefense = sDef;
    specialResistance = sRes;
}
