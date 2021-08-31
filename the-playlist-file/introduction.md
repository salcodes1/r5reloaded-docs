# R5reloadedの紹介

## プレイリストファイルとは

プレイリストファイルは、ゲームディレクトリのplatformフォルダ内にあるプレーンテキストファイルで管理しています。

* デフォルトのパラメーター \(例. `match_ending_enabled`\)
* ゲームモード \(例. `custom_tdm`, `survival`\) がどのようなマップでプレイできるのか。
* ゲームモードのパラメーター \(例. `custom_tdm`に`default_shield_hp`\)

プレイリストファイルを使えば、コードが分からなくても、どんなゲームモードでもカスタマイズできます。

## プレイリストファイルを改変するには

テキストエディタ、コードエディタでファイルを開くだけです。

### プレイリストファイルの構成

プレイリストファイルには、ゲームモードとプレイリストがあります。ゲームモードは`Gamemodes`ブロック、プレイリストは`Playlists`ブロックで定義されています。また、ファイルの下部には`KVFileOverrides`があります。

{% hint style="warning" %}
プレイリストとゲームモードは同じ名前を使うことができます\(例：custom\_tdm\)。どのブロックで定義されているかで見分けることができます。
{% endhint %}

#### `Gamemodes`について

ゲームモードは、プレイリストのベースとなるものです。このブロックでは通常、何も変更する必要はありません。現在、ベースとなるゲームモードは次のとおりです。 

* `survival`: 標準的なバトルロイヤルです。
* `custom_tdm`:その名の通り、リスポーンのあるチームデスマッチです。

#### `Playlists`について

ここでは、ゲームモードの動作を変更するためのプレイリストを定義することができます。このセクションについては、後ほど詳しく説明します。

{% hint style="info" %}
複数のプレイリストが同じゲームモードを持つことができます。
{% endhint %}

#### `KVFileOverrides`について

ここでは、ダメージや弾薬の数など、武器の値を変更することができます。武器のプロパティを変更する方法については、「武器」のセクションで詳しく説明しています。

{% hint style="danger" %}
scripts/weapons/\*を変更するのではなく、この方法を使うことで、接続しているすべてのプレイヤーに変更が反映されるため、問題が発生しません。この方法では、同期ズレの問題や奇妙なバグは発生しません。
{% endhint %}

####  では、例を見てみましょう。

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

上記は、`custom_tdm`**プレイリスト**設定の一部です。すべてのプレイリスト設定はファイルの中にあります。

まず第一に、//の前にあるものはゲームでは読まれず、 **コメント** と名付けられます\(例://whitelisted\_weapon\)。コメントは、あなたが行ったことを他の人に理解してもらうため、あるいはあなたが書いたすべてのプロパティをきれいに整理するためにのみ存在します。よくあるのは、一時的に無効にしたいプロパティを削除せずにコメントしておくことで、ゲームはその内容を読みません。

```text
max_teams 2
```

上のコードでは、今後**KV**（`key-value`）またはPlaylistVarと呼ばれるものが出てきました。**Key**はプロパティ名（`max_teams`）で、値はそのプロパティの値（2）です。ゲームはこの**KV**を読み込んで、プレイヤーが2チームにしか分配されないようにするので、チームデスマッチには最適です。

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

