# Managing Multiplier Groups

## Understanding the Format

To start off, here's the format for group multipliers.

```yaml
multipliers:
  GROUP_NAME:
    weight: NUMBER
    blocks:
      - MATERIAL MULTIPLIER # Decimals are supported.
    tools:
      - MATERIAL MULTIPLIER
    worlds:
      - WORLD_NAME MULTIPLIER
```

{% hint style="warning" %}
Don't be confused by double materials. A material can pretty much be anything that's not an entity. Diamonds are materials. Tools are materials. Blocks (types) are materials. Pretty much anything that can be in your hot bar is a material/has a material name.
{% endhint %}

When you fill this out, it should look something like this:

```yaml
multipliers:
  coal:
    weight: 1
    blocks:
      - COAL_ORE 1.2 # Decimals are supported.
    tools:
      - STONE_PICKAXE 1.2
    worlds:
      - real_world 1.5
```

Not all tags are required, you may remove any section if you don't wish to use it. For example, you can remove the "worlds" section from the group if you have no world-based multipliers.

```yaml
multipliers:
  coal:
    weight: 1
    blocks:
      - COAL_ORE 1.2 # Decimals are supported.
    tools:
      - STONE_PICKAXE 1.2
```

## Dealing with Multiple Groups

When you assign multiple ranks to a user, the plugin depends on the weights you have set to your groups. The higher the number the higher priority for the group over others.

By determining weight, such as the **default being 0**, and for example - **coal being 1**; coal has **higher priority** than default.
