---
description: After installing this plugin for the first time, some files will be generated in the plugin directory
---

# Configuration

## Document

{% tabs %}
{% tab title="lang/zh\_CN.yml" %}
TLocale language file, you can edit almost all messages of this plugin
{% endtab %}

{% tab title="data/globalData.yml" %}
Where the global cache data variables are stored

Do not edit when the server is enabled
{% endtab %}

{% tab title="data/itemRepository.yml" %}
Where the item repository data is stored

Do not edit when the server is enabled
{% endtab %}

{% tab title="menus" %}
The default menu loading directory

The menu file (YAML) can be placed in this directory or its subdirectories, and it will be automatically loaded by the plug-in
{% endtab %}

{% tab title="settings.yml" %}
The main configuration file of TrMenu
{% endtab %}
{% endtabs %}

## 设置

{% code title="settings.yml \(v3.0 BETA-2\)" %}
```yaml
#
# Plugin options
#
Options:
  # Performance mode: High, Normal, Low
  Running-Performance: Normal
  # Multithreading
  Multi-Thread: true
  # Load menu asynchronously
  Async-Load-Menus: true
#
# Plugin player data storage method
#
Database:
  # storage method: LOCAL, MONGODB
  Method: LOCAL
  Url:
    Client: 'mongodb://localhost:3307'
    Database: trixey
    Collection: menu

#
# Menu loader
#
Loader:
  # Custom load directory
  Menu-Files:
    - 'plugins/CustomMenusFolder'

#
# Menu Settings
#
Menu:
  # 选项
  Settings:
    # The minimum interval for the bound item to trigger the opening of the menu (to prevent frequent brushing)
    Bound-Item-Interval: 3
  # Icon
  Icon:
    # Whether to enable sub-icons to inherit the main icon by default
    Inherit: false
    # Display items
    Item:
      # Default Name color
      Default-Name-Color: "&7"
      # Default Lore color
      Default-Lore-Color: "&7"
      # Priority coloring
      # If turned on, first replace the color and then process the function variable
      Pre-Color: false

#
# Action related
#
Action:
  # Catcher
  Inputer:
    # Cancellation word (regular)
    Cancel-Words:
      - 'cancel|quit|end'
      - 'q'

#
# Actions performed by quick binding
# For specific notes, please refer to the [USAGE-Quick Binding] chapter
#
Shortcuts:
  Offhand: []
  Sneaking-Offhand:
    - condition: 'perm *trmenu.shortcut'
      execute: 'open: Example'
      deny: 'return'
  Right-Click-Player: 'open: Profile'
  Sneaking-Right-Click-Player: [ ]
  PlayerInventory-Border-Left: [ ]
  PlayerInventory-Border-Right: [ ]
  PlayerInventory-Border-Middle: [ ]

#
# Register custom commands
# Please refer to the [USAGE-Command Registration] chapter for specific notes
#
RegisterCommands:
  openMenus:
    aliases: [ ]
    permission: null
    execute:
      - 'tell: &7Argument `example` Required!'
    arguments:
      example: 'open: example'
```
{% endcode %}

## Language

TODO

