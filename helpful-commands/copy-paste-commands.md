# 複製貼上即可使用的指令

**鎖定角色**

```text
character_dummie                      hide       //假人
character_bangalore                   lock       //邦加羅爾
character_Bloodhound                  lock       //尋血犬
character_Caustic                     lock       //腐蝕
character_crypto                      lock    //暗碼士
character_Gibraltar                   lock       //直布羅陀
character_Lifeline                    lock       //生命線
character_Mirage                      lock       //幻象
character_Octane                      lock       //辛烷
character_Pathfinder                  lock       //探路者
character_wattson                     lock       //華森
character_Wraith                      lock       //惡靈
character_random                      lock       //隨機
```

**給武器**

```text
give mp_weapon_alternator_smg = Alternator       //轉換者衝鋒槍
give mp_weapon_defender = Charge Rifle           //電能步槍
give mp_weapon_esaw = Devotion                   //專注輕機槍(專注衝鋒槍)
give mp_weapon_epg = EPG                         //EPG(ttf2)
give mp_weapon_shotgun = EVA8                    //EVA-8自動
give mp_weapon_vinson = Flatline                 //平行步槍
give mp_weapon_g2 = G7                           //G7斥侯
give mp_weapon_energy_ar = Havoc                 //哈博克步槍
give mp_weapon_hemlok = Hemlok                   //汗洛
give mp_weapon_sniper = Kraber                   //克萊博
give mp_weapon_dmr = Longbow                     //長弓
give mp_weapon_lstar = Lstar                     //L-star
give mp_weapon_mastiff = Mastiff                 //獒犬霰彈槍
give mp_weapon_shotgun_pistol = Mozambique       //莫三比克
give mp_weapon_semipistol = P2020                //P2020
give mp_weapon_energy_shotgun = Peacekeeper      //和平使者
give mp_weapon_pdw = Prowler                     //獵獸
give mp_weapon_rspn101 = R301                    //R-301
give mp_weapon_r97 = R99                         //R-99
give mp_weapon_autopistol = RE45                 //RE45
give mp_weapon_smart_pistol = Smart Pistol       //智慧手槍(ttf2)
give mp_weapon_lmg = Spitfire                    //噴火槍
give mp_weapon_doubletake = Triple Take          //三重擊
give mp_weapon_wingman = Wingman                 //小幫手
```

**給武器\(多人遊戲\)**

```text
tgive mp_weapon_alternator_smg = Alternator     //轉換者衝鋒槍
tgive mp_weapon_defender = Charge Rifle         //電能步槍
tgive mp_weapon_esaw = Devotion                //專注輕機槍(專注衝鋒槍)
tgive mp_weapon_epg = EPG                      //EPG(ttf2)
tgive mp_weapon_shotgun = EVA8                   //EVA-8自動
tgive mp_weapon_vinson = Flatline                //平行步槍
tgive mp_weapon_g2 = G7                          //G7斥侯
tgive mp_weapon_energy_ar = Havoc                //哈博克步槍
tgive mp_weapon_hemlok = Hemlok                  //汗洛
tgive mp_weapon_sniper = Kraber                  //克萊博
tgive mp_weapon_dmr = Longbow                    //長弓
tgive mp_weapon_lstar = Lstar                    //L-star
tgive mp_weapon_mastiff = Mastiff                //獒犬霰彈槍
tgive mp_weapon_shotgun_pistol = Mozambique      //莫三比克
tgive mp_weapon_semipistol = P2020               //P2020
tgive mp_weapon_energy_shotgun = Peacekeeper     //和平使者
tgive mp_weapon_pdw = Prowler                    //獵獸
tgive mp_weapon_rspn101 = R301                   //R-301
tgive mp_weapon_r97 = R99                        //R-99
tgive mp_weapon_autopistol = RE45                //RE45
tgive mp_weapon_smart_pistol = Smart Pistol      //智慧手槍(ttf2)
tgive mp_weapon_lmg = Spitfire                   //噴火槍
tgive mp_weapon_doubletake = Triple Take         //三重擊
tgive mp_weapon_wingman = Wingman                //小幫手
```

**給帶有配件的武器**

```text
開啟作弊 = give [武器名稱] [配件名稱]
關閉作弊 = tgive [primary/secondary/tactical/ultimate] [武器名稱] [配件名稱]
//[primary主武器/secondary副武器/tactical技能/ultimate大招]，可輸入p代替primary依此類推
```

**給頭盔\(由上而下為等級1~4\)**

```text
script "Inventory_SetPlayerEquipment(gp()[0], \"helmet_pickup_lv1\", \"helmet\")"
script "Inventory_SetPlayerEquipment(gp()[0], \"helmet_pickup_lv2\", \"helmet\")"
script "Inventory_SetPlayerEquipment(gp()[0], \"helmet_pickup_lv3\", \"helmet\")"
script "Inventory_SetPlayerEquipment(gp()[0], \"helmet_pickup_lv4_abilities\", \"helmet\")"
```

**給包包\(由上而下為等級1~4\)**

```text
script "Inventory_SetPlayerEquipment(gp()[0], \"backpack_pickup_lv1\", \"backpack\")"
script "Inventory_SetPlayerEquipment(gp()[0], \"backpack_pickup_lv2\", \"backpack\")"
script "Inventory_SetPlayerEquipment(gp()[0], \"backpack_pickup_lv3\", \"backpack\")"
script "Inventory_SetPlayerEquipment(gp()[0], \"backpack_pickup_lv4_revive_boost\", \"backpack\")"
```

**給甲\(由上而下為等級1~4\)**

```text
script "Inventory_SetPlayerEquipment(gp()[0], \"armor_pickup_lv1\", \"armor\")"
script "Inventory_SetPlayerEquipment(gp()[0], \"armor_pickup_lv2\", \"armor\")"
script "Inventory_SetPlayerEquipment(gp()[0], \"armor_pickup_lv3\", \"armor\")"
script "Inventory_SetPlayerEquipment(gp()[0], \"armor_pickup_lv4_all_fast\", \"armor\")"
```

**給擊倒護盾\(由上而下為等級1~4\)**

```text
script "Inventory_SetPlayerEquipment(gp()[0], \"incapshield_pickup_lv1\", \"incapshield\")"
script "Inventory_SetPlayerEquipment(gp()[0], \"incapshield_pickup_lv2\", \"incapshield\")"
script "Inventory_SetPlayerEquipment(gp()[0], \"incapshield_pickup_lv3\", \"incapshield\")"
script "Inventory_SetPlayerEquipment(gp()[0], \"incapshield_pickup_lv4_selfrevive\", \"incapshield\")"
```

