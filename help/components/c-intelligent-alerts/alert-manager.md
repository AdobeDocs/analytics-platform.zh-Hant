---
description: 建立、編輯或刪除警報。
title: 管理警報
feature: Workspace Basics
role: User, Admin
exl-id: 174c3ebd-a77b-4403-ae9a-bb0cff4bcca6
source-git-commit: a85efff8720d8fdf02b0d1290fedf17654be48e3
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 21%

---

# 管理警報


您可以從中央[!UICONTROL 警示]管理介面篩選、標籤、刪除、重新命名、複製、啟用、停用更新及匯出警示。 若要管理警報：

* 在主介面中選取&#x200B;**[!UICONTROL 元件]**，然後選取&#x200B;**[!UICONTROL 警示]**。

警報管理員的結構類似於[區段管理員](/help/components/filters/manage-filters.md)和[計算量度管理員](/help/components/calc-metrics/cm-workflow/cm-manager.md)。


## 警報管理器

「警報」管理員具有下列介面元素：

![篩選器介面](assets/alerts-manager.png)

### 警示清單

警示清單➊會顯示您擁有的所有警示、已設定至您所有專案的警示，以及已與您共用的警示。 清單有以下欄位：

| 欄 | 說明 |
|---|---|
| ![StarOutline](/help/assets/icons/StarOutline.svg) | 選取以偏好![Star](/help/assets/icons/Star.svg)或取消偏好![StarOutline](/help/assets/icons/StarOutline.svg)警報。 |
| **[!UICONTROL 標題和說明]** | 若要編輯警報，請選取標題連結，以開啟[警報產生器](alert-builder.md#alert-builder)。 |
| **[!UICONTROL 類型]** | 顯示警示是Customer Journey Analytics資料警示還是伺服器呼叫使用量警示。 |
| **[!UICONTROL 已啟用]** | 指出警示是啟用還是停用。 |
| **[!UICONTROL 資料檢視]** | 套用此警報的資料檢視。 |
| **[!UICONTROL 所有者]** | 警示的擁有者。 如果您不是管理員，您只會看到自己所擁有或他人與您共用的警示。 |
| **[!UICONTROL 標記]** | 此警示的標籤。 |
| **[!UICONTROL 過期日期]** | 警示設為到期的日期和時間。 |
| **[!UICONTROL 修改日期]** | 上次修改警示的日期和時間。 |

<!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->

使用![ColumnSetting](/help/assets/icons/ColumnSetting.svg)指定要顯示的欄位。

### 動作列

您可以使用動作列對警報進➋行動作。 動作列包含以下動作：

| 圖示 | 動作 | 說明 |
|:---:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL 新增]** | 使用[警報產生器](alert-builder.md#alert-builder)新增另一個警報。 |
| ![Search](/help/assets/icons/Search.svg) | [!UICONTROL *依標題搜尋*] | 當清單中未選取警示時，請使用此搜尋欄位來搜尋警示。 |
| ![Label](/help/assets/icons/Label.svg) | **[!UICONTROL 標記]** | 標籤選取的警報。 在&#x200B;**[!UICONTROL 標籤警示]**&#x200B;對話方塊中，選取或取消選取所選警示的標籤。 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存所選警示的標籤。 |
| ![Delete](/help/assets/icons/Delete.svg) | **[!UICONTROL 刪除]** | 刪除選取的警示。 系統會提示您進行確認。 |
| ![Edit](/help/assets/icons/Edit.svg) | **[!UICONTROL 重新命名]** | 重新命名單一選取的警報。 選取後，您可以重新命名內嵌警報。 |
| ![Copy](/help/assets/icons/Copy.svg) | **[!UICONTROL 複製]** | 複製選取的警報。 已建立具有相同名稱與尾碼`(Copy)`的新警示。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL 啟用]**&#x200B;或&#x200B;**[!UICONTROL 停用]** | 啟用或停用選取的警示。 |
| ![重新整理](/help/assets/icons/Refresh.svg) | **[!UICONTROL 續約]** | 續約警報的到期日。無論原始到期日為何，到期日都會從您選取此選項的當天算起延長1年。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL 匯出至 CSV]** | 將警示匯出至`Alerts List.csv`檔案。 |


### 使用中的篩選欄

篩選器列會顯➌示從篩選器面板套用至警報清單的作用中篩選器（如果有的話）。 您可以使用![CrossSize75](/help/assets/icons/CrossSize75.svg)快速移除篩選條件。如果指定多個篩選條件，您可以使用&#x200B;**[!UICONTROL 移除全部]**&#x200B;來移除所有篩選條件。


### 篩選面板

您可以使用![篩選器](/help/assets/icons/Filter.svg) **[!UICONTROL 篩選器]**&#x200B;左側面板➍來篩選警示清單。 篩選器面板會顯示篩選器的型別，以及遵循特定篩選器的警示數目。


1. 選取![Filter](/help/assets/icons/Filter.svg)開啟「篩選」面板。如果您需要更多空間以儲存警示清單，可以再次選取![篩選器](/help/assets/icons/Filter.svg)以關閉面板。
1. 從任何可用的篩選器區段中選取篩選器。


#### 標籤篩選區段

{{tagfiltersection}}


#### 資料檢視篩選區段

{{dataviewfiltersection}}


#### 「擁有者」篩選器區段

{{ownerfiltersection}}


#### 已啟用狀態篩選區段

{{enabledstatusfiltersection}}


#### 輸入篩選區段

{{typefiltersection}}


#### 其他篩選器篩選器區段

{{otherfiltersfiltersection}}



## 編輯警報

您可以編輯警報

* 在[[!UICONTROL 警示]清單](#alerts-list)中，選取警示的標題。

您使用[警報產生器](alert-builder.md#alert-builder)來編輯警報。

## 疑難排解警報

對警報問題進行疑難排解時，請向Adobe支援提供JID （工作執行個體ID）編號。 JID號碼位於您收到的警報電子郵件通知底部。

![警報電子郵件](assets/alerts-email.PNG)
