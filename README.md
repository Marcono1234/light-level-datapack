# light-level-datapack
Minecraft datapack which uses the `light` [block predicate](https://minecraft.gamepedia.com/Predicate) introduced in 19w38a and stores the result as scoreboard score.

## Repository layout
The [datapack](/datapack) folder contains the actual datapack as a separate folder.  
This allows separating meta information (like this README file, license, ...) from files used by the datapack.

## Usage
### Initialization
Should happen automatically when the datapack is (re-)loaded. However, it can also be triggered manually by running:
```
/function marcono1234:light_level/_init
```

### Actions
#### Get light level
1. Run for any entity
```
/function marcono1234:light_level/get_light_level
```
2. Afterwards the for that entity the `light_level` score represents the light level where the function was executed
```
/scoreboard players get @s light_level
```

:warning: The light level represents the "visible light (`max(sky-darkening,block)`)". Therefore outside during day it will be 15, making you unable to determine the block light level.

### Removal
To remove all scoreboard objectives added by this datapack, run:
```
/function marcono1234:light_level/_remove
```

Afterwards the datapack folder should be removed since it won't work correctly anymore.  
It can be [initialized](#Initialization) to become functional again.
