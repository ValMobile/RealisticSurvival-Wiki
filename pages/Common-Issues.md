<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
<details>
<summary>Table of Contents</summary>

- [Temperature and thirst bar not displaying properly](#temperature-and-thirst-bar-not-displaying-properly)
- [Temperature does not change and thirst does not drain](#temperature-does-not-change-and-thirst-does-not-drain)
- [Uncraftable Spartan weapon recipes](#uncraftable-spartan-weapon-recipes)
- [Plugin not functioning on certain worlds](#plugin-not-functioning-on-certain-worlds)
- [Armor models not displaying](#armor-models-not-displaying)

</details>
<!-- END doctoc generated TOC please keep comment here to allow auto update -->

This page contains useful information about common in-game issues and how to resolve them.<br>

**NOTE: some issues are actually multiple separate issues, indicated by a division in troubleshooting steps. They have been moved under a main issue for ease of access.
If you've followed the troubleshooting guide with no success, consider [filing a bug report!](https://github.com/ValMobile/RealisticSurvival/wiki/How-to-report-bugs)**

## Temperature and thirst bar not displaying properly
Several factors can cause the temperature and thirst bar to not show up correctly in the HUD. 
Most issues are caused by not installing the plugin or customizing the per-world settings correctly, 
so, first, review the [guide on installing the plugin](https://github.com/ValMobile/RealisticSurvival/wiki/Installing-Realistic-Survival) to make sure you've followed the steps correctly.

### How to fix this (White rectangles)
Set `Force Unicode Font` to `off` in `Language...` option settings.

### How to fix this (Invisible bar)
Ensure you have installed the plugin correctly and configured the per-world settings so that the Tough as Nails module is enabled on your worlds.

The bar will not display if you are in creative or spectator mode. If you are in creative or spectator mode, switch to survival mode via
>/gamemode survival

### How to fix this (Off-center bar)
Issues related to an off-center temperature and thirst bar are not natively caused by Realistic Survival.

Ensure that you do not have another plugin enabled that modifies the actionbar. 
If you do find one, check if it has a config option to disable features that use the actionbar.

## Temperature does not change and thirst does not drain
Your temperature will fluctuate based on your surrounding environment, including the biome, certain blocks, daylight cycles, weather, and whether or not you're in an enclosed area.
Due to these various factors, it is possible that your environment is temperate enough so that your temperature naturally will not change.

On the other hand, your thirst will always drain, so an unchanged thirst bar indicates an issue.

### How to fix this
Deop yourself (if you are opped) and remove any temperature or thirst resistant permissions.

Opped players by default are immune to thirst drain and temperature changes.

Obviously, players with temperature and thirst immunity permissions will be unaffected by temperature and thirst changes.

Listed below are the temperature and thirst immunity permissions that could be causing issues:
- realisticsurvival.toughasnails.resistance.cold
  - Prevents player from getting cold
- realisticsurvival.toughasnails.resistance.colddamage
  - Prevents player from taking damage from hypothermia
- realisticsurvival.toughasnails.resistance.coldvisual 
  - Prevents player from receiving visual effects from hypothermia
- realisticsurvival.toughasnails.resistance.hot 
  - Prevents player from getting hot
- realisticsurvival.toughasnails.resistance.hotdamage 
  - Prevents player from taking damage from hyperthermia
- realisticsurvival.toughasnails.resistance.hotvisual 
  - Prevents player from receiving visual effects from hyperthermia
- realisticsurvival.toughasnails.resistance.thirst 
  - Prevents player from getting thirsty
- realisticsurvival.toughasnails.resistance.thirstdamage 
  - Prevents player from taking damage from dehydration

## Uncraftable Spartan weapon recipes
This issue is very common and caused by Spigot displaying a vanilla stick texture in the recipe instead of handle and pole textures.

### How to fix this
Use a handle or pole instead of a normal stick in the recipe.

Weapons that require handles include:
- Daggers
- Greatswords
- Longswords
- Katanas
- Sabers
- Rapiers
- Longbows
- Crossbows
- Throwing Knives
- Tomahawks
- Battleaxes
- Maces
- Hammers

Weapons that require poles include:
- Quarterstaffs
- Halberds
- Pikes
- Javelins
- Glaives
- Spears

Weapons that require handles and poles include:
- Lances

## Plugin not functioning on certain worlds
Realistic Survival will sometimes appear to be enabled but have no functionality on certain worlds.
Most of the time, this error is caused by not configuring the per-world settings correctly.

### How to fix this
Install the plugin correctly and configure the per-world settings so that the desired modules are enabled on your worlds.

## Armor models not displaying
Displaying custom armor models directly through vanilla Minecraft is currently impossible without hacky implementations or client-side mods.

That said, the resource pack is automatically configured to display custom armor models using Optifine's CIT texture system.

### How to fix this
Install Optifine or, alternatively, OptiFabric as the resource pack relies on Optifine's CIT texture system to work.