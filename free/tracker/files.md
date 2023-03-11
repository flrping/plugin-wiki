---
description: The default files by Tracker.
---

# Files

```yaml
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
```

```yaml
# Head over to https://docs.axelli.net/ and see what the values print.
prefix: "&8[&cTracker&8] "
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



