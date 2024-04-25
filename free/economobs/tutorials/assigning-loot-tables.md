---
description: How to assign loot tables to entities
---

# Assigning Loot Tables

## Introduction

With 2.0.0, the mobs.yml has completely changed and expanded. You now have to assign each mob a loot table (or use the wildcard).

## Assignment

In mobs.yml, you can assign mobs multiple loot tables. Each bundle of Loot Tables makes a Loot Container, which you may see logged on startup.\
\
This is the format to assign loot tables to mobs.&#x20;

```yaml
mobs:  
  PIG:
    tables:
      '1':
        table: money_table
```

Every loot table that you define in this file should be an existing loot table in loot.yml. The plugin creates the loot tables, then assigns each loot table to their respective loot containers.

To list multiple tables, you can do something as simple as this.

```yaml
mobs:  
  PIG:
    tables:
      '1':
        table: money_table
      '2':
        table: item_table
      '3':
        table: full_table
```

## Wildcard Table (Default Loot Table)

This table is not enabled by default, and it is something you have to add in to enable. This option allows you to easily assign a set of tables for mobs that share the same loot tables to avoid redundancy.\
\
Here is how it should be structured:

```yaml
default:
  tables:
    '1':
      table: money_table
```

In mobs.yml (or any hook file that supports table assigning) you should make a new section that starts with default. **This does not go in the list of mobs; this is its own section.**

You can add exclusions to the list as well, if you do not want a mob to have any drops at all.&#x20;

```yaml
default:
  tables:
    '1':
      table: money_table
  excludes:
    - 'PIG'  
```

## Example File

```yaml
default:
  tables:
    '1':
      table: money_table
  excludes:
    - 'PIG'  
mobs:  
  COW:
    tables:
      '1':
        table: money_table_2
  SHEEP:
    tables:
      '1':
        table: money_table_2
```
