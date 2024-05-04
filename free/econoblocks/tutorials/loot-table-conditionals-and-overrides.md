---
description: Advanced loot customization with conditionals and overrides
---

# Loot Table Conditionals and Overrides

## Introduction <a href="#introduction" id="introduction"></a>

You can expand on loot tables with conditionals. These allow you to have certain drops in certain areas, or if a block was broken with a specific item, and more. Weight overrides allow you to dynamically adjust the drop rate.

## Adding Conditionals <a href="#adding-conditionals" id="adding-conditionals"></a>

Adding conditionals to a loot table is relatively simple. To assign conditionals, you have to do it when you assign tables to blocks. This allows you to flexibly control where conditionals are. Below where you define the table for that entry, below you put the conditions section. Then you list all the conditions the table should have. For example:

```yaml
blocks:  
  STONE:
    tables:
      '1':
        table: money_table
        conditions:
          - '[permission] example.permission'
```

To clarify, you simply list what type of condition it is and then the context.

```yaml
conditions:
  - "[type] context"
```

The list of supported conditionals is:

* Permission - The player needs a permission.
* World - The player needs to be in a specific world.
* With - The player needs to break a block with a certain item.
* Biome - The player needs to be in a specific biome.

{% hint style="info" %}
When using the \[with] conditional, if you decide to use a custom item - be sure to include the hook/plugin where it is from.&#x20;

For example: An Emerald Pickaxe from ItemsAdder would look like:&#x20;

\- "\[with] items\_adder:emerald\_pickaxe"
{% endhint %}

### Example Table with Conditionals <a href="#example-table-with-conditionals" id="example-table-with-conditionals"></a>

```yaml
blocks:  
  COAL_ORE:
    tables:
      '1':
        table: money_table
        conditions:
          - '[permission] example.permission'
          - '[world] world'
          - '[with] DIAMOND_PICKAXE'
          - '[with] items_adder:emerald_pickaxe'
          - '[biome] PLAINS'
```

***

### Weight Overrides <a href="#weight-overrides" id="weight-overrides"></a>

Along with conditionals, you can define a weight override for the loot table. If you have a collection of tables assigned to a block, you may want to adjust the weight depending on how difficult it is to mine or its rarity. Let's say money\_table has a defined weight of 100 in loot.yml and you want to change it to 200 for Deepslate Diamonds.

Copy

```yaml
blocks:  
  DEEPSLATE_DIAMOND_ORE:
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
