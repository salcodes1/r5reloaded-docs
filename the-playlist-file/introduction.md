# playlist文件介绍

## 什么是playlist文件?

playlist文件是位于 `platform` 文件夹中的纯文本文件。它管理以下功能:

* 默认游戏参数 \(例如 `match_ending_enabled`\)
* 游戏模式 \(例如 `custom_tdm`, `survival`\) ，并决定了相关模式的可用地图
* 游戏模式的参数 \(例如在 `custom_tdm` 中的 `default_shield_hp` \)

通过playlist文件，你可以自定义任何已存在的游戏模式，而无需知道如何去实现它们。

## 如何修改playlist文件？

只需使用任何文本/代码编辑器来打开文件。

### 文件结构

In the playlist file, there's the gamemodes, and there's the playlists. Gamemodes are defined in the `Gamemodes` block, while playlists are defined in the `Playlists` block. At the bottom of the file, you will also find `KVFileOverrides`.

{% hint style="warning" %}
Playlists and gamemodes can share the same name \(e.g. `custom_tdm`\)! You can differentiate them by looking in which block they're defined.
{% endhint %}

#### 游戏模式部分

Gamemodes are **bases** which the playlists **build upon**. You do not typically need to modify anything in this block. Currently, we have as base gamemodes:

* `survival`: standard Apex Battle Royale experience
* `custom_tdm`:despite its name, it's a variable-team deathmatch experience with respawns

#### Playlists部分

在这里，您可以定义playlist来修改游戏模式的行为。稍后我们将进一步讨论这一部分。.

{% hint style="info" %}
多个playlists可以拥有相同的基础游戏模式。
{% endhint %}

#### KVFileOverrides（关键数据覆盖）部分

This is where you can modify weapon values, such as damage, ammo count etc. You can read more about how to modify weapon properties in the Weapons section.

{% hint style="danger" %}
We urge you to use this method instead of modifying the files `scripts/weapons/*` , as the changes are broadcasted to every player connected to you, so no weird issues arise using this method. This way, no desync issues/weird bugs will arise.
{% endhint %}

####  Now, let's look at an example:

```yaml
Playlists
{
	custom_tdm
	{
				inherit defaults
				vars
				{
					max_teams                          2
					min_players                        2
					max_players                        64
					
					//TDM Settings
					survival_jumpkit_enabled           1
					survival_wallrun_enabled           1
					survival_infinite_ammo             1
					default_shield_hp                  75
					ground_loot_enable                 0
					lootbin_loot_enable                0
	
					//whitelisted_weapon_0			       "mp_weapon_mastiff"
	
					jump_from_plane_enabled            0
					match_ending_enabled               0
					sur_circle_start_paused            1
	
	
				}
				gamemodes { custom_tdm { maps {
					mp_rr_desertlands_64k_x_64k 1
				} } }
		}
}


```

The above is an excerpt from the `custom_tdm` **playlist** settings. You can find the full version in the file.

First of all, anything preceded by `//` is not read by the game and is named a **comment**. It is there only to help other people understand what you've done, or to neatly organize all the properties you've written. A common practice is to **comment** properties you want to temporarily disable without deleting them, as the game will not read the contents.

```text
max_teams 2
```

In the code above, you see what we'll refer to going forward as a **KV** \(key-value\) or **PlaylistVar**. The **key** is the property name \(`max_teams`\) and the value is, well, the value of said property \(`2`\). The game will read this **KV** and make it so the players only get distributed in 2 teams, which is perfect for a Team Deathmatch! 

KV's support multiple value **types**:

| Type | Explanation | Example |
| :--- | :--- | :--- |
| `int` | Integer | `3`, `-41` |
| `bool` | Must be either `0` or `1`  Typically used for PlaylistVars with ****only 2 possible values, such as`replay_enabled` | `0` |
| `float` | Rational numbers | `3.14` |
| `string` | Plain text  **Must be surrounded by** `"` | `"mp_weapon_mastiff"` |

## 实际样例

Team Deathmatch is nice and all, but, because of the flexibility of the playlist file, we can make it into a Free For All without any code changes, with the following properties changed:

```text
max_teams                          64
max_players                        64
max_team_players                   1
```

Notice that we use a new KV called `max_team_players`. This will make it so the game is forced to leave only 1 player in each team. 

{% hint style="warning" %}
Make sure `max_players` isn't greater than `max_teams` though, because the game will not have enough teams to assign the players to!
{% endhint %}

## 我需要更多相关知识!

继续下一节，在这里您可以了解到所有可以修改的关键数据\(KVs\)。

