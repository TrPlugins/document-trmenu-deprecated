---
description: 本节需要有一定的 Java / JavaScript 或类似编程基础方便理解
---

# JavaScript

## 对象

TrMenu 的 JavaScript 引擎目前提供以下对象

* `bukkitServer` 即 Bukkit.getServer\(\)
* `utils` 即 me.arasple.mc.trmenu.module.internal.script.js.Assist.INSTANCE
* `player` 即 玩家本身
* `session` 即 me.arasple.mc.trmenu.module.display.MenuSession

## 函数

TrMenu 的 JavaScript 引擎目前提供以下函数

* `vars(String input)`  返回替换函数变量
* `varInt(String input)` 替换变量并转换为整型

## 注意

* TrMenu 的 JavaScript 均会预编译缓存，一切变量使用都需要通过函数处理
* 表示 “或” 的符号为 `||` , 表示 “与” 的符号为 `&&`

## 实例

* 判断有无权限
  * 可直接调用 player 对象的方法，`player.hasPermission("perm")` 

## utils

{% embed url="https://github.com/TrPlugins/TrMenu/blob/stable/v3/plugin/src/main/kotlin/trplugins/menu/module/internal/script/js/Assist.kt" caption="TrMenu/Assist.kt" %}

