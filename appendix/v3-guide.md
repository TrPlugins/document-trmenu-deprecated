---
description: This document is taking you to quickly understand TrMenu 3.0 and upgrade steps
---

# Upgrade Wizard

## Update Content

### Bottom Layer

* Configuration file & language file format are all redesigned
* 90% of the code is completely rewritten, aiming at the ultimate performance experience
* The virtual container structure of the package is completely remade, faster & more flexible

#### Function

* Added `Free-Slot` item to unlock items in the target slot (unstable)

#### Material

```text
head:%player_name% head:BlackSky
head:eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvNDRmNDUyZDk5OGVhYmFjNDY0MmM2YjBmZTVhOGY0ZTJlNjczZWRjYWUyYTZkZmQ5ZTZhMmU4NmU3ODZlZGFjMCJ9fX0=
head:44f452d998eabac4642c6b0fe5a8f4e2e673edcae2a6dfd9e6a2e86e786edac0

repo:myCustomItem
repo:%custom_variable_whichreturnstheid%

source:HDB:random
source:ORAXEN:itemId

{json Content}
```

* Special items are no longer needed { } 、&lt;&gt; etc.
* HeadDatabase / Oraxen / **ItemsAdder**\(新\) ****Other item hooks need to be in ItemSource format
* SkinsRestorer hook and heads of custom materials are all integrated into the player’s head, and will be automatically detected and processed

#### Condition

Conditional detection is the biggest change part of this update

Now the condition abandoned the "smart expression" provided by TrMenu 2，and only supports **Kether** and **JavaScript** statements. Kether statement is used by default

* **Kether**
  * Kether official documentation will provide instructions for use
* **JavaScript**
  * Js prefix is required, for example `condition: 'js: player.getHealth() > 20.0'`
  * Full cache, does not support dynamic compilation of variables, use of variables requires a set of functions
  * **Objects** is provided by default
    * `player`
    * `bukkitServer`
    * `utils`
  * **Function** is provided by default
    * `vars("STRING")` Compile variables and return String
    * `varInt("STRING")` Compile variable, return integer

> Reasons for deprecating v2:
>
> ```text
> 1. Bloated and inflexible, many errors caused by imperfections
> 2. No standard caching, variable processing
> ```

#### Function

{% page-ref page="../usage/functions.md" %}

#### Action

* **ActionBound** The \_\|\|\_ left over from v1 is discarded, and at this stage, it is unified as `&&&`
* **Title** The unified specification format of the action is
  * `title: [Title] [Subtitle] [Fade In] [Stay] [Fade Out]`
  * Title text application that contains spaces · Enclose
* **Refresh** Actions can now specify icon slots to refresh a single icon
* **ActionOption** Action parameters are now recommended to use the format definition of `{[TYPE]=[VALUE]}`
* **InputCatcher** The standard parameters of the catcher now include `type`, `start`, `cancel`, `end`. The special parameters are `display`, `itemLeft`, `itemRight`, `content` & add BOOK type catcher

#### Data

* Meta & Data function module is rewritten, and GlobalData is added to set global variables
* Can be called by function

#### Command

* Item repo and item conversion are combined into one command
* Sound preview function is rewritten based on ReceptacleAPI
* Rewrite the performance loss statistics function
* Menu list formatting
* Debug function rewrite Mirror & Dump function integrated under Debug

{% page-ref page="../usage/command.md" %}

#### API

* Provide `ReceptacleAPI` to create custom virtual containers, use cases can refer to `me.arasple.mc.trmenu.module.internal.command.impl.CommandSounds`

## Start

Because the configuration & language structure of v3.x and v2.x are completely incompatible, the menu is partially compatible

Therefore, in order to better complete the upgrade, please rename the old TrMenu folder for future use.

Then replace the plugin to generate a new TrMenu folder

## Configuration

Quickly understand the configuration structure according to this Wiki & configure as needed

## Menu

Point of incompatibility

* Built-in functions & conditions & scripts
* Part of the hook material writing
* \(v1.x \) TITLE action writing
* \(v1.x\) Action option binding `_||_`

Solution

* Make sure to read the new version of the document completely
* Rewrite conditions according to the new format (for JavaScript, string related expressions need to be processed)

## Q & A

#### Why not provide one-click migrate

This update discards most of the bloated design of v2 & rewrites almost all modules

Especially when it comes to scripts and conditions, the migration function is not easy to do

If you only use some simple conditions or JavaScript forms, it is relatively easier to upgrade

For example, application replacement function `hasPerm.` -> `perm *`

#### Is it necessary to upgrade

For a large-scale server that is running and a large menu volume, it is not necessary in the short term

New servers or menus with low demand (less conditional expressions) are recommended to upgrade as soon as possible

The old version has ceased maintenance and support, and no longer deals with remaining issues



