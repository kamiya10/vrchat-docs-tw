# 角色接觸 (Contacts)

角色接觸 (Contacts) 是一個允許角色偵測與自己或其他角色碰撞的新系統。然後可以使用這些碰撞來驅動動畫控制器並執行各種有趣的效果。

這些與標準 Unity 碰撞器是分開的。角色接觸分為發送者和接收者。發送者只是為了被偵測而存在的，接收者偵測發送者，並且互相更新參數。

## VRCContactSender

Contact Sender 組件定義了在與 Contact Reciever 接觸時發送的 Contact 訊號的體積。

![](https://files.readme.io/59b6e82-2022-04-19\_11-53-01\_Unity.png)

`Root Transform` - 放置這個接觸的形變。如果為空，將使用這個遊戲物件的形變。

### 形狀 (Shape) <a href="#shape" id="shape"></a>

此部分包含定義 ContactSender 形狀的設定。\
`Shape Type` - 這個接觸使用的碰撞形狀。你可以在 Sphere 和 Capsule 之間進行選擇。\
`Radius` - 從原點延伸的的大小。\
`Height` - 膠囊沿所選軸的高度。\
`Position` - 從根形變的位置偏移量。\
`Rotation` - 從根形變的旋轉偏移量。

### 過濾 (Filtering) <a href="#filtering" id="filtering"></a>

這個部分包含讓你可以調整和定義這個 ContactSender 將如何與 [ContactReceivers](contacts.md#vrccontactreceiver) 互動的設定。

`Collision Tags` - 指定可以影響 / 受其影響的字串列表。為了成功發生碰撞，發送者與接收者都需要至少一對相對的字串。碰撞標籤區分大小寫。

舉個例子，下面的標籤將導致 Sender 在與預設的頭部 [ContactReceiver](contacts.md#vrccontactreceiver) 或任何帶有標籤 Face 的自定義 [ContactReceiver](contacts.md#vrccontactreceiver) 碰撞時發送接觸訊號 —— 注意大寫的 F！

![](https://files.readme.io/de34d55-2022-04-19\_11-53-34\_NVIDIA\_Share.png)

### 標準碰撞器 <a href="#standard-colliders" id="standard-colliders"></a>

一組「標準碰撞器」在 Avatar Descriptor 中位於一個名為「碰撞器」的新部分中定義。本節讓你可以定義存在於每個角色身上的許多標準碰撞器。如果你不去碰它，那這些將會被自動設定，但它們也可能以拿來調整來完全符合你的角色。這些碰撞器不會影響性能評級。

* 頭
* 軀幹
* 手（左/右）
* 腳（左/右）
* 手指（左/右）
  * 食指
  * 中指
  * 無名指
  * 小指

這些碰撞器主要充當 Contact Senders，其他人可以透過他們的角色偵測到。但是，手指和手部碰撞器也用於創建整體[物理骨骼](physbones.md)碰撞器，可用於影響其他人的物理骨骼。

## VRCContactReceiver

Contact Receiver 組件定義了在與 Contact Sender 接觸時接收的 Contact 訊號的體積。然後它將按照玩家定義的特定方式設定動畫器參數。

![](https://files.readme.io/6f84ac4-2022-04-19\_11-57-25\_NVIDIA\_Share.png)

`Root Transform` - 放置這個接觸的形變。如果為空，將使用這個遊戲物件的形變。

### 形狀 (Shape) <a href="#shape-1" id="shape-1"></a>

此部分包含定義 ContactReceiver 形狀的設定。\
`Shape Type` - 這個接觸使用的碰撞形狀。你可以在 Sphere 和 Capsule 之間進行選擇。\
`Radius` - 從原點延伸的的大小。\
`Height` - 膠囊沿所選軸的高度。\
`Position` - 從根形變的位置偏移量。\
`Rotation` - 從根形變的旋轉偏移量。

### 過濾 (Filtering) <a href="#filtering-1" id="filtering-1"></a>

這個部分包含讓你可以調整和定義這個 ContactReceivers 將如何與 [ContactSender](contacts.md#vrccontactsender) 互動的設定。

`Allow Self` - 允許這個接觸受到你自己的影響。\
`Allow Others` - 允許這個接觸受到其他人的影響。\
`Local Only` - 將這個接觸限制為僅在本機客戶端上運作。\
`Collision Tags` - 指定可以影響 / 受其影響的字串列表。為了成功發生碰撞，發送者與接收者都需要至少一對相對的字串。碰撞標籤區分大小寫。

### 接收器 (Receiver) <a href="#receiver" id="receiver"></a>

這個部分包含定義接收器在收到訊號時所做的行為。\
`Receiver Type` 定義接收訊號時設定參數的行為。

* `Constant` - 在有任何接觸時通知你。未偵測到接觸時重置。理想情況下，在這裡會使用布林值。為浮點數設為 `1.0`，為布林值設為 `True` ，為整數設為 `1`。
* `OnEnter` - 在偵測到接觸的幀通知你。下一幀重置。理想情況下，在這裡會使用布林值。為浮點數設為 `1.0`，為布林值設為 `True` ，為整數設為 `1`可以選擇定義 `Min Velocity`。
* `Proximity` - 根據接觸與觸發器中心的接近程度，提供 0.0 \~ 1.0 的浮點數。計算為發送者到接收者的最近點。必須使用浮點數。如果偵測到多個接觸，它將提供給最接近的接觸。

{% hint style="info" %}
如果你想要更精確地測量接近值，則將需要將 Sender 的半徑調整至非常小。
{% endhint %}

`Parameter` - 在動畫控制器上要更新的參數。這個參數不需要在同步的Avatar Parameter列表中定義。參數可以是浮點數、布林值或整數，具體取決於所使用的接收器類型。\
`Value` - 偵測到接觸時將參數更新成的值。當沒有接觸時，參數將重置為零。\
`Min Velocity` - 碰撞器影響這個觸發器所需的最小速度，僅在 OnEnter 類型中有效。
