# Creating a Reward

## Understanding the Format

This is a general explanation of what each section means and does.

```yaml
# MATERIAL - You know, something like DIAMOND_SWORD.
# MILESTONE_TYPE - This can either be once or interval. 
#     Once are ONE TIME rewards, interval happens every x blocks.
# AMOUNT - the amount of blocks or kills needed for this reward.
# REWARD_TYPE - This can either be commands: or enchants:
#
# for example:
# enchants:
#    - sharpness:1

milestones:
    <MATERIAL>:
        <MILESTONE_TYPE>:
            <AMOUNT>:
                <REWARD_TYPE>:
                    - "context"
```

{% hint style="info" %}
These values are for 1.13+. Please use the correct values for anything below.
{% endhint %}

## Diamond Pickaxe Example Reward

Lets make a reward for a diamond pickaxe, that gives a player 100 bucks and efficiency on their pickaxe when they reach 100 blocks.

```yaml
milestones:
    DIAMOND_PICKAXE: # <- Material
        once: # <- Since we want to give the player rewards when they hti 100 blocks,
              # we will use once since it's a one time thing.
            100: # <- the 100 blocks we want the player to reach.
                commands: # <- The commands that will run
                    - "eco give %player% 100" # <- give the player 100 bucks.
                enchants: # <- the enchantments that will apply to the item
                    - "eco give %player% 100" # <- give the tool efficiency.
```

## Reward That Applies to Every Sword

This time, lets make a reward that applies to every sword available. The reward will give the player $100 for every 50 mobs they kill.

```yaml
milestones:
    EVERY_SWORD: # <- EVERY_ keyword.
        interval: # <- Since we want to give the player rewards each time they kill 
              # 50 mobs, we will use interval since it's repeating.
            50: # <- the 50 kills we want the player to reach.
                commands: # <- The commands that will run
                    - "eco give %player% 100" # <- give the player 100 bucks.
```

_****_

{% hint style="info" %}
The EVERY\_ keyword will work with most tool types.
{% endhint %}
