# カスタム開発メニュータブ

{% hint style="danger" %}
開発モードでのホスティングは推奨しません。不必要なセキュリティリスクが発生します。その代わりに、カスタムメニューを追加する方法のページを参照してください。
{% endhint %}

1:まず、トップに入って新しいグローバル機能を追加します。 `\platform\scripts\vscripts\ai\sh_dev_npc_settings.gnut`and adds in the top a new global function `Type global function <Setup<something>` \(例: global function SetupCustomThings\)

![](../.gitbook/assets/image%20%282%29.png)

  
2: その後、下の方に行って、新しいvoid関数を追加します。`Type "void function Setup<something>()"` \(Example: void function SetupCustomThings\(\)\)

3: void関数の下には、次のように入力します。:

```text
{
    #if UI

    SetupDevCommand( "<Name you want to have displayed>", "give <name on the .txt file>" )

    #endif
}
```

4: then you gotta go to `\platform\scripts\vscripts\ui\menu_dev.nut` and under line 271 can you type your new menu up \(place it in the code = where in line you want it to be in the dev menu\)

5: then you have found where you want the menu to be then type `SetupDevMenu( "<Name of the new dev menu>", SetDevMenu_<what you typed after "Setup" in your global and void function> )` \(Example: SetupDevMenu\( "Custom Community Things", SetDevMenu\_CustomThings \)\)

![](../.gitbook/assets/image%20%281%29.png)

6: then go down under line 392 and add a new void function:

```text
void function SetDevMenu_<what you typed after "Setup" in your global and void function>( var _ )
{
    thread ChangeToThisMenu( Setup<what you typed after "Setup" in your global and void function> )
}
```

![](../.gitbook/assets/image.png)

