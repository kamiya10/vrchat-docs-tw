# 測試內容

{% hint style="warning" %}
## 此頁面可能已過時

這頁在原文最後更新為**一年前**，內容可能已過時，在這裡先打個預防針。\
趕快叫VRChat 官方更新這頁吧！
{% endhint %}

## 測試場景 <a href="#testing-a-scene" id="testing-a-scene"></a>

要在 VRChat 中測試你在 Unity 中創建的場景，你需要先使用你的 VRChat 帳號登入，方法是到 VRChat 選單，然後選擇 `VRChat SDK > Show Control Panel > Authentication`。登入後，到「設定」分頁確保安裝的客戶端路徑正確並指向 VRChat.exe。

現在到 `VRChat SDK > Show Control Panel > Builder`。如果它要求你添加場景敘述器，請到 `Assets > VRCSDK > Prefabs > World`，將 VRCWorld 拖到你的場景中，並將它放在你希望玩家重生的地方。

在 Builder 分頁中有 2 個選項。要在本地在 VRChat 中測試你的世界而不上傳您要選擇的內容，請在離線測試部分點擊`Build & Test`。 點擊按鈕後，Unity 將構建場景的 VRChat 版本，然後啟動 VRChat 並載入你的世界。

## 測試角色 <a href="#testing-an-avatar" id="testing-an-avatar"></a>

目前無法在本地測試角色。如要測試角色，請將它上傳到你的帳號並在遊戲中選擇它作為角色。
