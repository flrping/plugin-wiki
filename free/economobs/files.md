---
description: Default files for Economobs.
---

# Files

## Configuration

{% tabs %}
{% tab title="2.0.0" %}
```yaml
# Configuration of Economobs. For help, visit https://wiki.flrp.dev
config-version: 6

# Allow the plugin to check for updates?
check-for-updates: true

# Allow players to be killed for money?
# This system currently doesn't contain any countermeasures for repeat kills.
reward-pvp: false

# What stacker should the plugin look for?
# Current list: NONE (Default), WILD_STACKER, STACK_MOB, ULTIMATE_STACKER, ROSE_STACKER
stacker: NONE

# Reward handling.
rewards:
  limit:
    # Should rewards be limited? This is to aid with stackers.
    enabled: true
    # The max amount of rewards that are rolled.
    amount: 10

# Message handling.
message:
  # Should the plugin send messages about money gained?
  enabled: true

  # How should the plugin display messages when a player is given money?
  # NOTE: Some options will only work with select versions. You can see which below.
  # OPTIONS: CHAT, ACTION_BAR (1.12+), HOLOGRAM (1.12+), TITLE (1.12+)
  message-type: CHAT

  # HOLOGRAMS
  # This will only work if you have holograms set as your type.
  holograms:
    # This option will affect animations.
    # How long should the hologram stay? This is in seconds.
    duration: 1

  # This will only work if you have title set as your type.
  title:
    # How long should the title stay? This is in seconds.
    stay: 3
    # How long should the title fade in? This is in seconds.
    fade-in: 1
    # How long should the title fade out? This is in seconds.
    fade-out: 1
    # Naturally, the money message will be displayed in the subtitle.
    # You can change the title to whatever you want here. Placeholders are supported.
    title: "&a&lREWARD"

# Hook management.
hooks:
  entity:
    # Enable MythicMobs support? Adds the ability to earn rewards from custom mobs, and enables multipliers for custom entities.
    MythicMobs: true
    # Enable LevelledMobs support? Adds the ability to add money per level to the base amount (before applying multipliers).
    LevelledMobs: true
    # Enable InfernalMobs support? Adds the ability to add money per modifier to the base amount (before applying multipliers).
    InfernalMobs: true
    # Enable ItemsAdder support? Allows players to earn rewards from custom mobs, and enables multipliers for custom entities.
    ItemsAdder: true
    # Enable Sentinels support? Adds the ability for Sentinels to reward their owners.
    Sentinel: true
  item:
    # Enable Oraxen support? Adds the ability to have multipliers for custom items.
    Oraxen: true
    # Enable ItemsAdder support? Adds the ability to have multipliers for custom items.
    ItemsAdder: true
    # Enable MMOItems support? Adds the ability to have multipliers for custom items.
    MMOItems: true

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
{% endtab %}

{% tab title="1.0.0+ (Older)" %}
```yaml
# Configuration of Economobs. For help, visit https://wiki.flrp.dev
config-version: 5

# Allow the plugin to check for updates?
check-for-updates: true

# Allow players to be killed for money?
# This system currently doesn't contain any countermeasures for repeat kills.
reward-pvp: false

# What currency should the plugin use?
# Current list: VAULT (Default), PLAYER_POINTS, TOKEN_MANAGER
economy: VAULT

# What stacker should the plugin look for?
# Current list: NONE (Default), WILDSTACKER, STACKMOB, ULTIMATESTACKER, ROSESTACKER
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

# Hook management.
hooks:
  # Enable MythicMobs support? Adds the ability to earn money from custom mobs.
  MythicMobs: true
  # Enable LevelledMobs support? Adds the ability to add money per level to the base amount (before applying multipliers).
  LevelledMobs: true
  # Enable InfernalMobs support? Adds the ability to add money per modifier to the base amount (before applying multipliers).
  InfernalMobs: true
  #Enable ItemsAdder support? Allows players to earn money from custom entities, and enabled multipliers for custom items and entities.
  ItemsAdder: true

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
{% endtab %}
{% endtabs %}

## Language

{% tabs %}
{% tab title="2.0.0" %}
<pre class="language-yaml"><code class="lang-yaml"><strong># New placeholders from v2 - OLD PLACEHOLDERS ARE NOT SUPPORTED ANYMORE.
</strong># {base} prints out base amount.
# {multiplier} prints out multiplier.
# {mob} prints out mob name.
# {amount} prints out amount.
# {item} prints out item name.
# {effect} prints out potion effect given.
# {amplifier} prints out potion amplifier.
# {duration} prints out potion duration.
# {command} prints out command used.
# {weight} prints out weight.

# {loot} prints out the loot identifier.
# {loot_table} prints out the loot table identifier.
# {loot_prefix} prints out the loot prefix.

prefix: "&#x26;8[&#x26;aEconomobs&#x26;8] "
command-denied: "&#x26;cYou do not have permission to run this command"

economy-given: "&#x26;7You've earned &#x26;f${amount} &#x26;7by killing a {mob}. &#x26;7&#x26;o({base} x {multiplier})"
economy-max: "&#x26;cYou can't earn more money due to a maximum balance."
item-given: "&#x26;7You have found &#x26;fx{amount} {item} &#x26;7by killing a {mob}."
custom-item-given: "&#x26;7You have found &#x26;fx{amount} {item} &#x26;7by killing a {mob}."
potion-given: "&#x26;7You have been enchanted with {effect} {amplifier} for {duration} seconds &#x26;7by killing a {mob}."
command-given: "&#x26;7Killing a {mob} caused &#x26;f{command} &#x26;7to be ran {amount} times."

reward-toggle: "&#x26;7Toggled messages."
</code></pre>
{% endtab %}

{% tab title="1.0.0+ (Older)" %}
```yaml
prefix: "&8[&aEconomobs&8] "
command-denied: "&cYou do not have permission to run this command"
# {0} prints out the money made.
# {1} prints out the base value.
# {2} prints out the multiplier.
economy-given: "&7You've earned &f${0} &7by killing this mob. &7&o({1} x {2})"
economy-max: "&cYou can't earn more money due to a maximum balance."
economy-toggle: "&7Toggled income messages."
```
{% endtab %}
{% endtabs %}

## Loot

```yaml
tables:
  money_table:
    weight: 100
    drops:
      1:
        weight: 60
        type: ECONOMY
        from: VAULT
        min: 10
        max: 20
      2:
        weight: 30
        type: ECONOMY
        from: VAULT
        min: 20
        max: 30
      3:
        weight: 10
        type: ECONOMY
        from: VAULT
        min: 50
        max: 80
  item_table:
    weight: 100
    drops:
      1:
        weight: 500
        type: ITEM
        min: 1
        max: 1
        material: DIAMOND
      2:
        weight: 50
        type: ITEM
        material: DIAMOND_PICKAXE
        min: 1
        max: 1
        name: '&aDiamond Pickaxe'
        lore:
          - '&7This is a diamond pickaxe'
          - '&7that you got from killing a mob.'
      3:
        weight: 10
        type: ITEM
        material: DIAMOND_PICKAXE
        name: '&aEnchanted Diamond Pickaxe'
        min: 1
        max: 1
        enchantments:
          - unbreaking:3
          - efficiency:3
          - fortune:3
        lore:
          - '&7This is an enchanted diamond pickaxe'
          - '&7that you got from killing a mob.'
  full_table:
    weight: 100
    drops:
      '1':
        weight: 100
        type: ECONOMY
        from: VAULT
        min: 10
        max: 30
      '2':
        weight: 10
        type: ITEM
        min: 1
        max: 1
        material: DIAMOND
      '3':
        weight: 1
        type: ITEM
        material: DIAMOND_PICKAXE
        min: 1
        max: 1
        name: '&aDiamond Pickaxe'
        lore:
          - '&7This is a diamond pickaxe'
          - '&7that you got from killing a mob.'
      '4':
        weight: 1
        type: CUSTOM_ITEM
        from: ITEMS_ADDER
        item: 'GOLD_FRAGMENT'
        min: 3
        max: 5
      '5':
        weight: 5
        type: POTION
        effect: SPEED
        amplifier: 1
        min: 80
        max: 120
      '6':
        weight: 10
        type: COMMAND
        min: 1
        max: 1
        command: 'give {player} diamond 1'
        message: '&7You have been given a diamond.'
```
