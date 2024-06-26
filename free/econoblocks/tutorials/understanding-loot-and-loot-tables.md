---
description: Explaining loot and loot tables
---

# Understanding Loot and Loot Tables

## Introduction

With 2.0.0 comes a huge expansion on the rewards system. Not only can you give rewards and have multipliers like usual, but you may now have items, commands, potion effects, and even custom items as loot.

Let's take a look at how loot tables are structured and made.

## Loot Table <a href="#loot-table" id="loot-table"></a>

Here's a bit of the default loot table **money\_table** that is generated with a fresh install of the plugin.

```yaml
money_table:
  weight: 100
  drops:
    '1':
      weight: 60
      type: ECONOMY
      from: VAULT
      min: 10
      max: 20
```

If you are experienced with Econoblocks it may seem familiar. Loot now has way more options for you to use and make your servers unique. Here is the breakdown and available options.

```yaml
TABLE_NAME:
  weight: 100
  drops:
    LOOT_ID:
      weight: 60
      type: ECONOMY
      from: VAULT
      min: 10
      max: 20
      message: Set custom message here
```

{% hint style="info" %}
Weight is a piece of distribution.

When the plugin rolls and picks an outcome, it uses "total weight" - adding all the reward weights together.&#x20;

For example: A reward with a weight of 20 in a total weight of 200, means it will have a 10% chance of dropping said reward.&#x20;

These weight values **do not** need to be within a 100 total weight. Use this weight system to your advantage.&#x20;

_When no weight is defined, it will assume 100 weight._ \
_When the total is under 100, this allows rewards to not be given._
{% endhint %}

* TABLE\_NAME - name of the loot table. These must be unique across your tables; you will be using this name to assign your blocks loot tables.
* LOOT\_ID - id of the loot inside the table, these must be unique within the table. TYPE is the type of loot. This can be ECONOMY, ITEM, CUSTOM\_ITEM, POTION, or COMMAND
* FROM **-** where the loot is sourced from. When it comes to economy, this should be an Economy hook. When it comes to custom items, it should be a custom item hook.
* MIN and MAX - the ranges of the amount the loot will distribute.
* MESSAGE **-** sets a custom message for the loot. If not defined, the plugin will use the message in language.yml.

## Examples <a href="#examples" id="examples"></a>

Basic economy reward that will come from your server's main economy.

```yaml
example_table:
  weight: 100
  drops:
    '1':
      weight: 60
      type: ECONOMY
      from: VAULT
      min: 10
      max: 20
```

Item reward that drops an enchanted, named pickaxe.

```yaml
example_table:
  weight: 100
  drops:
    '1':
      weight: 10
      type: ITEM
      material: DIAMOND_PICKAXE
      name: "&aEnchanted Diamond Pickaxe"
      min: 1
      max: 1
      enchantments:
        - unbreaking:3
        - efficiency:3
        - fortune:3
      lore:
        - "&7This is an enchanted diamond pickaxe"
        - "&7that you got from mining a block."
```

Custom item reward that drops ruby shards from the plugin ItemsAdder.

```yaml
example_table:
  weight: 100
  drops:
    '1':
      weight: 10
      type: CUSTOM_ITEM
      from: ITEMS_ADDER
      item: RUBY_SHARD
      min: 3
      max: 5
```

Potion effect reward that gives you Speed 2.

```yaml
example_table:
  weight: 100
  drops:
    '1':
      weight: 5
      type: POTION
      effect: SPEED
      amplifier: 2
      min: 80
      max: 120
```

A reward that runs a command.

```yaml
example_table:
  weight: 100
  drops:
    '1':
      weight: 10
      type: COMMAND
      min: 1
      max: 1
      command: give {player} diamond 1
      message: "&7You have been given a diamond."
```
