---
description: 工作區中的專案共用與專案角色
keywords: Analysis Workspace sharing
title: 共用工作區專案
translation-type: tm+mt
source-git-commit: 92dfb091a004ca7403f67e3f16527ea1e39cd01a
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 7%

---


# 共用工作區專案

>[!NOTE] 您正在檢視客戶歷程分析中分析工作區的檔案。 其功能集與傳統Adobe Analytics中 [的「分析工作區」略有不同](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html)。 [更多詳情...](/help/getting-started/cja-aa.md)

共用功能可讓組織中的其他分析工作區使用者使用專案。 收 [件者](curate.md) 開啟專案時，會反映您所套用的任何組織。

## 專案角色 {#Roles}

您可以將收件者新增至三個專案角色中的一個。 專案角色會系結至使用者和特定專案ID。 專案角色不受 [Adobe Experience Cloud管理控制台中管理的使用者權限影響](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/manage-users-and-products/admin-getting-started.html)。

| 角色 | 專案控制 |
|---|---|
| 可編輯 | 收件者可變更專案，以共同擁有者的身分操作。如果您想要與其他同事共同編輯專案，這個角色會很有用。<br>注意： 分析工作區目前不支援即時協作，因此建議在指定時間只有一位使用者編輯專案。 如果專案同時儲存，則會保留最後一個版本。 |
| 可重複 | 收件者可以「另存新檔」並存取左側導軌。 此角色不限於專案互動。 如果您想要將專案共用給瞭解組織資料以及如何使用分析工作區的使用者，但您不想變更專案，這個角色就很有用。 |
| 可檢視 | 收件者無法另存新檔，也無法存取左側導軌。 專案互動也有限。 如果您想要將專案共用給對您組織的資料結構、分析工作區或Adobe Analytics不太熟悉的使用者，這個角色就很有用。 不過，您仍希望他們在安全的環境中使用資料和見解。<br>進一步瞭解「可 [以檢視專案體驗」](/help/analysis-workspace/curate-share/view-only-projects.md)。 |

### 未分配角色

如果收件者未獲指派角色並收到專案的連結(**[!UICONTROL Share]>[!UICONTROL Get project link]**)，則依預設會將他們置於「 **[!UICONTROL Can view]** 」角色中。

### 指派多個角色

如果收件者被置於多個角色中，他們將永遠獲得最高體驗。 如果使用者同時以個人身分和群組的一部分新增，則可能會發生此情況。 例如，如果使用者獲得 **[!UICONTROL Can edit]** role as an dividual，而 **[!UICONTROL Can role as a group，則他們會收到]** Can edit **** project experience。

### 管理員和角色

被置於「可以 **[!UICONTROL 」或「]****** 可以檢視」角色的管理員，在開啟專案時，會收到這些有限的體驗。 視需要，管理員可將其角色增加為 **[!UICONTROL 隨時透過「元件]** >專案」 **[!UICONTROL 進行][!UICONTROL 編輯]**。

## 將收件者新增至共用專案 {#Add}

若要將收件者新增至共用專案：

1. 按一 **[!UICONTROL 下「共用]** >共 **[!UICONTROL 用專案」]**。
如果有未保存的更改，系統會提示您先保存項目。
1. 新增收件者或使用者群組。
請參考上方的說明圖示，以取得每個角色的說明。
1. （選用）與所有收件者共用內嵌的專案元件（區段、計算量度和日期範圍）。
共用後，這些元件會顯示在收件者工作區的「元件」下拉式清單中。 請注意，此設定不會持續存在——這是共用時的單一動作。
1. （可選）將此頁面設為收件者的登陸頁面。
這項動作不會沿用，僅在單次共用中有效。
1. 按一下「共用」。您也可以按一下「 **[!UICONTROL 組織」和「共用]** 」，自動套用專案組織。 如果專案已共用，這些按鈕會顯示「 **[!UICONTROL 更新]****[!UICONTROL 」和「組織與更新」]**。 進一步瞭解專 [案組織](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/curate-share/curate.html)。

![](assets/share-proj-modal.png)

## 共用給收件者群組 {#Groups}

所有使用者都可以將專案共用給群組，而群組是收件者的集合。 在Adobe Analytics中，群組是由 [Adobe Experience Cloud管理控制台中的產品設定檔所定義](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/manage-users-and-products/admin-getting-started.html)。

* 管理員可以共用給任何群組，包括「全部」。
* 非管理員可以共用給他們所屬的群組，但「全部」除外。

## 在專案經理中共用專案 {#Manager}

您也可以從「元件 **[!UICONTROL >專案」共]用專案**。 依照上述相同步驟，可共用單一專案。

如果選取多個專案以進行共用，收件者將會新增至每個專案的現有收件者清單。 例如：

* 專案A會共用給使用者1、2、3
* 專案B共用給使用者4、5、6
* 在選取專案A和B後，會將使用者4和7新增至收件者清單。 每個專案的新收件者清單現在為：
   * 專案A: 1, 2, 3, 4, 7
   * 項目B: 4, 5, 6, 7
   ![](assets/mult-proj-sharing.png)

## 常見問題解答 {#FAQs}

| 問題 | 回答 |
|---|---|
| 如果兩個編輯器同時儲存專案，會發生什麼情況？ | 不會合併變更，並保留上次儲存的專案版本。 分析工作區目前不支援即時協作。 |
| 身為管理員，我將看到哪些專案體驗？ | 被置於「可以 **[!UICONTROL 」或「]****** 可以檢視」角色的管理員，在開啟專案時，會收到這些有限的體驗。 視需要，管理員可將其角色增加為 **[!UICONTROL 隨時透過「元件]** >專案」 **[!UICONTROL 進行][!UICONTROL 編輯]**。 |
| 如果使用者以個人身分被置於某個角色，而以群組成員身分被置於另一個角色時，會發生什麼情況？ | 如果收件者被置於多個角色中，他們將永遠獲得更高的體驗。 例如，如果使用者獲得 **[!UICONTROL Can edit]** role as an dividual，而 **[!UICONTROL Can role as a group，則他們會收到]** Can edit **** project experience。 |
| 為什麼使用者在取得專案連結時會收到僅供檢視的體驗？ | 如果收件者未獲指派角色並收到專案的連結(**[!UICONTROL Share]>[!UICONTROL Get project link]**)，則依預設會將他們置於「 **[!UICONTROL Can view]** 」角色中。 如果用戶希望增加項目角色，項目所有者或編輯者可以通過項目共用模式將它們添加到「可以複製」或「可以編輯」角色。 |
