# 踢出指令

## 踢出客户端

按客户端名称踢出的方式如下所示：

```text
kick 客户端名称
```

{% hint style="info" %}
如果因为客户端名称带有特殊字符而导致无法踢出相应客户端，请参阅使用下面的kickid。
{% endhint %}

按OriginID\(橘子ID\)/玩家顺位/IP地址进行踢出的方式如下所示：

```text
kickid 橘子ID
kickid 玩家顺位
kickid IP地址

使用时不应该带有下列示例中以"#"号开头的文本

kickid 1000000000   #橘子ID
kickid 1            #玩家在服务器中的位置
kickid 127.0.0.0    #IP地址
```



{% hint style="info" %}
您可以通过参考下面的链接页面来获取IP地址和玩家顺位。

{% page-ref page="status-command.md" %}
{% endhint %}





