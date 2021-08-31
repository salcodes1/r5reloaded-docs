# 自定义开发者菜单 \(不推荐\)

{% hint style="danger" %}
我们**不鼓励**在开发模式下搭建主机服务器。它引入了不必要的安全风险！与此相反，请参阅有关如何添加自定义菜单的页面。
{% endhint %}

1: 首先找到并打开 `\platform\scripts\vscripts\ai\sh_dev_npc_settings.gnut`并在文件的头部声明全局函数 `Type global function <Setup<something>` \(样例: global function SetupCustomThings\)

![](../.gitbook/assets/image%20%282%29.png)

  
2: 然后在文件的尾部添加一个新的无返回值函数类型 `Type "void function Setup<something>()"` \(样例: void function SetupCustomThings\(\)\)

3: 在空函数下，输入下列代码：

```text
{
    #if UI

    SetupDevCommand( "<Name you want to have displayed>", "give <name on the .txt file>" )

    #endif
}
```

4: 然后找到并打开 `\platform\scripts\vscripts\ui\menu_dev.nut` ，然后在第271行下输入新的菜单（将其放置在代码块中的位置=您希望它位于dev菜单中行的位置）

5: 找到菜单的位置后，输入： `SetupDevMenu( "<Name of the new dev menu>", SetDevMenu_<what you typed after "Setup" in your global and void function> )` \(样例: SetupDevMenu\( "Custom Community Things", SetDevMenu\_CustomThings \)\)

![](../.gitbook/assets/image%20%281%29.png)

6: 然后在第392行下添加一个新的无返回值函数：

```text
void function SetDevMenu_<what you typed after "Setup" in your global and void function>( var _ )
{
    thread ChangeToThisMenu( Setup<what you typed after "Setup" in your global and void function> )
}
```

![](../.gitbook/assets/image.png)

