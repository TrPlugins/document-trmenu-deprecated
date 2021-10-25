# Quick binding

## Configuration

{% code title="settings.yml" %}
```yaml
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
```
{% endcode %}

## Type

* Switch Off-hand OFFHAND
* Sneak + Switch Off-hand SNEAKING\_OFFHAND
* Right click player RIGHT\_CLICK\_PLAYER
* Sneak + Right click player SNEAKING\_RIGHT\_CLICK\_PLAYER
* \(In survival mode\) Click outside the player’s inventory PLAYER\_INVENTORY\_BORDER\_LEFT/RIGHT/MIDDLE

## Note

* When the execution result of **action group** is true, this event will be canceled \(for example, switch deputy\)
* To prevent interference with the game experience, all shortcut combinations of \[sneak + operation\] need to be completed within **1.5s** before they can be triggered
* The shortcut of the right-click player will pass in the menu argument as the name of the target player by default

