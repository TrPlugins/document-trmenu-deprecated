---
description: This section requires a certain Java / JavaScript or similar programming foundation to facilitate understanding
---

# JavaScript

## Object

TrMenu’s JavaScript engine currently provides the following objects

* `bukkitServer` 即 Bukkit.getServer\(\)
* `utils` 即 me.arasple.mc.trmenu.module.internal.script.js.Assist.INSTANCE
* `player` I.e. the player itself
* `session` 即 me.arasple.mc.trmenu.module.display.MenuSession

## Function

The JavaScript engine of TrMenu currently provides the following functions

* `vars(String input)`  Return the replacement function variable
* `varInt(String input)` Replace variable and convert to integer

## Note

* TrMenu’s JavaScript will be pre-compiled and cached, and all variables need to be processed through functions
* The symbol for "or" is `||`, and the symbol for "and" is `&&`

## Instance

* Check whether there is permission
  * You can directly call the method of the player object, `player.hasPermission("perm")`



