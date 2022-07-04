## Prerequisites
To install Realistic Survival, you will need a Spigot or Paper Server (most preferably the latest version).<br>
Forks of either of these should work too, though we only test against Paper and Spigot.

### Realistic Survival 4 Downloads
You can download stable released builds on [Spigot](https://www.spigotmc.org/resources/realistic-survival-1-17-temperature-thirst-baubles.93795/history) or download development builds in the `dev-log` channel of the [Discord server](https://discord.gg/mMt3f4usqK).
Stable builds have been around for quite a while and were thoroughly tested, development builds are the latest builds of Realistic Survival you can get.
If your Server is very reliant on a working build of Realistic Survival, choose a stable build.
But if you want to help contribute to Realistic Survival by reporting issues and helping us identify those more quickly, please consider using a development build (Bug Reports from "stable" builds may be ignored since they are outdated).

**We generally recommend development builds over stable builds, as they are the most recent versions of Realistic Survival. The stable branch is only updated once a month or even less frequent, so fixes may take quite a while to make it into these builds.**

## How to install
Drag and drop the Realistic Survival jar file into your server's */plugins/* directory.
Then, restart your server.<br>
***Do not use /reload, as it can cause intense memory leaks.***

## Configuring Realistic Survival
This part assumes you now have Realistic Survival installed on your server.

When viewing the Realistic Survival plugin folder, you will notice a few different .YML files. Start by viewing *config.yml* in your favorite text editor.
Personally, I recommend [Notepad++](https://notepad-plus-plus.org).

Most of the things in this file are very self explanatory, from enabling certain modules to customizing
various messages.

**Items.yml*** allows you to enable or disable certain items *globally*. If you install multiple addons for Realistic Survival, this file can get very big,
so, a recommendation is to take your time and install addons slowly, if again, you plan on enabling or disabling certain items.

**messages.yml** contains all data for messages when using Realistic Survival. You can edit what the plugin sends a player when a certain event occurs.

**Researches.yml** allows you to edit the XP Values of items in Realistic Survival, as well as their names, you can also disable researching all together if you wish to allow players
the ability to use all of Realistic Survival right off the bat.

**permissions.yml** allows you to define permission nodes for Realistic Survival items to restrict the usage of items based on user's permission levels.

Any changes you make should be saved, then restart the server. Again, ***do not use /reload.*** If you are experiencing issues, and you issued a server reload,
just stop and restart the server, since this fixes most issues.

### Server Optimizations
Here is a full article on how to [Optimize your Realistic Survival Server](https://github.com/ValMobile/RealisticSurvival/wiki/Server-Optimizations)