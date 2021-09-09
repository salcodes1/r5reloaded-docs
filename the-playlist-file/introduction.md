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

複数のキータイプに対応しています

<table>
  <thead>
    <tr>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Explanation</th>
      <th style="text-align:left">Example</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>int</code>
      </td>
      <td style="text-align:left">&#x6570;&#x5024;</td>
      <td style="text-align:left"><code>3</code>, <code>-41</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>bool</code>
      </td>
      <td style="text-align:left">0(&#x306A;&#x3057;)&#x304B;1(&#x3042;&#x308A;)&#x306E;&#x307F;&#x3067;&#x3059;
        <br
        />
        <br />&#x901A;&#x5E38;&#x3001;replay_enabled&#x306A;&#x3069;&#x3001;2&#x3064;&#x306E;&#x5024;&#x3057;&#x304B;&#x306A;&#x3044;PlaylistVar&#x306B;&#x4F7F;&#x7528;&#x3055;
        &#x308C;&#x307E;&#x3059;&#x3002;</td>
      <td style="text-align:left"><code>0</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>float</code>
      </td>
      <td style="text-align:left">Rational numbers</td>
      <td style="text-align:left"><code>3.14</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>string</code>
      </td>
      <td style="text-align:left">
        <p>&#x6587;&#x5B57;&#x5217;
          <br />
        </p>
        <p><em><b>&quot;&#x306B;&#x56F2;&#x307E;&#x308C;&#x3066;&#x3044;&#x308B;&#x5FC5;&#x8981;&#x304C;&#x3042;&#x308A;&#x307E;&#x3059;&#x3002;</b></em>
        </p>
      </td>
      <td style="text-align:left"><code>&quot;mp_weapon_mastiff&quot;</code>
      </td>
    </tr>
  </tbody>
</table>

## 例

チームデスマッチもいいですが、プレイリストファイルには柔軟性があるので、コードを変更することなく、以下のプロパティを変更することで、自由参加\(free for all\)にすることができます。

```text
max_teams                          64
max_players                        64
max_team_players                   1
```

`max_team_players`という新しいKVを使っていることに注目してください。これにより、ゲームでは各チームに1人のプレーヤーしか残らないようにすることができます。

{% hint style="warning" %}
ただし、`max_players`が`max_teams`以上にならないようにしてください。
{% endhint %}

## もっと知りたい場合

次のセクションに進むと、変更可能なすべてのKVについて説明しています。

