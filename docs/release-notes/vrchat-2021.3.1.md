---
description: 發布 - 2021/7/8 - 遊戲內版本 1113
---

# VRChat 2021.3.1

## 客戶端

### &#x20;變更、修復和雜項

* **網路行為的重大改進。**這應該解決人們在實例中停留一段時間後遇到「斷斷續續的 IK」的問題
* 修正：SDK3 世界中的影片播放器在遇到錯誤後會導致音訊/影訊不同步
* 修正：「允許角色複製」設置可能在玩家之間不同步
*

    修正：Holoport 游標會在啟動時直到收到任何其他輸入為止出現
*

    修正：玩家可能會被無意中踢出具有特定世界設定的世界
*

    修正了一個取消世界最愛的錯誤
*

    修正了一些與卸載內容相關的崩潰
*

    修正跳躍不適用於 Holoport 的問題
*

    將 AVPro 升級到 2.1.5
*

    減少畫面hitching的改進
*

    角色卸載的改進

## Udon

* &#x20;**預設**情況下的新的影片播放器同步將會是**關閉**的！ SDK 會提示你並通知你應該啟用它。這樣做是因為如果重新同步太多次（例如，每秒多次），新的同步方法就會出現問題。你真的不應該頻繁地同步。每隔幾秒鐘檢查一次就足夠了。
* &#x20;為 `SetProgramVariable`、`SendCustomEvent`、`GetProgramVariable` 及其變量添加了下拉選單。如果節點使用了有效的 UdonBehavior，你現在可以看到目標變量和事件的列表。

![](../.gitbook/assets/7b9f34d-image\_5.png)

* &#x20;「Set Variable」節點現在有一個 `sendChange` 選框，如果它被選中，它將觸發該變量的 `OnVariableChanged` 事件。
* &#x20;[添加了 `OnVariableChanged` 事件節點](https://docs.vrchat.com/v2021.3.2/docs/special-nodes#on-variable-changed)，當它通過 `SetProgramVariable` 或 `SetVariable` 更改時提供變量的新值和舊值，並打開 `sendChange`。此更改也適用於同步變量！通過按住 Alt 鍵並將變量拖到圖表上，在節點圖表中可以找到這個事件。
* 更改了重新命名或刪除變量後重新載入圖形的行為
* &#x20;添加了 `PostLateUpdate`，一個將在計算 IK 後接近幀結束時發生的事件。 此時獲取骨骼位置將為您提供最新的位置，這樣它們就不會落後一幀。
* 更新了 `UdonExampleScene` 以盡可能使用 `OnVariableChange` 事件而不是 `OnDeserialization`。
* 修復了在檢查從 `UnityEngine.Object` 繼承的類別的已刪除實例是否為 `null` 時，Udon 會因 NullReferenceException 崩潰的問題。 感謝 Merlin 的幫助！
* 將大量的 `UdonBehaviour` 事件移動到組件：`OnAnimatorMove`、`OnCollisionStay`、`OnTriggerStay`、`OnRenderObject` 和 `OnWillRenderObject` 僅在您的程式使用它們時才會被調用。 感謝 Merlin 在這方面的初步作業！

