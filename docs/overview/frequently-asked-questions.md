# 常見問題

## 為什麼我還不能上傳內容？ <a href="#why-cant-i-upload-content-yet" id="why-cant-i-upload-content-yet"></a>

你必須在我們的信任和安全系統中至少獲得「新用戶」信任等級後才能開始上傳內容。 你只需在 VRChat 上花幾個小時，跑一些世界，交一些朋友，就可以得到這個。 給它一些時間，你將能夠上傳內容。

順帶一題，你必須要有一個 VRChat 帳號才能上傳內容。這意味著你不能使用 Steam 帳號、Oculus 帳號或 Viveport 帳號來上傳世界或角色等內容。

## 我有一個 Steam 或 Oculus 帳號，我想將我的東西移轉過來來讓我可以上傳內容！ <a href="#i-have-a-steam-or-oculus-account-and-i-want-to-move-my-stuff-over-so-i-can-upload-content" id="i-have-a-steam-or-oculus-account-and-i-want-to-move-my-stuff-over-so-i-can-upload-content"></a>

如果你使用 Steam 或 Oculus 帳號，你可以輕鬆地將你的帳號「轉移」成 VRChat 帳號。當你在遊戲中時，到「Settings」選單，你會在右下角看到一個按鈕來讓你開始轉移！

請確保你要「轉換到」的帳號是一個空白的全新 VRChat 帳號。如果你的VRChat 帳號中有任何已保存的收藏夾或其他內容，你的 Steam/Oculus 帳號資料將不會被轉移！

## 如何製作自己的角色？ <a href="#how-can-i-make-my-own-custom-avatar" id="how-can-i-make-my-own-custom-avatar"></a>

很高興你問了！VRChat 有一個 Unity 軟體開發工具包 (SDK)，允許你為 VRChat 創建內容，包括角色。

要開始的話請查看[創建你的第一個角色](https://docs.vrchat.com/v2021.3.2/docs/creating-your-first-avatar)。

此外，YouTube 上還有大量由我們的社區製作的教學影片。

## 我可以創建我自己的世界嗎？ <a href="#can-i-create-my-own-world" id="can-i-create-my-own-world"></a>

可以，使用我們的 Unity SDK，你可以創建自己的世界。從一個私人世界開始，這意味著你只能通過打開傳送門或邀請朋友來讓他們加入。一旦你準備好公開世界時，首先你必須先完成將你的世界提交給[社區實驗室](https://docs.vrchat.com/v2021.3.2/docs/vrchat-community-labs)的任務。

## 我如何找到我自己的世界？ <a href="#how-can-i-access-my-world" id="how-can-i-access-my-world"></a>

使用 SDK 創建並上傳你的世界後，你將可以在世界選單中的的`Mine`標籤下找到你的世界。

## 我的遊戲程式有問題。 <a href="#im-having-a-problem-with-the-application" id="im-having-a-problem-with-the-application"></a>

我們很遺憾聽到這個消息！我們想幫助你解決問題。請先查看我們的[知識庫](https://help.vrchat.com/)，看看你是否可以在那裡找到解決方案。如果不行，請在[這裡](https://help.vrchat.com/new)創建 ticket 來聯繫我們的支持團隊。請確定你選擇了「SUP」類別。

## 這個叫「SDK」的東東是什麼東西啊？ <a href="#whats-this-sdk-thing" id="whats-this-sdk-thing"></a>

VRChat SDK 使玩家能夠使用 Unity3D 為 VRChat 創建互動式世界和角色。Unity 提供的大多數工具都可以在 VRChat 中使用，包括光照、導航網格、粒子、動畫和其他標準的 Unity 功能。

VRChat SDK 有兩個版本：

* VRChat SDK 2
* VRChat SDK 3

我們簡稱為「VRCSDK2」和「VRCSDK3」。你可以在我們的[選擇你的 SDK](https://docs.vrchat.com/v2021.3.2/docs/choosing-your-sdk) 文檔頁面上閱讀有關它們的更多資訊。

如果你想知道我們在角色和世界中究竟允許什麼，請查看[角色組件白名單](https://docs.vrchat.com/v2021.3.2/docs/whitelisted-avatar-components)和[世界組件白名單](https://docs.vrchat.com/v2021.3.2/docs/whitelisted-world-components)文檔頁面。

{% hint style="danger" %}
## Steam 帳號

你必須使用 VRChat 帳號（不是 Steam 或 Oculus 帳號）才能使用 SDK。你可以在[這裡](https://vrchat.com/register)註冊一個。
{% endhint %}

## 我什麼時候才可以開始在 SDK 中編寫腳本？ <a href="#when-can-i-start-scripting-in-the-sdk" id="when-can-i-start-scripting-in-the-sdk"></a>

我們不允許通過 MonoBehaviours 對 VRChat 中的任何內容編寫腳本。

不過，你可以使用 Udon 在世界中創建複雜的行為。我們正在為角色準備更複雜、更先進的功能。

## 我要如何找到 VRChat 的輸出日誌？ <a href="#how-do-i-find-the-vrchat-output-logs" id="how-do-i-find-the-vrchat-output-logs"></a>

VRChat 輸出日誌位於 `C:\Users[使用者名稱]\AppData\LocalLow\VRChat\vrchat`。 輸出日誌命名格式為 `output_log-HH-MM-SS.txt`。 你可以通過將以下字串黏貼到 Windows 檔案總管地址欄中來快速找到這個目錄：

`%AppData%..\LocalLow\VRChat\vrchat\`

你的日誌會保留 24 個小時，其中檔案名稱的 `HH-MM-SS` 部分描述了你啟動遊戲程式的時間。當 VRChat 啟動時，它會檢查是否有任何日誌超過 24 小時。如果有，它將會刪除掉它們。

## 我要如何清除 VRChat 快取？ <a href="#how-do-i-clear-the-vrchat-cache" id="how-do-i-clear-the-vrchat-cache"></a>

只需打開你的設定選單，點擊右上角「Advanced Settings」的按鈕，然後點「Clear Downloaded Content Cache」就好了！

### 手動方式 <a href="#manual-method" id="manual-method"></a>

或者，你可以使用手動方法：VRChat 快取資料夾位於 `C:\Users[使用者名稱]\AppData\LocalLow\VRChat\vrchat`。你可以通過將以下字串黏貼到 Windows 檔案總管地址欄中來快速找到這個目錄：

`%AppData%..\LocalLow\VRChat\vrchat\`

刪除以下資料夾：

`Cookies`\
`HTTPCache`\
`Unity`\
`VRCHTTPCache`\
`HTTPCache-WindowsPlayer`\
`Cache-WindowsPlayer`

不要刪除其他檔案（像是 `config.json` 或 `output_log.txt`），你可能會需要這些檔案。

如果你在 Oculus Quest 上遊玩 VRChat，解除安裝並重新安裝遊戲可以清除所有快取資料和設定。

## 我要如何清除我的本地設定檔資料？ <a href="#how-do-i-clear-my-local-profile-data" id="how-do-i-clear-my-local-profile-data"></a>

只需打開你的設定選單，點擊右上角「Advanced Settings」的按鈕，然後點「Clear All Local Profile Data」就好了！

### 手動方式 <a href="#manual-method-1" id="manual-method-1"></a>

要手動執行此操作，你可以使用登錄編輯程式。 在 Windows 上，打開登錄編輯程式並刪除 `HKEY_CURRENT_USER\Software\VRChat\vrchat`。 編輯你的 Windows 登錄檔可能會很危險，因此我們不建議使用此方法，除非你是高級使用者，或者支援人員指示你編輯登錄檔。

如果你在 Oculus Quest 上遊玩 VRChat，解除安裝並重新安裝遊戲可以清除所有快取資料和設定。

## 我在 PC 上遊玩 VRChat 後，就無法在 Quest 上玩了！ <a href="#after-playing-vrchat-on-my-pc-i-cant-play-on-quest" id="after-playing-vrchat-on-my-pc-i-cant-play-on-quest"></a>

如果你在遊玩 PC 後遊玩 Quest（包括其他 VR 耳機、桌面和 Quest Link 連接線）並且發生崩潰，請確保你的家世界設為相容 Quest 的世界並且你使用的是相容 Quest 的角色。

你可以到 VRChat 網站並在角色頁面上重置。

要重置您的家世界，你必須使用 PC 開啟 VRChat，並將你的家世界設定為相容 Quest 的世界，例如 VRChat Home。
