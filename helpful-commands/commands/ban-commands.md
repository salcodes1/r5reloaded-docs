# 封禁指令

## 封禁客户端

按客户端名称封禁的方式如下所示：

```
ban 客户端名称
```

{% hint style="info" %}
 如果因为客户端名称带有特殊字符而导致无法禁用相应客户端，请参阅使用下面的banid。
{% endhint %}

按OriginID\(橘子ID\)/玩家顺位/IP地址进行封禁的方式如下所示：

```text
banid 橘子ID
banid 玩家顺位
banid IP地址

使用时不应该带有下列示例中以"#"号开头的文本

banid 1000000000   #橘子ID
banid 1            #玩家在服务器中的位置
banid 127.0.0.0    #IP地址
```

{% hint style="info" %}
您可以通过参考下面的链接页面来获取IP地址和玩家顺位。

{% page-ref page="status-command.md" %}
{% endhint %}

## 解封客户端

解封客户端的方式如下所示：

```text
unban 橘子ID
unban IP地址

使用时不应该带有下列示例中以"#"号开头的文本

unban 1000000000   #橘子ID
unban 127.0.0.0    #IP地址
```

{% hint style="info" %}
您可以从R5 Reloaded的根目录文件夹中的banlist.config来获取被封禁的客户端IP地址和橘子ID。
{% endhint %}

## 本地封禁列表

封禁客户端会在R5 Reloaded文件夹中的根目录创建封禁列表。.

封禁列表的文件名是 `banlist.config`

您可以手动在那里添加玩家，以通过IP地址或橘子ID来封禁他们。

或者也可以手动删除列表中的玩家来取消对他们的封禁。

{% hint style="danger" %}
确保在修改之后，检查banlist.config中列表的数据。

如果第一个条目名为1，请确保下一个条目名为2，以此类推；否则游戏可能会崩溃。
{% endhint %}

## 重新加载封禁列表

可以按如下方式重新加载封禁列表：

```text
reloadbanlist
```

