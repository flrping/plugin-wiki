# Managing Multiplier Groups

## Understanding the Format

To start off, here's the format for group multipliers.

```yaml
multipliers:
  GROUP_NAME:
    weight: NUMBER
    mobs:
      - ENTITY NUMBER # Decimals are supported.
    weapons:
      - MATERIAL NUMBER
    worlds:
      - WORLD_NAME NUMBER
```

When you fill this out, it should look something like this:

```yaml
 multipliers:
   legendary:
    weight: 5
    mobs:
      - PIG 1.1
    weapons:
      - DIAMOND_SWORD 1.2
    worlds:
      - real_world 1.2
```

Not all tags are required, you may remove any section if you don't wish to use it. For example, you can remove the "worlds" section from the group if you have no world-based multipliers.

```yaml
 multipliers:
   weight: 5
   legendary:
    mobs:
      - PIG 1.1
    weapons:
      - DIAMOND_SWORD 1.2
```

## Dealing With Multiple Groups

When you assign multiple ranks to a user, the plugin depends on the weights you have set to your groups. The higher the number the higher priority for the group over others.

By determining weight, such as the **default being 0**, and for example - **legendary being 5**; legendary has **higher priority** than default.

