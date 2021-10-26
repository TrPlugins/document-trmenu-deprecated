# Command Register

## Configuration

{% code title="settings.yml" %}
```yaml
RegisterCommands:
  # Main command name
  openMenus:
    # Sub command name
    aliases: [ ]
    # Required permissions, no need permissions set it to null
    permission: null
    # Action
    execute:
      - 'tell: &7Argument `example` Required!'
    # Arguments
    arguments:
      # /openMenu example
      # Action
      example: 'open: example'
```