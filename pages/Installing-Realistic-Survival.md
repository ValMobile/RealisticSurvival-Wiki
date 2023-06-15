## Prerequisites
To install Realistic Survival, you will need a Spigot or Paper Server (most preferably the latest version).<br>
Forks of either of these should work too, though we only test against Paper and Spigot.

### Realistic Survival Downloads
You can download stable released builds on [Spigot](https://www.spigotmc.org/resources/realistic-survival-1-16-dragons-baubles-weapons.93795/history) or download development builds in the `dev-log` channel of the [Discord server](https://discord.gg/mMt3f4usqK).
Stable builds have been around for quite a while and were thoroughly tested, development builds are the latest builds of Realistic Survival you can get.
If your server is very reliant on a working build of Realistic Survival, choose a stable build.
But if you want to help contribute to Realistic Survival by reporting issues and helping us identify those more quickly, please consider using a development build (Bug Reports from "stable" builds may be ignored since they are outdated).

**We generally recommend development builds over stable builds, as they are the most recent versions of Realistic Survival. The stable branch is only updated once a month or even less frequently, so fixes may take quite a while to make it into these builds.**

## How to install
Drag and drop the Realistic Survival jar file into your server's */plugins/* directory.
Then, restart your server.<br>
Next, configure the per-world settings to ensure the plugin is enabled on your desired worlds. See the [customizing the 
install guide](#customizing-the-install) for more information. <br>
Finally, set `Force Unicode Font` to `off` in `Language...` option settings. This is necessary for the temperature and thirst bar to properly display.<br><br>
![Set force unicode font to off](https://raw.githubusercontent.com/ValMobile/RealisticSurvival-Wiki/master/images/force-unicode-font.png)

***If you are migrating from an older version, follow the instructions under the [migration guide](#migrating-from-older-versions) first before installing.***

***Do not use /reload, as it can cause intense memory leaks.***

## Customizing the install
Realistic Survival is divided into various modules, each of which represent the Forge mod of the same name. You can think of Realistic Survival as a "plugin pack" with each module being a plugin. You can enable and disable modules as you wish.

To enable or disable a module,
set `Enabled` to `true` or `false` respectively under the desired module.

Realistic Survival is also per-world, meaning modules can be enabled on certain worlds and disabled on others.

You can enable or disable a module on a world by adding a new entry under `EnabledWorlds` titled with the world name and `true` or `false`, respectively

`lobby: true` --> Enables module on the world named `lobby`

`lobby: false`  --> Disables module on the world named `lobby`

## Migrating from older versions
If you are migrating from an older version, you must reset the Realistic Survival plugins folder.<br>
This means you must stop the server, completely delete the Realistic Survival plugin folder and its contents, and restart the server.<br>
If you wish to transfer your current configuration settings, you must first move your current config files to a separate folder and then retype all the configurations manually.

## Configuring Realistic Survival
This part assumes you now have Realistic Survival installed on your server.

When viewing the Realistic Survival plugin folder, you will notice a few different .YML files and some folders. Start by viewing *config.yml* in your favorite text editor.
Personally, I recommend [Notepad++](https://notepad-plus-plus.org).

Most of the things in this file are self-explanatory, from enabling modules to customizing various messages. For more information on customizing config files, see [this guide](https://github.com/ValMobile/RealisticSurvival/wiki/Editing-Config-Files).

**baubles.yml/iceandfire.yml/etc.yml** allows editing of features of the respective module. This includes enabling and disabling items and recipes, configuring abilities, and performance customizations.

**resources** contains data for all the modules, their items, and recipes

**baubles/iceandfire/etc** contain .YML files for the items and recipes of the respective module

**items.yml** contains the metadata for the items of a module. Most users will not need to edit this file as the default item settings work well, but if you do need to edit, do so carefully, following [this guide](https://github.com/ValMobile/RealisticSurvival/wiki/Editing-Item-YML-Files).

**recipes.yml** contains the data for the recipes of a module. Most users will not need to edit this file as the default recipe settings work well, but if you do need to edit, do so carefully, following [this guide](https://github.com/ValMobile/RealisticSurvival/wiki/Editing-Recipe-YML-Files).

Any changes you make should be saved, then restart the server. Again, ***do not use /reload.*** If you are experiencing issues, and you issued a server reload,
just stop and restart the server since this fixes most issues.

### Server Optimizations
Here is a full article on how to [Optimize your Realistic Survival Server](https://github.com/ValMobile/RealisticSurvival/wiki/Server-Optimizations)
