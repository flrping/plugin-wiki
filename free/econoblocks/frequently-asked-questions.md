# Frequently Asked Questions

## Group multipliers aren't recognized in ItemsAdder.yml

This is an issue from a generation issue from version 1.4.1 (Fixed in 1.4.2 - files generate correctly). To fix this issue, adjust your values as so:\
\
**INCORRECT**\


```yaml
multipliers:
  example:
    blocks:
      carved_wood_block: '1.2'
```

**CORRECT**

```yaml
multipliers:
  example:
    blocks:
    - carved_wood_block 1.2
```

For the plugin to be able to read the multipliers there should be no colons ( : ) or apostrophe ( ' )\
This rule applies for every other multiplier in the plugin.
