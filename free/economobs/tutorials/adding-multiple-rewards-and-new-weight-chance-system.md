# Adding Multiple Rewards & New Weight (Chance) System

Economobs Update 1.5.0 allows users to now set multiple rewards for a single mob. Lets first look at how it's setup by default.

```yaml
mobs:
  PIG:
   - '10' 
# $10 with a weight of 100
```

Now to add another reward, you simply do this:

```yaml
mobs:
  PIG:
   - '10' # $10 with a weight of 100
   - '20' # $20 with a weight of 100 
   
# 200 total weight | each value is 50% chance
```

With the weight & reward system in place, now a PIG has an **EQUAL** chance to drop $10 and $20. Keep note that the plugin will set a values weight to 100 if nothing is defined.\
\
To get rid of this, just set weights behind the value.

```yaml
mobs:
  PIG:
   - '10 80' # $10 with a weight of 80
   - '20 20' # $20 with a weight of 20 

# 100 total weight | $10 80% chance | $20 20% chance
```

Also note, total weights that don't add up to 100 are automatically set to 100. This allows nothing to be dropped.

```yaml
mobs:
  PIG:
   - '10 10' # $10 with a weight of 10
   - '20 10' # $20 with a weight of 5 
   
# 15 total weight BUT set to 100 | $10 10% chance | $20 5% chance
```



