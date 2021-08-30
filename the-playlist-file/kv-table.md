# 关键数据\(KV\)表

{% tabs %}
{% tab title="所有游戏模式" %}
| 名称 | 类型 | 注解 |
| :--- | :--- | :--- |
| `min_players` | `int` | 开始一场比赛所需要的最小玩家数 |
| `max_players` | `int` | 最大玩家数限制 |
| `max_team_players` | `int` | 同队最多玩家数限制 |
| `match_ending_enabled` | `bool` | 冠军显示 |
| `skydive_ziplines_enabled` | `bool` | 启用滑索 |
| `survival_jumpkit_enabled` | `bool` | 二段跳模式 |
| `survival_wallrun_enabled` | `bool` | 滑墙模式 |
| `survival_infinite_ammo` | `bool` | 所有武器弹药不限 |
| `ground_loot_enable` | `bool` | 是否在地上刷出物品 |
| `lootbin_loot_enable` | `bool` | 物品是否在箱中刷出 |
{% endtab %}

{% tab title="自定义团队死斗" %}
<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x540D;&#x79F0;</th>
      <th style="text-align:left">&#x7C7B;&#x578B;</th>
      <th style="text-align:left">`&#x6CE8;&#x89E3;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>replay_enabled</code>
      </td>
      <td style="text-align:left"><code>bool</code>
      </td>
      <td style="text-align:left">&#x662F;&#x5426;&#x5E94;&#x542F;&#x7528;&#x51FB;&#x6740;&#x56DE;&#x653E;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>replay_delay</code>
      </td>
      <td style="text-align:left"><code>float</code>
      </td>
      <td style="text-align:left">&#x4F60;&#x5E0C;&#x671B;&#x51FB;&#x6740;&#x56DE;&#x653E;&#x6301;&#x7EED;&#x591A;&#x4E45;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>default_shield_hp</code>
      </td>
      <td style="text-align:left"><code>float</code>
      </td>
      <td style="text-align:left">
        <p>&#x8BBE;&#x7F6E;&#x73A9;&#x5BB6;&#x81EA;&#x5E26;&#x62A4;&#x76FE;&#x7B49;&#x7EA7;&#xFF0C;&#x81EA;&#x9002;&#x5E94;&#x8BBE;&#x7F6E;&#x3002;</p>
        <p>&#x4F8B;&#x5982; <code>75</code> &#x662F;&#x84DD;&#x7532;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>whitelisted_weapon_x</code>
      </td>
      <td style="text-align:left"><code>string</code>
      </td>
      <td style="text-align:left">
        <p>&#x5982;&#x679C;&#x4F60;&#x60F3;&#x9650;&#x5236;&#x73A9;&#x5BB6;&#x53EF;&#x4EE5;&#x5F97;&#x5230;&#x7684;&#x6B66;&#x5668;&#xFF0C;&#x8BF7;&#x5728;&#x540E;&#x9762;&#x5305;&#x542B;&#x6B66;&#x5668;&#x7684;&#x540D;&#x79F0;&#xFF1A;</p>
        <p></p>
        <p>&#x6837;&#x4F8B;: <code>whitelisted_weapon_0 &quot;mp_weapon_mastiff&quot;</code>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>oob_damage_percent</code>
      </td>
      <td style="text-align:left"><code>float</code>
      </td>
      <td style="text-align:left">
        <p>&#x5982;&#x679C;&#x73A9;&#x5BB6;&#x8D70;&#x51FA;&#x5305;&#x56F4;&#x7740;&#x6E38;&#x620F;&#x533A;&#x57DF;&#x7684;&#x8FB9;&#x754C;&#xFF0C;&#x4F1A;&#x81EA;&#x52A8;&#x5BF9;&#x73A9;&#x5BB6;&#x9020;&#x6210;&#x7684;&#x4F24;&#x5BB3;&#xFF1A;</p>
        <p>&#x4F8B;&#x5982;&#x8BBE;&#x4E3A; <code>25</code> &#x4F1A;&#x5BF9;&#x6700;&#x5927;&#x751F;&#x547D;&#x503C;&#x4E3A;100&#x7684;&#x73A9;&#x5BB6;&#x9020;&#x6210;25&#x70B9;&#x751F;&#x547D;&#x4F24;&#x5BB3;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>tgive_enabled</code>
      </td>
      <td style="text-align:left"><code>bool</code>
      </td>
      <td style="text-align:left">&#x662F;&#x5426;&#x901A;&#x8FC7; <code>tgive </code>&#x6765;&#x53D1;&#x653E;&#x6B66;&#x5668;</td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>
{% endtab %}
{% endtabs %}

