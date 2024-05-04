# Managing Rewards & Drop Weight

## Explanation

First, let's understand how the format works.

```yaml
mobs:
  BLOCK: 
   - 'PAY WEIGHT' 
```

**BLOCK** would be something like STONE or COAL\_ORE. You can find a list of valid blocks [here](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html).

**PAY** would be what the player would be paid if the roll lands.&#x20;

**WEIGHT** would be the distribution value (or chance) of that reward.&#x20;

{% hint style="info" %}
To explain weight further, a weight is a piece of distribution.\
\
When the plugin rolls and picks a reward, it uses a "total weight" - adding all the reward weights together.\
\
For example: A reward with a weight of 20 in a total weight of 200, means it will have a 10% chance of dropping said reward.\
\
These weight values **do not** need to be within a 100 total weight. Use this weight system to your advantage.
{% endhint %}

## Examples

```yaml
blocks:
  COAL_ORE:
   - '10' 
# $10 with a weight of 100, will always drop
```

{% hint style="info" %}
Values with no weight defined will assume **Weight = 100**
{% endhint %}

```yaml
blocks:
  COAL_ORE:
   - '10' # $10 with a weight of 100
   - '20' # $20 with a weight of 100 
   
# 200 total weight | each value is 50% chance
```

```yaml
blocks:
  COAL_ORE:
   - '10 80' # $10 with a weight of 80
   - '20 20' # $20 with a weight of 20 

# 100 total weight | $10 80% chance | $20 20% chance
```

```yaml
blocks:
  COAL_ORE:
   - '10 10' # $10 with a weight of 10
   - '20 5' # $20 with a weight of 5 
   
# 15 total weight BUT set to 100 | $10 10% chance | $20 5% chance | $0 85% chance
```

{% hint style="info" %}
Total weight under 100 will assume **Total Weight = 100**\
This allows nothing to be dropped.
{% endhint %}





