# Adding Chances

## Basic Usage

To add a chance to a mob, simply just add the percentage after your value. Let's add a 50% chance for $10 for every time a pig is killed.

Simply add a 50 after the amount.

From this:

```yaml
mobs:
    PIG: '10'
```

To this:

```yaml
mobs:
    PIG: '10 50'
```

## More Rare Chances

You are allowed to set way rarer chances than 1%. For example, down below there's a 5 in 1000 chance (or 1 in 200) for a pig to give you $1000. &#x20;

```yaml
mobs:
    PIG: '1000 0.5'
```

This example shows a 1 in 1,000,000 chance for a pig to give you $100,000.

```yaml
mobs:
    PIG: '100000 0.0001'
```
