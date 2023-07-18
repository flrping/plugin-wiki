---
description: Default files for Econoblocks.
---

# Files

```yaml
# Configuration of Econoblocks. For help, visit https://docs.axelli.net/
check-for-updates: true

# Gamemode settings.
gamemode:
  # Should people in creative mode get rewards?
  creative-rewards: false

# Message handling.
message:
  # Should the plugin send messages about money gained?
  enabled: true

  # How should the plugin display messages when a player is given money?
  # NOTE: Some options will only work with select versions. You can see which below.
  # OPTIONS: CHAT, ACTION_BAR (1.12+), HOLOGRAM (1.12+)
  message-type: CHAT

  # HOLOGRAMS
  # This will only work if you have holograms set as your type.
  holograms:
    # OPTIONS: STAY, FLOAT, BOUNCE
    animation: STAY
    # This option will affect animations.
    # How long should the hologram stay? This is in seconds.
    duration: 1

# The check system provides methods to help make sure players can't duplicate rewards.
checks:
  # This option uses SQLite. SQL support will come later.
  storage:
    # Should blocks be stored in a database? This will keep all block data across restarts. Setting this option to false will still keep track of blocks,
    # but they will NOT be saved across restarts.
    enabled: true
    # How long will blocks be stored for until they expire? This will help clear up space in the database.
    # To disable this, just set it to 0. This is in days.
    expiry: 3
    
# Hook management.
hooks:
  # Enable ItemsAdder support? This adds the ability to earn money from custom blocks.
  ItemsAdder: true
  
# Multiplier handling.
# Down below are configurable multiplier groups.
# When given permission, a user will gain specific multipliers.
# If any conditions are true, they will be considered towards the output amount.
# Make sure to balance this properly if you use multipliers. You can leave any category empty with [] if you wish not to use it.
multipliers:
  # econoblocks.group.example
  example:
    # Higher the number, heavier the group, higher priority.
    weight: 1
    # Specific block multipliers.
    blocks:
      - COAL_ORE 1.5
      - IRON_ORE 1.5
    # Specific tool multipliers.
    tools:
      - IRON_PICKAXE 1.05
      - GOLDEN_PICKAXE 1.1
      - DIAMOND_PICKAXE 1.2
    # The world the block was mined in.
    worlds:
      - real_world 1.1
  # More examples...
  coal:
    weight: 2
    tools:
      - IRON_PICKAXE 1.1
  diamond:
    weight: 3
    blocks:
      - DIAMOND_ORE 1.5
    tools:
      - IRON_PICKAXE 1.15

# A list of worlds where money won't be given.
world-blacklist:
  - world2
```

```yaml
# Blocks.yml

# Format - "<amount> (chance)"
# Setting a chance is completely optional. Leaving it blank will set it to 100%.
blocks:
  COAL_ORE: 10
  IRON_ORE: 10
  GOLD_ORE: 100 30
  REDSTONE_ORE: 50 30
  LAPIS_ORE: 50 30
  DIAMOND_ORE: 100 20
  EMERALD_ORE: 200 10
```

```yaml
# Language.yml

prefix: "&8[&6Econoblocks&8] "
command-denied: "&cYou do not have permission to run this command"
# {0} prints out the money made.
economy-given: "&7You've earned &f${0} &7by mining this block."
economy-max: "&cYou can't earn more money due to a maximum balance."
economy-failed: "&cUnable to add money to your balance."
economy-toggle: "&7Toggled income messages."
```
