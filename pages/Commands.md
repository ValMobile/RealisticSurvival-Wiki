This page contains information about Realistic Survival's commands.
While there are not a lot of commands in Realistic Survival, it is still important to know about these. Commands by default are accessible only to administrators, but this restriction can be changed by modifying the player's permissions.
You can use the prefix /realisticsurvival or /rsv. Both will work.
But for simplicity, we will list commands as /rsv.

() = Required <br>
[] = Optional <br>
~ = Relative position <br>
@ = Argument takes in a vanilla target selector (@a, @e, @p, etc.)

| Command                                                            | Description                                                                                                                               | Required Permission                   |
|--------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------|
| /rsv give (player) (item) \[amount]                                | Gives the specified player a Realistic Survival item                                                                                      | realisticsurvival.command.give        |
| /rsv spawnitem (item) (amount) ~(x-pos) ~(y-pos) ~(z-pos) \[world] | Summons a Realistic Survival item at the specified location                                                                               | realisticsurvival.command.spawnitem   |
| /rsv spawnitem                                                     | Only usable by players; summons a Realistic Survival item at the player's location                                                        | realisticsurvival.command.spawnitem   |
| /rsv spawnmob (mob) ~(x-pos) ~(y-pos) ~(z-pos) \[world]            | Summons a Realistic Survival mob at the player's location                                                                                 | realisticsurvival.command.spawnmob    |
| /rsv spawnmob                                                      | Only usable by players; summons a Realistic Survival mob at the player's location                                                         | realisticsurvival.command.spawnmob    |
| /rsv reload                                                        | Reloads the settings defined in the plugin's configuration files; note that some changes may require a restart to take effect             | realisticsurvival.command.reload      |
| /rsv thirst @(player) ~(integer from 0 to 20)                      | Sets the player's thirst to the specified value                                                                                           | realisticsurvival.command.thirst      |
| /rsv temperature @(player) ~(integer from 0 to 25)                 | Sets the player's temperature to the specified value                                                                                      | realisticsurvival.command.temperature |
| /rsv resetitem \[all]                                              | Resets the Realistic Survival item's meta; removes enchants, custom names, and other information depending on the corresponding base item | realisticsurvival.command.resetitem   |
| /rsv updateitem \[all]                                             | Updates the texture and material type of the Realistic Survival item in the player's main hand                                            | realisticsurvival.command.updateitem  |
| /rsv help                                                          | Displays a list of all commands in Realistic Survival                                                                                     | realisticsurvival.command.help        |
| /rsv version                                                       | Displays information about the plugin and server version                                                                                  | realisticsurvival.command.version     |