---
description: How to assign loot tables to blocks
---

# Assigning Loot Tables

## Introduction <a href="#introduction" id="introduction"></a>

With 2.0.0, the blocks.yml has completely changed and expanded. You now have to assign each block a loot table (or use the wildcard).

## Assignment <a href="#assignment" id="assignment"></a>

In blocks.yml, you can assign blocks multiple loot tables. Each bundle of Loot Tables makes a Loot Container, which you may see logged on startup. This is the format to assign loot tables to blocks.

This is the format to assign loot tables to blocks.

```yaml
blocks:  
  COAL_ORE:
    tables:
      '1':
        table: money_table
```

Every loot table that you define in this file should be an existing loot table in loot.yml. The plugin creates the loot tables, then assigns each loot table to their respective loot containers.

To list multiple tables, you can do something as simple as this.

```yaml
blocks:  
  COAL_ORE:
    tables:
      '1':
        table: money_table
      '2':
        table: item_table
      '3':
        table: full_table
```

### Wildcard Table (Default Loot Table) <a href="#wildcard-table-default-loot-table" id="wildcard-table-default-loot-table"></a>

This table is not enabled by default, and it is something you have to add in to enable. This option allows you to easily assign a set of tables for blocks that share the same loot tables to avoid redundancy. Here is how it should be structured:

```yaml
default:
  tables:
    '1':
      table: money_table
```

In blocks.yml (or any hook file that supports table assigning) you should make a new section that starts with default. **This does not go in the list of blocks; this is its own section.**

You can add exclusions to the list as well, if you do not want a block to have any drops at all.

```yaml
default:
  tables:
    '1':
      table: money_table
  excludes:
    - 'STONE'  
```

### Example File <a href="#example-file" id="example-file"></a>

```yaml
default:
  tables:
    '1':
      table: money_table
  excludes:
    - 'STONE'  
blocks:  
  COAL_ORE:
    tables:
      '1':
        table: money_table_2
  OAK_LOG:
    tables:
      '1':
        table: money_table_2
```
