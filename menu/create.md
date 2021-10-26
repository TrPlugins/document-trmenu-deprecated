# Create

## Base

The menu of TrMenu is configured, read and loaded in **YAML** \(.yml\) file format

Therefore, to create a new menu, you can start by creating a new YAML file

## Path

The menu file can be placed in the default menu directory \(menus\) or in a custom path \(you need to configure yourself\)

The menu file name \(excluding the extension suffix\) is the unique ID of the menu.

Menus with duplicate IDs will still be loaded, but it will affect the normal operation of the open command

## Configuration

The configuration items of the menu will be analyzed in detail in the following chapters

Please browse the sample mode provided below to quickly understand the basic structure of the menu

```yaml
# Title displayed by the inventory
Title: 'TrMenu'

# Refresh time of inventory title
Title-Update: 40

# Menu layout
Layout: []

# Menu layout - player inventory
PlayerInventory: []

# Menu options
Options:
  # Whether to enable the argument
  Arguments: false
  # Default argument filling
  Default-Arguments: [ ]
  # Free slot
  Free-Slots:
    - 71
    - 72
  # Default page number
  Default-Layout: 0
  # Whether to hide player inventory items
  Hide-Player-Inventory: false
  # Minimum click delay
  Min-Click-Delay: 200
  # Menu dependent PlaceholderAPI extension
  Depend-Expansions: [ 'server', 'player', 'progress', 'animations' ]

# Menu binding
Bindings:
  # Command
  Commands:
    - '(?i)example(-)?(gui)?(s)?'
  # Items
  Items:
    - 'material:compass'
    - 'material:clock,lore:OPEN_MENU'
    - 'texture:eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvNDRmNDUyZDk5OGVhYmFjNDY0MmM2YjBmZTVhOGY0ZTJlNjczZWRjYWUyYTZkZmQ5ZTZhMmU4NmU3ODZlZGFjMCJ9fX0='

# Menu event reaction
Events:
  # Open event
  Open:
    - condition: 'perm *trmenu.use'
      actions:
        - 'sound: BLOCK_CHEST_OPEN-1-0'
      deny:
        - 'sound: ENTITY_ITEM_BREAK-1-0'
        - 'title: `&c&lPermission Required` `&7&lYou need permission &6&ltrmenu.use &7&lto open this menu` 15 20 15'
        - 'return'
  # Close event
  Close:
    - 'sound: BLOCK_CHEST_CLOSE-1-0'

# Icon body of the menu
Icons:
  # Icon Id
  'Close':
    # Icon update frequency
    update: []
    # Icon refresh frequency
    refresh: -1
    # Display part
    display: []
    # Action part
    actions: []

# Timed task
Tasks:
  # Task ID
  tikTok:
    # Task period (in ticks)
    period: 80
    # Task response (reactions)
    task:
      - condition: '$ sender.isOp()'
        actions:
          - 'sound: BLOCK_NOTE_BLOCK_BIT-1-2'

# Built-in custom JavaScript functions
Functions:
  id: 'content'

```

### Structure

* Title
  * Single or multiple titles
  * Title update cycle
* Layout
  * Menu layout
  * Player inventory layout
* Options
  * Default completion arguments
  * Default layout page number
  * Whether to hide player inventory items
  * Free slot
  * Anti-frequent click interval
  * Depend PlaceholderAPI extensions
* Binding
  * Binding regular commands
  * Bound items
* Event
  * Open the menu to perform actions
  * Close the menu to perform an action
* Icon
* Built-in script
* Periodic task

