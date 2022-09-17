# Adding Chances

## Basic Usage

To add a chance to a block, simply just add the percentage after your value. Let's add a 50% chance for $10 for every time coal is mined.

Simply add a 50 after the amount.

From this:

```yaml
blocks:
  COAL_ORE: 10
```

To this:

```yaml
blocks:
  COAL_ORE: 10 50
```

## More Rare Chances

You are allowed to set way rarer chances than 1%. For example, down below there's a 5 in 1000 chance (or 1 in 200) for coal to give you $1000. &#x20;

```yaml
blocks:
  COAL_ORE: 1000 0.5
```

This example shows a 1 in 1,000,000 chance for coal to give you $100,000.

```yaml
blocks:
  COAL_ORE: 100000 0.0001
```
