---
description: The default files by Tracker.
---

# Files

```yaml
# config.yml

# What stacker should the plugin look for?
# Current list: NONE, WILDSTACKER, STACKMOB
stacker: NONE

# Everything dealing with the counter process.
counter:
  # The tag that will appear on the items display.
  tag: "&8[&7%stats%&8]"

  # Sounds that will play on mine or kill.
  sounds:
    enabled: true
    sound: BLOCK_NOTE_BLOCK_BELL

  # Are milestones enabled?
  milestones:
    enabled: true

# List of tools that will be applied to either block breaking or killing an entity.
# Adding an item in both lists will share the counter tag.
stats:
  # Is block tracking enabled?
  blocks:
    enabled: true
    list:
      - WOODEN_PICKAXE
      - WOODEN_AXE
      - WOODEN_SHOVEL
      - STONE_PICKAXE
      - STONE_AXE
      - STONE_SHOVEL
      - IRON_PICKAXE
      - IRON_AXE
      - IRON_SHOVEL
      - GOLDEN_PICKAXE
      - GOLDEN_AXE
      - GOLDEN_SHOVEL
      - DIAMOND_PICKAXE
      - DIAMOND_AXE
      - DIAMOND_SHOVEL
      - NETHERITE_PICKAXE
      - NETHERITE_AXE
      - NETHERITE_SHOVEL

  kills:
    # Is kill tracking enabled?
    enabled: true
    list:
      - WOODEN_SWORD
      - STONE_SWORD
      - IRON_SWORD
      - GOLDEN_SWORD
      - DIAMOND_SWORD
      - NETHERITE_SWORD

# This module allows your players to get a tracker enchantment book; which
# can be applied to allow tracking on the item.
# NOTE: Enabling this module will only track tools that have the module.
module:
  # Is this module enabled?
  enabled: false

  # Sounds related to module events.
  sounds:
    enabled: true
    receive: BLOCK_NOTE_BLOCK_BELL
    fail: BLOCK_ANVIL_LAND
    success: BLOCK_NOTE_BLOCK_BELL

  # This section represents the enchantment item.
  item:
    material: NETHER_STAR
    title: "&a&lTracker Module"
    lore:
      - "&7Add an objective tracker on your tool."
```

```yaml
# milestones.yml (previously goals.yml)

# Tool type examples: ALL (For all tools), EVERY_PICKAXE (Only Pickaxes), DIAMOND_PICKAXE (Only this tool)
# Specifying a type other than ALL will bypass it.
# Priorities Example (Highest to Lowest) : DIAMOND_PICKAXE -> EVERY_PICKAXE -> ALL
# Head over to https://docs.axelli.net/ to see more info.
milestones:
  DIAMOND_PICKAXE:
    # Happens only when x amount of blocks is reached.
    once:
      # The amount of blocks
      1000:
        # Console Commands that will run.
        commands:
          - "eco give %player% 1000"
        # The enchants that will be added or buffed.
        enchants:
          - efficiency:1
      10000:
        # You can leave options out if you want.
        enchants:
          - efficiency:2
    # Happens every x amount of blocks.
    interval:
      5000:
        commands:
          - "eco give %player% 1000"
        enchants:
          - efficiency:1
  EVERY_SWORD:
    once:
      1000:
        commands:
          - "eco give %player% 1000"
        enchants:
          - sharpness:1
          - unbreaking:1
  EVERY_AXE:
    interval:
      1000:
        commands:
          - "eco give %player% 1000"
  ALL:
    interval:
      1000:
        enchants:
          - unbreaking:1
```

```yaml
# language.yml

# Head over to https://docs.axelli.net/ and see what the values print.
prefix: "&8[&cTrackerPlus&8] "
tool_not_supported: "&cThis item can't be used for tracking."
# Boolean values if reached or not.
milestone-not-reached: "&c&lNOT REACHED"
milestone-reached: "&a&lREACHED"
# 0 - Prints amount needed
# 1 - Type of unit (kills or blocks)
current-milestone: "&7The current milestone for this tool is &f{0} &7{1}."
no-milestones-left: "&7This tool has reached all it's milestones."
no-milestones-exist-total: "&cThis tool doesn't have any milestones it can achieve for it's total amount."
no-milestones-exist: "&cThis tool doesn't have any milestones it can achieve."
# 0 - Prints amount needed
# 1 - Type of unit (kills or blocks)
# 2 - REACHED or NOT REACHED
milestone-once-header: "&cOnce"
milestone-once-entry: "&8- &7Reach a total of &f{0} &7{1} &8|&r {2}"
milestone-interval-header: "&cRepeating"
milestone-interval-entry: "&8- &7Every &f{0} &7{1}"
# 0 - prints entry
milestone-list:
  - "&c&lMILESTONES"
  - "&7The current milestones for this tool are:"
  - "&7"
  - "{0}"
# 0 - prints the milestone amount
# 1 - Type of unit (kills or blocks)
milestone-achieved-once: "&7You reached &f{0} &7{1}! Here are some rewards for reaching this milestone."
milestone-achieved-interval: "&7You hit another &f{0} &7{1}! Here are some rewards for reaching this milestone."
# 0 - prints level
# 1 - prints enchant
milestone-reward-entry: " &c+{0} &l{1}"
# 0 - prints the list of enchants applied
milestone-reward-list:
  - "&7Your tool has received the following:"
  - "{0}"
  - "&7"
module-give-player: "&7You successfully gave &f{0} &7a Tracker Module."
module-received: "&7You received a &fTracker Module&7."
module-applied: "&aYou successfully applied a Tracker Module to this tool."
module-exists: "&7A Tracker Module already exists on this item."
```

```yaml
# whitelist.yml

# Use a valid name according to your server version.
# To disable whitelisting, just use [].
blocks:
  - "STONE"
  - "COBBLESTONE"
  - "DEEPSLATE"
  - "COPPER_ORE"
  - "DEEPSLATE_COPPER_ORE"
  - "COAL_ORE"
  - "DEEPSLATE_COAL_ORE"
  - "IRON_ORE"
  - "DEEPSLATE_IRON_ORE"
  - "REDSTONE_ORE"
  - "DEEPSLATE_REDSTONE_ORE"
  - "LAPIS_ORE"
  - "DEEPSLATE_LAPIS_ORE"
  - "GOLD_ORE"
  - "DEEPSLATE_GOLD_ORE"
  - "DIAMOND_ORE"
  - "DEEPSLATE_DIAMOND_ORE"
  - "EMERALD_ORE"
  - "DEEPSLATE_EMERALD_ORE"
  - "NETHER_QUARTZ_ORE"
  - "NETHER_GOLD_ORE"
  - "ANCIENT_DEBRIS"
mobs: []
```



