<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
<details>
<summary>Table of Contents</summary>

- [Temperature and thirst bar not displaying properly](#temperature-and-thirst-bar-not-displaying-properly)
- [Temperature does not change and thirst does not drain](#temperature-does-not-change-and-thirst-does-not-drain)
- [Plugin not functioning on certain worlds](#plugin-not-functioning-on-certain-worlds)
- [Wooden logs and planks don't drop anything](#wooden-logs-and-planks-don't-drop-anything)
- [Cannot craft wooden planks and sticks](#cannot-craft-wooden-planks-and-sticks)
- [Textures not displaying](#textures-not-displaying)
- [Armor models not displaying](#armor-models-not-displaying)

</details>
<!-- END doctoc generated TOC please keep comment here to allow auto update -->

This page contains useful information about common in-game issues and how to resolve them.<br>

**NOTE: some issues are actually multiple separate issues, indicated by a division in troubleshooting steps. They have been moved under a main issue for ease of access.
When following the troubleshooting steps, ensure you restart the server after changing a configuration file.
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

### How to fix this (Blinking bar)
Set `VisualTickPeriod` in `toughasnails.yml` to a reasonably low value (e.g. `5`).

Ensure that you do not have another plugin enabled that modifies the actionbar (e.g. ItemsAdder, Oraxen).
If you do find one, check if it has a config option to disable features that use the actionbar.

### How to fix this (Off-center bar)
Issues related to an off-center temperature and thirst bar are not natively caused by Realistic Survival.

Ensure that you do not have another plugin enabled that modifies the actionbar (e.g. ItemsAdder, Oraxen). 
If you do find one, check if it has a config option to disable features that use the actionbar.

## Temperature does not change and thirst does not drain
Your temperature will fluctuate based on your surrounding environment, including the biome, certain blocks, daylight cycles, weather, and whether you're in an enclosed area.
Due to these various factors, it is possible that your environment is temperate enough so that your temperature naturally will not change.

On the other hand, your thirst will always drain, so an unchanged thirst bar indicates an issue.

### How to fix this
Remove any temperature or thirst immunity permissions. You can review the permissions [here](https://github.com/ValMobile/RealisticSurvival/wiki/Permissions).

## Plugin not functioning on certain worlds
Realistic Survival will sometimes appear to be enabled but have no functionality on certain worlds.
Most of the time, this error is caused by not configuring the per-world settings correctly.

### How to fix this
Install the plugin correctly and configure the per-world settings so that the desired modules are enabled on your worlds.

## Wooden logs and planks don't drop anything
Wooden logs and planks will not drop anything when broken without an axe. This feature adds realism and increases difficulty.

### How to fix this
This mechanic is not a bug, but if you wish to disable it, you can set `Enabled` to `false` under `PreventPunchingWood` in the `notreepunching.yml` config file.

## Cannot craft wooden planks and sticks
The vanilla Minecraft wooden plank and stick recipes have been disabled. This feature adds realism and increases difficulty.

### How to fix this
This mechanic is not a bug, but if you wish to disable it, you can set `DisablePlankRecipes` and `DisableStickRecipes` to `false` under `Lumberjack` in the `notreepunching.yml` config file.

## Textures not displaying
Several factors can cause textures not to display correctly.
Most issues are caused by not installing the plugin or equipping the resource pack correctly,
so, first, review the [guide on installing the plugin](https://github.com/ValMobile/RealisticSurvival/wiki/Installing-Realistic-Survival) to make sure you've followed the steps correctly.

### How to fix this (No textures)
This issue is caused by not equipping the resource pack. Review the [installation instructions](https://github.com/ValMobile/RealisticSurvival/wiki/Installing-Realistic-Survival) as you may have installed the plugin incorrectly.
The resource pack will auto-enable by default. There should be no reason for you to disable it unless you are using another server resource pack already.

So, first, set `Enabled` to `true` under `ResourcePack` in `config.yml`. This step should solve the issue. If it doesn't, you have another resource pack interfering with Realistic Survival's,
so combine the resource packs together and set that combination as your server resource pack.

### How to fix this (Incorrect textures/Invalid textures/Purple and black squares)
This issue usually occurs when an item created in a very old version of the plugin is ported to a newer version of the plugin.
Try running /rsv updateitem (requires the appropriate permission) while holding the item in your main hand.
If this does not solve the issue, you will have to discard your item as it is too old to migrate.

Occasionally, texture issues are caused by other plugins and/or datapacks interfering with the server resource pack.
Plugins like ItemsAdder and Oraxen are known to cause issues.
If you have these plugins, you'll have to combine the resource packs together and set that combination as your server resource pack.

### How to fix this (Armor textures)
See [this](#armor-models-not-displaying) for the solution to armor model issues.

## Armor models not displaying
Displaying custom armor models directly through vanilla Minecraft is currently impossible without hacky implementations or client-side mods.

That said, the resource pack is automatically configured to display custom armor models using Optifine's CIT texture system.

### How to fix this
Install Optifine or, alternatively, OptiFabric as the resource pack relies on Optifine's CIT texture system to work.