# KV Table

{% tabs %}
{% tab title="All Gamemodes" %}
| Name | Type | Notes |
| :--- | :--- | :--- |
| `min_players` | `int` | Minimum number of players required to start a match |
| `max_players` | `int` | Maximum player limit |
| `max_team_players` | `int` | Maximum number of players in a team |
| `match_ending_enabled` | `bool` | Champion screen |
| `skydive_ziplines_enabled` | `bool` | Activating ziplines |
| `survival_jumpkit_enabled` | `bool` | Double jump Mode |
| `survival_wallrun_enabled` | `bool` | Wallrun mode |
| `survival_infinite_ammo` | `bool` | Unlimited ammo for all weapons |
| `ground_loot_enable` | `bool` | Whether loot should spawn on the ground |
| `lootbin_loot_enable` | `bool` | Whether loot should spawn in loot bins |
{% endtab %}

{% tab title="Custom TDM" %}
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
      <td style="text-align:left">Whether kill replay should be enabled or not</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>replay_delay</code>
      </td>
      <td style="text-align:left"><code>float</code>
      </td>
      <td style="text-align:left">How far back do you want the replay to go</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>default_shield_hp</code>
      </td>
      <td style="text-align:left"><code>float</code>
      </td>
      <td style="text-align:left">
        <p>How much shield you spawn with. Shield type autoscales.</p>
        <p>e.g. <code>75</code> for a blue shield</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>whitelisted_weapon_x</code>
      </td>
      <td style="text-align:left"><code>string</code>
      </td>
      <td style="text-align:left">
        <p>If you want to restrict what weapons players can get, include the name
          of the weapons</p>
        <p></p>
        <p>Example KV: <code>whitelisted_weapon_0 &quot;mp_weapon_mastiff&quot;</code>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>oob_damage_percent</code>
      </td>
      <td style="text-align:left"><code>float</code>
      </td>
      <td style="text-align:left">
        <p>How much ring should damage you if you go outside the bubble encompassing
          the play area</p>
        <p>e.g. <code>25</code> to deal 25 health damage on a target with 100 max health</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>tgive_enabled</code>
      </td>
      <td style="text-align:left"><code>bool</code>
      </td>
      <td style="text-align:left">Whether you can give yourself weapons through <code>tgive</code>
      </td>
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

