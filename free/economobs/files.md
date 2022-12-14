---
description: Default files for Economobs.
---

# Files

### Config

```yaml
# Configuration of Economobs. For help, visit https://docs.axelli.net/

# What stacker should the plugin look for?
# Current list: NONE, WILDSTACKER, STACKMOB
stacker: NONE

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

# Multiplier handling.
# Down below are configurable multiplier groups.
# If any conditions are true, they will be considered towards the output amount.
# Make sure to balance this properly if you use multipliers. You can leave any category empty with [] if you wish not to use it.
multipliers:
  example:
    # Higher the number, heavier the group, higher priority.
    weight: 1
    # Specific mob multipliers.
    mobs:
      - CHICKEN 1.1
      - PIG 1.1
      - COW 1.1
    # The tool used to kill the mob.
    weapons:
      - DIAMOND_SWORD 1.2
    # The world the mob died in.
    worlds:
      - real_world 1.1
  # More examples...
  coal:
    weight: 2
    mobs:
      - COW 1.5
    weapons:
      - DIAMOND_SWORD 1.5
  diamond:
    weight: 3
    mobs:
      - COW 2
    weapons:
      - DIAMOND_SWORD 2.5

# A list of worlds where money won't be given.
world-blacklist:
  - world2
```

### Language

```yaml
# Language.yml

prefix: "&8[&aEconomobs&8] "
command-denied: "&cYou do not have permission to run this command"
# {0} prints out the money made.
economy-given: "&7You've earned &f${0} &7by killing this mob."
economy-max: "&cYou can't earn more money due to a maximum balance."
economy-failed: "&cUnable to add money to your balance."
economy-toggle: "&7Toggled income messages."
```
