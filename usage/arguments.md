---
description: TrMenu menu supports the use of arguments with the suffix of the trigger command as a variable
---

# Menu Arguments

## Function Enable

Without any configuration, the menu arguments transfer function is **enabled** by default.

If you encounter command incompatibility, you can turn it off through options

{% page-ref page="../menu/configuration/option.md" %}

## Transfer Method

* Binding custom open command transfer
* Plugin turn on menu command transfer
* Call action second modification

## How To Use

For example, the player’s current arguments are apple, juice, orange, which is an array of size 3

Almost anywhere in the menu can be used as a variable, {0} will return apple, {1} will return juice, and so on

## Note

* By default, closing the menu does not delete existing arguments

