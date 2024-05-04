---
description: Default files for Econoblocks.
---

# Files

## Config

{% tabs %}
{% tab title="2.0.0" %}
```yaml
# Configuration of Econoblocks. For help, visit https://wiki.flrp.dev/
config-version: 6

# Allow the plugin to check for updates?
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
  # OPTIONS: CHAT, ACTION_BAR (1.12+), HOLOGRAM (1.12+), TITLE (1.12+)
  message-type: CHAT

  # HOLOGRAMS
  # This will only work if you have holograms set as your type.
  holograms:
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
  block:
    # Enable ItemsAdder support? This adds the ability to earn money from custom blocks.
    ItemsAdder: true
    # Enable Oraxen support? This adds the ability to earn money from custom blocks.
    Oraxen: true
  item:
    # Enable ItemsAdder support? This adds the ability to have multipliers for custom items.
    ItemsAdder: true
    # Enable Oraxen support? This adds the ability to have multipliers for custom items.
    Oraxen: true
    # Enable MMOItems support? This adds the ability to have multipliers for custom items.
    MMOItems: true

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
{% endtab %}

{% tab title="1.0.0" %}
```yaml
# Configuration of Econoblocks. For help, visit https://wiki.flrp.dev/
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
  - world
```
{% endtab %}
{% endtabs %}

## Blocks

{% tabs %}
{% tab title="2.0.0" %}
```yaml
blocks:
  COAL_ORE:
    tables:
      '1':
        table: money_table
  DEEPSLATE_COAL_ORE:
    tables:
      '1':
        table: money_table
  COPPER_ORE:
    tables:
      '1':
        table: money_table
  DEEPSLATE_COPPER_ORE:
    tables:
      '1':
        table: money_table
  IRON_ORE:
    tables:
      '1':
        table: money_table
  DEEPSLATE_IRON_ORE:
    tables:
      '1':
        table: money_table
  GOLD_ORE:
    tables:
      '1':
        table: money_table
  DEEPSLATE_GOLD_ORE:
    tables:
      '1':
        table: money_table
  REDSTONE_ORE:
    tables:
      '1':
        table: money_table
  DEEPSLATE_REDSTONE_ORE:
    tables:
      '1':
        table: money_table
  LAPIS_ORE:
    tables:
      '1':
        table: money_table
  DEEPSLATE_LAPIS_ORE:
    tables:
      '1':
        table: money_table
  DIAMOND_ORE:
    tables:
      '1':
        table: money_table
  DEEPSLATE_DIAMOND_ORE:
    tables:
      '1':
        table: money_table
  EMERALD_ORE:
    tables:
      '1':
        table: money_table
  DEEPSLATE_EMERALD_ORE:
    tables:
      '1':
        table: money_table
  NETHER_QUARTZ_ORE:
    tables:
      '1':
        table: money_table
  NETHER_GOLD_ORE:
    tables:
      '1':
        table: money_table
  ANCIENT_DEBRIS:
    tables:
      '1':
        table: money_table
```
{% endtab %}

{% tab title="1.0.0" %}
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
{% endtab %}
{% endtabs %}

## Language

{% tabs %}
{% tab title="2.0.0" %}
```yaml
# New placeholders from v2 - OLD PLACEHOLDERS ARE NOT SUPPORTED ANYMORE.
# {base} prints out base amount.
# {multiplier} prints out multiplier.
# {block} prints out block name.
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

prefix: "&8[&6Econoblocks&8] "
command-denied: "&cYou do not have permission to run this command"

economy-given: "&7You've earned &f${amount} &7by mining {block}. &7&o({base} x {multiplier})"
economy-max: "&cYou can't earn more money due to a maximum balance."
item-given: "&7You have found &fx{amount} {item} &7by mining {block}."
custom-item-given: "&7You have found &fx{amount} {item} &7by mining {block}."
potion-given: "&7You have been enchanted with {effect} {amplifier} for {duration} seconds &7by mining {block}."
command-given: "&7Mining {block} caused &f{command} &7to be ran {amount} times."

reward-toggle: "&7Toggled messages."
```
{% endtab %}

{% tab title="1.0.0" %}
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
          - '&7that you got from mining a block.'
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
          - '&7that you got from mining a block.'
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
          - '&7that you got from mining a block.'
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
