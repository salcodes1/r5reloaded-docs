# カスタムDev Menuタブ

{% hint style="danger" %}
開発モードでのホスティングは推奨しません。不必要なセキュリティリスクが発生します。その代わりに、カスタムメニューを追加する方法のページを参照してください。
{% endhint %}

1:まず、上に入って新しいグローバル機能を追加します。

`\platform\scripts\vscripts\ai\sh_dev_npc_settings.gnut`の上に新しいグローバル関数を追加します `Type global function <Setup<something>` \(例: global function SetupCustomThings\)

![](../.gitbook/assets/image%20%282%29.png)

  
2: その後、下の方に行って、新しいvoid関数を追加します。`Type "void function Setup<something>()"` \(例: `void function SetupCustomThings()`\)

3: void関数の下には、次のように入力します。

```text
{
    #if UI

    SetupDevCommand( "<Name you want to have displayed>", "give <name on the .txt file>" )

    #endif
}
```

4: 次に、「menu\_dev.nut」にアクセスして、271行目に新しいメニューを入力してください\(コードの中に配置する＝開発メニューの中で配置したい場所に配置する\)

5: メニューの位置が決まったら、次のように入力します。`SetupDevMenu( "<Dev Menuに表示したい名前>", SetDevMenu_<2で定義した関数の名前> )` \(例: SetupDevMenu\( "Custom Community Things", SetDevMenu\_CustomThings \)\)

![](../.gitbook/assets/image%20%281%29.png)

6: 次に392行目の下に行き、新しいvoid関数を追加します。:

```text
void function SetDevMenu_<what you typed after "Setup" in your global and void function>( var _ )
{
    thread ChangeToThisMenu( Setup<what you typed after "Setup" in your global and void function> )
}
```

![](../.gitbook/assets/image.png)

