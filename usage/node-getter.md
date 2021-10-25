---
description: TrMenu also supports getting the nodes in the configuration file as variables to avoid writing the same content repeatedly.
---

# Node variable

## Usage
```text
{node: <key>}

E.g:
{node: Title}
 -> Get the Title of the menu
 
{node: Icons.A.display.name}
 -> Get the display name of icon A
 
{node: Icons.@iconid@.display.name}
 -> If the variable exists in any area of B that supports function variables, the display name of icon B will be obtained
```
* **Note**: When getting the node, pay attention to whether the case matches as much as possible
* As a function variable, it can be used in any area that supports variables
* **@iconid@** is a static variable, which will be parsed as the id of the icon under the icon

## 示例
```yaml
Title: '子服列表'

Layout:
  - '012345678'

Icons:
  0:
    display:
      material: 'wool'
      name: '&3前往 => &b{node: Icons.@iconid@.properties.name}'
      lore:
        - '&7有关信息: {node: Icons.@iconid@.properties.desc}'
        - ''
    actions:
      all:
        - 'server: {node: Icons.@iconid@.properties.server}'
    properties:
      name: '子服-@iconId@'
      server: 'server-@iconId@'
      desc: '这里有许多友爱的玩家们'
  1:
    display:
      material: 'wool'
      name: '&3前往 => &b{node: Icons.@iconid@.properties.name}'
      lore:
        - '&7有关信息: {node: Icons.@iconid@.properties.desc}'
        - ''
    actions:
      all:
        - 'server: {node: Icons.@iconid@.properties.server}'
    properties:
      name: '子服-@iconId@'
      server: 'server-@iconId@'
      desc: '这里风和日丽'
  2:
    display:
      material: 'wool'
      name: '&3前往 => &b{node: Icons.@iconid@.properties.name}'
      lore:
        - '&7有关信息: {node: Icons.@iconid@.properties.desc}'
        - ''
    actions:
      all:
        - 'server: {node: Icons.@iconid@.properties.server}'
    properties:
      name: '子服-@iconId@'
      server: 'server-@iconId@'
      desc: '这里危机重重'
  3:
    display:
      material: 'wool'
      name: '&3前往 => &b{node: Icons.@iconid@.properties.name}'
      lore:
        - '&7有关信息: {node: Icons.@iconid@.properties.desc}'
        - ''
    actions:
      all:
        - 'server: {node: Icons.@iconid@.properties.server}'
    properties:
      name: '子服-@iconId@'
      server: 'server-@iconId@'
      desc: '这里适合养老'
  4:
    display:
      material: 'wool'
      name: '&3前往 => &b{node: Icons.@iconid@.properties.name}'
      lore:
        - '&7有关信息: {node: Icons.@iconid@.properties.desc}'
        - ''
    actions:
      all:
        - 'server: {node: Icons.@iconid@.properties.server}'
    properties:
      name: '子服-@iconId@'
      server: 'server-@iconId@'
      desc: '这里怪物很多'
  5:
    display:
      material: 'wool'
      name: '&3前往 => &b{node: Icons.@iconid@.properties.name}'
      lore:
        - '&7有关信息: {node: Icons.@iconid@.properties.desc}'
        - ''
    actions:
      all:
        - 'server: {node: Icons.@iconid@.properties.server}'
    properties:
      name: '子服-@iconId@'
      server: 'server-@iconId@'
      desc: '这里适合生电'
  6:
    display:
      material: 'wool'
      name: '&3前往 => &b{node: Icons.@iconid@.properties.name}'
      lore:
        - '&7有关信息: {node: Icons.@iconid@.properties.desc}'
        - ''
    actions:
      all:
        - 'server: {node: Icons.@iconid@.properties.server}'
    properties:
      name: '子服-@iconId@'
      server: 'server-@iconId@'
      desc: '这里经常崩服'
  7:
    display:
      material: 'wool'
      name: '&3前往 => &b{node: Icons.@iconid@.properties.name}'
      lore:
        - '&7有关信息: {node: Icons.@iconid@.properties.desc}'
        - ''
    actions:
      all:
        - 'server: {node: Icons.@iconid@.properties.server}'
    properties:
      name: '子服-@iconId@'
      server: 'server-@iconId@'
      desc: '这里有剧情'
  8:
    display:
      material: 'wool'
      name: '&3前往 => &b{node: Icons.@iconid@.properties.name}'
      lore:
        - '&7有关信息: {node: Icons.@iconid@.properties.desc}'
        - ''
    actions:
      all:
        - 'server: {node: Icons.@iconid@.properties.server}'
    properties:
      name: '子服-@iconId@'
      server: 'server-@iconId@'
      desc: '这里可以上天'
```