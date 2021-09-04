# 簡介

## 什麼是playlist呢?

playlist是一個純文字檔，位於遊戲的`platform` 資料夾。他負責管理:

* 預設的遊戲參數\( 如決定遊戲是否會結束的`match_ending_enabled`\)
* 遊戲模式\(如`custom_tdm`, `survival`\) 以及地圖
* 遊戲參數 \(如`custom_tdm`模式中出生時甲的血量 `default_shield_hp`\)

透過playlist檔案，不需要具備寫程式的基礎即可自訂義任何遊戲模式。

## 如何修改playlist檔案?

簡單，用任何的文字編輯器都可以。個人喜歡Notepad++，即使意外關機仍會保留檔案\(但需要手動儲存\)。

### 結構

在playlist檔案中，有`Gamemodes` 以及`Playlists`兩大區塊。遊戲模式定義在`Gamemodes`，而playlist定義在`Playlists` 區塊。 在最下面，還能發現 `KVFileOverrides`.

{% hint style="warning" %}
Playlists 以及遊戲模式\(Gamemodes\) 可以使用相同名稱\(如`custom_tdm`\)! 你可以透過他們在不同的區塊來分辨它們。
{% endhint %}

#### 遊戲模式\(Gamemodes\)區塊

遊戲模式是playlist的基礎。通常來說，你不需要在這裡修改任何東西。目前，我們有這些遊戲模式:

* `survival`: 標準的Apex大逃殺模式
* `custom_tdm`:d顧名思義，是個可以重生、分為多個隊伍的死鬥模式。

#### Playlist 區塊

這是你定義遊戲模式的行為的地方，聽不太懂沒關係，請容我繼續往下說明。

{% hint style="info" %}
不同的playlist可以擁有相同的遊戲模式\(Gamemode\)
{% endhint %}

#### KVFileOverrides 區塊

這是你修改武器數值的地方，如傷害、彈匣容量等。之後會在武器修改的章節說明怎麼自定義。

{% hint style="danger" %}
我們建議用這裡來修改而不是去動 `scripts/weapons/*` 的檔案，因為這些數值更動必須傳到每個連線到你伺服器的客戶端，用這裡更動比較不會有不同步的問題。
{% endhint %}

####  來囉，以下是一個範例:

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

以上是`custom_tdm` **playlist**設定中的一小部分，你可以在檔案中找到完整版本。

首先，有點程式語言基礎的人應該知道， `//` 是不會被遊戲讀取成要執行的程式的，稱為註解，用來讓陌生人能簡單讀懂你寫的是什麼意思，或是用來分類。一個必學技巧，可以透過在設定前面加上`//`來快速的暫時停用這項設定，不用刪除，方便許多。

```text
max_teams 2
```

上面的程式，我們稱之為**關鍵字數值 \(KV,** key-value\) 或 **PlaylistVar** 。  
`max_teams`即為關鍵字，簡單理解為這項設定的名稱；而`2`就是該項設定的數值。  
遊戲將會讀取這條關鍵字數值**KV**，如同它的名稱，將全部人分成最多兩隊，正好適合死鬥模式。  


數值有這幾種**資料型態**:

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>&#x8CC7;&#x6599;</p>
        <p>&#x578B;&#x614B;</p>
      </th>
      <th style="text-align:left">&#x7C21;&#x4ECB;</th>
      <th style="text-align:left"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>int</code>
      </td>
      <td style="text-align:left">&#x6574;&#x6578;</td>
      <td style="text-align:left"><code>3</code>, <code>-41</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>bool</code>
      </td>
      <td style="text-align:left">&#x5FC5;&#x9808;&#x662F;<code>0</code> &#x6216; <code>1</code>
      </td>
      <td style="text-align:left"><code>0</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>float</code>
      </td>
      <td style="text-align:left">&#x6709;&#x7406;&#x6578;</td>
      <td style="text-align:left"><code>3.14</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>string</code>
      </td>
      <td style="text-align:left">&#x7D14;&#x6587;&#x5B57;&#xFF0C;<b>&#x5FC5;&#x9808;&#x88AB;<code>&quot;&quot;</code>&#x5305;&#x4F4F;</b>
      </td>
      <td style="text-align:left"><code>&quot;mp_weapon_mastiff&quot;</code>
      </td>
    </tr>
  </tbody>
</table>

## 實際範例

有了playlist檔案，就可以自由的修改想要的配置。像這樣修改，團隊死鬥就變成了FFA，從所有玩家分成兩隊變成每個玩家都是自己solo。

```text
max_teams                          64
max_players                        64
max_team_players                   1
```

注意到我們使用了一個新的**關鍵字數值** `max_team_players`，這將強制一個隊伍只有一個人。

{% hint style="warning" %}
在每隊只有一人的情況下，確保 `max_players` 小於 `max_teams` ，否則遊戲將沒有足夠的隊伍分配給玩家。
{% endhint %}

## 我想看更多!

下一章節你可以看到所有能夠修改的**關鍵字數值。**

