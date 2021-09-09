# KV 一覧表

**すべてのゲームモード**

| Name | Type | Notes |
| :--- | :--- | :--- |
| `min_players` | `int` | マッチ内でのプレイヤーの最少人数 |
| `max_players` | `int` | マッチ内でのプレイヤーの最大人数 |
| `max_team_players` | `int` | 人チームの最大人数 |
| `match_ending_enabled` | `bool` | マッチエンディングをを有効にするかどうか |
| `skydive_ziplines_enabled` | `bool` | ジャンプタワーを有効にするかどうか |
| `survival_jumpkit_enabled` | `bool` | 二段ジャンプを有効にするかどうか |
| `survival_wallrun_enabled` | `bool` | ウォールランを有効にするかどうか |
| `survival_infinite_ammo` | `bool` | 弾を無限にするかどうか |
| `ground_loot_enable` | `bool` | アイテムを地面にスポーンさせるかどうか |
| `lootbin_loot_enable` | `bool` | サプライボックスからアイテムをスポーンさせるかどうか。 |

## カスタム TDM

<table>
  <thead>
    <tr>
      <th style="text-align:left">Name</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">`</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>replay_enabled</code>
      </td>
      <td style="text-align:left"><code>bool</code>
      </td>
      <td style="text-align:left">&#x30AD;&#x30EB;&#x30EA;&#x30D7;&#x30EC;&#x30A4;&#x3092;&#x6709;&#x52B9;&#x306B;&#x3059;&#x308B;&#x304B;&#x3069;&#x3046;&#x304B;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>replay_delay</code>
      </td>
      <td style="text-align:left"><code>float</code>
      </td>
      <td style="text-align:left">&#x30EA;&#x30D7;&#x30EC;&#x30A4;&#x3092;&#x3069;&#x3053;&#x307E;&#x3067;&#x3055;&#x304B;&#x306E;&#x307C;&#x3089;&#x305B;&#x308B;&#x304B;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>default_shield_hp</code>
      </td>
      <td style="text-align:left"><code>float</code>
      </td>
      <td style="text-align:left">&#x3069;&#x308C;&#x3060;&#x3051;&#x306E;&#x30B7;&#x30FC;&#x30EB;&#x30C9;&#x3092;&#x6301;&#x3063;&#x3066;&#x30B9;&#x30DD;&#x30FC;&#x30F3;&#x3059;&#x308B;&#x304B;&#x3002;&#x30B7;&#x30FC;&#x30EB;&#x30C9;&#x306E;&#x7A2E;&#x985E;&#x306F;&#x81EA;&#x52D5;&#x8ABF;&#x6574;&#x3055;&#x308C;&#x307E;&#x3059;&#x3002;
        &#x4F8B;&#xFF1A;&#x9752;&#x306E;&#x30B7;&#x30FC;&#x30EB;&#x30C9;&#x306F;75</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>whitelisted_weapon_x</code>
      </td>
      <td style="text-align:left"><code>string</code>
      </td>
      <td style="text-align:left">
        <p>&#x30D7;&#x30EC;&#x30A4;&#x30E4;&#x30FC;&#x304C;&#x53D6;&#x5F97;&#x3067;&#x304D;&#x308B;&#x6B66;&#x5668;&#x3092;&#x5236;&#x9650;&#x3057;&#x305F;&#x3044;&#x5834;&#x5408;&#x306F;&#x3001;&#x6B66;&#x5668;&#x306E;&#x540D;&#x524D;&#x3092;&#x5165;&#x308C;&#x3066;&#x304F;&#x3060;&#x3055;&#x3044;&#x3002;</p>
        <p>&#x4F8B; KV: whitelisted_weapon_0 &quot;mp_weapon_mastiff&quot;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>oob_damage_percent</code>
      </td>
      <td style="text-align:left"><code>float</code>
      </td>
      <td style="text-align:left">&#x30D7;&#x30EC;&#x30A4;&#x30A8;&#x30EA;&#x30A2;&#x3092;&#x56F2;&#x3080;&#x30D0;&#x30D6;&#x30EB;&#x306E;&#x5916;&#x306B;&#x51FA;&#x305F;&#x5834;&#x5408;&#x3001;&#x3069;&#x308C;&#x3060;&#x3051;&#x306E;&#x30EA;&#x30F3;&#x30B0;&#x306E;&#x30C0;&#x30E1;&#x30FC;&#x30B8;&#x3092;&#x4E0E;&#x3048;&#x308B;&#x304B;
        &#x4F8B;&#xFF1A;&#x6700;&#x5927;&#x4F53;&#x529B;&#x306E;&#x304C;100&#x306E;&#x30BF;&#x30FC;&#x30B2;&#x30C3;&#x30C8;&#x306B;25&#x306E;&#x30D8;&#x30EB;&#x30B9;&#x30C0;&#x30E1;&#x30FC;&#x30B8;&#x3092;&#x4E0E;&#x3048;&#x308B;&#x306B;&#x306F;25</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>tgive_enabled</code>
      </td>
      <td style="text-align:left"><code>bool</code>
      </td>
      <td style="text-align:left"><code>tgive</code> &#x3067;&#x81EA;&#x5206;&#x306B;&#x6B66;&#x5668;&#x3092;&#x4E0E;&#x3048;&#x3089;&#x308C;&#x308B;&#x304B;&#x3069;&#x3046;&#x304B;</td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

