---
description: '[] is a required argument, <> is an optional argument'
---

# Plugin Commands

## Main Command

> The main command of the plugin

* Name：`trmenu` `menu` 
* Permission: `trmenu.access` 

## List

> List loaded menus

* Permission: `trmenu.command.list` 
* Argument
  * &lt;Filter&gt; Filter menu name

## Open

> Open the specified menu

* Permission: `trmenu.command.open` 
* Argument
  * \[ID\]:&lt;Page&gt; Menu name and specified page number
  * &lt;Player&gt; Specify the player, if you leave it blank, you will default to yourself
  * &lt;Menu Argument&gt; The incoming menu argument, used as a variable
* Example
  * `trmenu open Example BlackSKY` Open the Example menu for player BlackSKY
  * `trmenu open Shop:3` Open the Shop menu for yourself, page 3

## Reload

> Reload menu

* Permission: `trmenu.command.reload` 

## Template

> Template creation function, quick layout menu \(currently only supports box containers\)

* Permission: `trmenu.command.template` 
* Argument
  * &lt;Rows&gt; The row size of the menu \(1~6\)

## Action

> Test TrMenu action

* Permission: `trmenu.command.action` 
* Argument
  * \[ID\] The name of the player object performing the action
  * \[Action\] Action line
* Note
  * By default, the action return & related costs will be printed to the commander
  * To hide this print function, you need to put a `#` mark at the top of the action line

## Item

> Management control items

* Permission: `trmenu.command.item` 
* Argument
  * \[Method\] Operation type
    * toJson Convert items in hand to JSON text format
    * fromJson Convert the text content of Argument2 into an item object
    * save Save items to the item repository
    * get Get items from the item repository
    * delete Delete items from the item repository
  * &lt;Value&gt; value

## Sounds

> Preview sound effects

* Permission: `trmenu.command.sounds` 
* Argument
  * &lt;Filter&gt; Filter sound effect name

## Debug

> Debug function

* Permission: `trmenu.command.debug`

