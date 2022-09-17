# Frequently Asked Questions

## There's a parseDouble() error when loading the plugin.

This issue is from a mistake I made when creating blocks.yml **The default configuration is fixed as of version 1.0.1**. To fix this problem, just remove the **:** from your values

**INCORRECT**

```yaml
blocks:
    COAL_ORE: 10:10
```

**CORRECT**&#x20;

```yaml
blocks:
    COAL_ORE: 10 10
```
