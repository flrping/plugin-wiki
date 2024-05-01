---
description: Lists of commands and permissions can be found here.
---

# Permissions, Commands, & Placeholders

| Command                                                                                                     | Permission           | Description                              |
| ----------------------------------------------------------------------------------------------------------- | -------------------- | ---------------------------------------- |
| /economobs                                                                                                  | default              | Brings up an in-game help guide.         |
| /economobs toggle                                                                                           | default              | Toggles messaging features.              |
| /economobs profile \<player>                                                                                | economobs.profile    | Checks the multiplier profile of a user. |
| /economobs check \<mob/custom> \<entity>                                                                    | economobs.check      | Checks the loot tables of an entity.     |
| /economobs multiplier add \<user> \<entity/tool/world/custom\_entity/custom\_tool> \<context> \<multiplier> | economobs.multiplier | Adds a multiplier to a user.             |
| /economobs multiplier remove \<user> \<entity/tool/world/custom\_entity/custom\_tool> \<context>            | economobs.multiplier | Removes a multiplier from a user.        |
| /economobs reload                                                                                           | economobs.reload     | Reloads the plugin.                      |
| All                                                                                                         | economobs.admin      | Gives access to all commands.            |

| Permission               | Description                              |
| ------------------------ | ---------------------------------------- |
| economobs.group.\<group> | Adds a multiplier group to a user/group. |



<table><thead><tr><th width="358">Placeholder</th><th width="255">Description</th><th>Default Value</th></tr></thead><tbody><tr><td>%economobs_multiplier_entity_&#x3C;entity>%</td><td>Prints the players multiplier of an entity.</td><td>1.0</td></tr><tr><td>%economobs_multiplier_tool_&#x3C;tool>%</td><td>Prints the players multiplier of a tool.</td><td>1.0</td></tr><tr><td>%economobs_multiplier_world_&#x3C;world>%</td><td>Prints the players multiplier of a world.</td><td>1.0</td></tr></tbody></table>
