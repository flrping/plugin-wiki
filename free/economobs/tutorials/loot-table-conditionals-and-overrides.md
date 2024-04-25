---
description: Advanced loot customization with conditionals and overrides
---

# Loot Table Conditionals and Overrides

## Introduction

You can expand on loot tables with conditionals. These allow you to have certain drops in certain areas, or if an entity was killed with a specific item, and more. Weight overrides allow you to dynamically adjust the drop rate.

## Adding Conditionals

Adding conditionals to a loot table is relatively simple. To assign conditionals, you have to do it when you assign tables to entities. This allows you to flexibly control where conditionals are.  \
\
Below where you define the table for that entry, below you put the conditions section. Then you list all the conditions the table should have. For example:&#x20;

```yaml
mobs:  
  ZOMBIE:
    tables:
      '1':
        table: money_table
        conditions:
          - '[permission] example.permission'
```

To clarify, you simply list what type of condition it is and then the context.&#x20;

```
conditions:
  - "[type] context"
```

The list of supported conditionals is:

* Permission - The player needs a permission.
* World - The player needs to be in a specific world.
* With - The player needs to kill the entity with a certain item.
* Biome - The player needs to be in a specific biome.

{% hint style="info" %}
When using the \[with] conditional, if you decide to use a custom item - be sure to include the hook/plugin where it is from. For example:\
\
An Emerald Sword from ItemsAdder would look like:\
\- "\[with] items\_adder:emerald\_sword"
{% endhint %}

## Example Table with Conditionals

```yaml
mobs:  
  PIG:
    tables:
      '1':
        table: money_table
        conditions:
          - '[permission] example.permission'
          - '[world] world'
          - '[with] DIAMOND_SWORD'
          - '[with] items_adder:emerald_sword'
          - '[biome] PLAINS'
```

***

## Weight Overrides

Along with conditionals, you can define a weight override for the loot table. If you have a collection of tables assigned to an entity, you may want to adjust the weight depending on how difficult it is to kill or its rarity.\
\
Let's say money\_table has a defined weight of 100 in loot.yml and you want to change it to 200 for Pigs.

```yaml
mobs:  
  PIG:
    tables:
      '1':
        table: money_table
        weight: 200
      '2':
        table: item_table
      '3':
        table: full_table
```

Just add a weight section and define it's new weight.
