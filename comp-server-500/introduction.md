# Introduction

## What is the playlist file?

The playlist file is a plain text file located in your game directory's `platform` folder. It manages:

* Default game parameters \(e.g. `match_ending_enabled`\)
* Gamemodes \(e.g. `custom_tdm`, `survival`\) and what maps these gamemodes can be played on
* Gamemode parameters \(e.g. `default_shield_hp` for `custom_tdm`\)

Through the playlist file, you can customize any gamemode without needing to know how to code.

## How do I modify the playlist file?

Simply open the file with any text/code editor.

### Structure

In the playlist file, there's the gamemodes, and there's the playlists. Gamemodes are defined in the `Gamemodes` block, while playlists are defined in the `Playlists` block. At the bottom of the file, you will also find `KVFileOverrides`.

{% hint style="warning" %}
Playlists and gamemodes can share the same name \(e.g. `custom_tdm`\)! You can differentiate them by looking in which block they're defined.
{% endhint %}

#### Gamemodes block

Gamemodes are **bases** which the playlists **build upon**. You do not typically need to modify anything in this block. Currently, we have as base gamemodes:

* `survival`: standard Apex Battle Royale experience
* `custom_tdm`:despite its name, it's a variable-team deathmatch experience with respawns

#### Playlists block

This is where you can define playlists in order to modify the behavior of the gamemodes. We will talk about this section more in just a bit.

{% hint style="info" %}
Multiple playlists can have the same base gamemode.
{% endhint %}

#### KVFileOverrides block

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

## Practical Example

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

## I want more!

Continue to the next section, where you can read about all of the KVs you can modify.

