Editing configuration files requires strict adherence to YAML formatting and Spigot API naming conventions. A basic understanding of programming will also be needed. Since most users will not be experienced with YAML, the Spigot API, or programming, explanations have been provided below.

## YAML
“YAML Ain’t markup language" or YAML is a data serialization language designed to be human-friendly and work well with other programming languages for everyday tasks.

YAML syntax is in-depth, but as a user, you will only need to know how to create key-value pairs and add to a list.

### Creating Key-value Pairs
A key-value pair consists of a key, a colon, and its value.

As an example, in `config.yml`, you must add a key containing each of your worlds and a boolean to specify whether a module will be enabled on that world. The key-value pairs would look like this:

`world: true`

`another_world: true`

As another example, in `bauble.yml`, you can add keys and several values to allow certain baubles like the stone of the sea to give you more potion effects. The default customization of the stone of the sea is listed below.
![Default Stone of the Sea Keys](https://raw.githubusercontent.com/ValMobile/RealisticSurvival-Wiki/master/images/config-tutorial-stone-sea-default.png)


To demonstrate, if you wanted the stone of the sea to give you resistance 2 for 20 seconds as well, you would add this key and its values below:
![Resistance Effect Addition](https://raw.githubusercontent.com/ValMobile/RealisticSurvival-Wiki/master/images/config-tutorial-stone-sea-resistance.png)

The result would look like this.
![Edited Stone of the Sea Keys](https://raw.githubusercontent.com/ValMobile/RealisticSurvival-Wiki/master/images/config-tutorial-stone-sea-edited.png)


### Adding to a list
To add to a list, simply add a dash below the bottommost entry followed by the value.

For example, in `notreepunching.yml`, you can add the name of a [material enum constant](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html) to the `WoodBlocks` list to prevent that block from being broken by a player's fists.

The default customization of the `WoodBlocks` list is shown below.

![Default WoodBlocks List](https://raw.githubusercontent.com/ValMobile/RealisticSurvival-Wiki/master/images/config-tutorial-woodblocks-default.png)

To demonstrate, if you wanted the player to also be unable to break oak planks in addition to the above blocks, you would add this below the lowest entry:

![Oak Planks Addition](https://raw.githubusercontent.com/ValMobile/RealisticSurvival-Wiki/master/images/config-tutorial-woodblocks-planks.png)

The result would look like this.
![Edited WoodBlocks List](https://raw.githubusercontent.com/ValMobile/RealisticSurvival-Wiki/master/images/config-tutorial-woodblocks-edited.png)

**Never use tab spaces to move text around in YAML files as this will cause errors. Only use your spacebar to move text around.**

## Essential Java Knowledge

### Data Types
Data is stored in variables which have their own data types. Listed below are common data types you'll work with in configuration files.

`int`
- Represents an integer value
- Possible range of values is -2,147,483,648 to 2,147,483,647.
  Setting an integer to a value less than the minimum value results in the integer becoming positive. Conversely, setting an integer to a value greater than the maximum value results in the integer becoming negative.
- The takeaway is here to never set an integer value to an extremely high positive or negative value as that can cause unintended consequences.
- Ex: `-1`, `0`, `4`

`double`
- Represents a fractional value
- The maximum precision of a double is 15 decimal digits.
- Avoid setting a double to have too many digits as that can cause inaccuracy. Beyond 3 digits, the effects of extra digits will likely be indiscernable.
- Ex: `1.85`, `-2.00`

`boolean`
- Represents a condition
- Only has 2 values:`true` and `false`. This is used in the config files for enabling and disabling features. True corresponds with enabled while false corresponds with disabled.

`String`
- Represents text
- Can hold characters, including characters for foreign languages, allowing for translation
- Must be set off with double or single quotation marks
- You can use single quotation marks to display double quotation marks and vice versa
- Ex: `"Dog"`, `"Double quotes!"`, `"'Single quotes'"`

For more information on data types, see [this tutorial](https://www.w3schools.com/java/java_data_types.asp).

### Enums
An enum is a class that represents a group of constants. Standard Java naming conventions dictate that enum constants are uppercase.

For example, to store office supplies, you could create an enum class called `Supplies` holding the `PEN`, `STAPLER`, and `MARKER` constants.

For more information on enums, see [this tutorial](https://www.w3schools.com/java/java_enums.asp).

## Spigot
The [Spigot API](https://hub.spigotmc.org/javadocs/spigot/) allows developers to easily access and modify aspects of Minecraft.

Information is commonly stored as enum constants. Commonly used enum constants are listed below.

- [Materials](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html)

  - Ex: ACACIA_PLANKS
- [*Potion Effect Types](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/potion/PotionEffectType.html)

  - Ex: DAMAGE_RESISTANCE
- [Entity Types](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/EntityType.html)

  - Ex: ZOMBIE, CAVE_SPIDER


\* Technically are a list of Strings but are functionally identical to enum constants

**Note that the names of Minecraft features may not be the same as their enum constant names. For example, the resistance effect is called DAMAGE_RESISTANCE in code.**

**You must use the exact names of these enum constants in the config files, or errors will occur.**

**Sometimes, enums will be found in quotation marks, especially for the recipe.YML files. In these cases, simply follow the same naming steps above for enums while ensuring they are enclosed in quotation marks.**
