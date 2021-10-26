# Condition

## Introduce

"Conditional expression" is a single string that can be used in the following scenarios

* Action arguments
* Reaction \(action group\) conditions
* 子图标筛选条件

The execution result should return a Boolean value \(Boolean\), namely `true` / `false`

Currently, TrMenu supports two types of expressions, Kether and JavaScript, as conditional compilation.

Among them, Kether is uniformly called by default \*\(recommended\)

## Use

Kether expressions are used directly, JavaScript expressions need to be prefixed with `js:` and standard variable processing

For example, create a condition that only holds when the player has the permission of `vip.user` or the balance is greater than or equal to `1000`

* Kether: `any [ perm *vip.user money *1000 ]` 
* JavaSctipt: `js: player.hasPermission("vip.user") || utils.hasMoney(player, 1000.0)` 

The format of the two grammars can be further studied through the chapter `SCRIPT`

## Advanced

{% page-ref page="../script/kether.md" %}

{% page-ref page="../script/javascript.md" %}

> In-depth understanding of the structure of the two grammars and application scenarios in TrMenu to make a more powerful menu

