---
description: 工作區中的專案共用與專案角色
keywords: Analysis Workspace sharing
title: 共用工作區專案
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '1108'
ht-degree: 5%

---


# 共用工作區專案

>[!NOTE]
>
>您正在檢視客戶歷程分析中分析工作區的檔案。 其功能集與傳統Adobe Analytics中 [的「分析工作區」略有不同](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html)。 [更多詳情...](/help/getting-started/cja-aa.md)

共用功能可讓組織中的其他分析工作區使用者使用專案。 收 [件者](curate.md) 開啟專案時，會反映您所套用的任何組織。

## 專案角色 {#Roles}

您可以將收件者新增至三個專案角色中的一個。 專案角色會系結至使用者和特定專案ID。 專案角色不受 [Adobe Experience Cloud管理控制台中管理的使用者權限影響](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/manage-users-and-products/admin-getting-started.html)。

| 角色 | 專案控制 |
|---|---|
| 可編輯 | Recipients can **[!UICONTROL Save]** changes to a project and function as co-owners. 如果您想要與其他同事共同管理專案，則此角色很有用； 這包括編輯、刪除和修改共用專案的收件者清單。 <br>注意： 分析工作區目前不支援即時協作，因此建議在指定時間只有一位使用者編輯專案。 如果專案同時儲存，則會保留最後一個版本。 |
| 可重複 | 收件者可 **[!UICONTROL 以「另存新檔]** 」並存取左側導軌。 此角色不限於專案互動。 如果您想要將專案共用給瞭解組織資料以及如何使用分析工作區的使用者，但您不想變更專案，這個角色就很有用。 |
| 可檢視 | 收件者無法另存新檔，也無法存取左側導軌。 專案互動也有限。 如果您想要將專案共用給對您組織的資料結構、分析工作區或Adobe Analytics不太熟悉的使用者，這個角色就很有用。 不過，您仍希望他們在安全的環境中使用資料和見解。<br>進一步瞭解「可 [以檢視專案體驗」](/help/analysis-workspace/curate-share/view-only-projects.md)。 |

>[!IMPORTANT]
> 在2020年6月18日之前新增的專案收件者已移轉至專案角色。 已移轉至「可編輯」角 **[!UICONTROL 色的管理員]** ，以及移轉至「可複製」角色的「非 **[!UICONTROL 管理員」用戶]** 。 這些角色提供與先前相同的專案體驗。 此外，所有群組（包括「全部」）都會移轉至「 **[!UICONTROL 可複製]** 」角色。

### 未指派任何角色（專案連結收件者）

如果收件者未獲指派角色並收到專案連結(**[!UICONTROL Share]>[!UICONTROL Get project link]**)，則預設會將他們置於角色中。 管理員會 **[!UICONTROL 收到]** 「可以編輯」，非管理員會收到「 **[!UICONTROL 可以複製」]**。

### 指派多個角色

如果收件者被置於多個角色中，他們將永遠獲得最高體驗。 如果收件者同時以個人身分和群組的一部分新增，則可能發生此情況。 例如，如果收件者獲得「可以 **[!UICONTROL 編輯]** 」角色作為個人，而「可以 **[!UICONTROL 」角色作為群組的成員查看，他們將會收到「可以編輯]****** 」專案體驗。

### 管理員和角色

被置於「可以 **[!UICONTROL 」或「]****** 可以檢視」角色的管理員，在開啟專案時，會收到這些有限的體驗。 視需要，管理員可將其角色增加為 **[!UICONTROL 隨時透過「元件]** >專案」 **[!UICONTROL 進行][!UICONTROL 編輯]**。

## 將收件者新增至共用專案 {#Add}

若要將收件者新增至共用專案：

1. 按一 **[!UICONTROL 下「共用]** >共 **[!UICONTROL 用專案」]**。
如果有未保存的更改，系統會提示您先保存項目。
1. 新增收件者或收件者群組。
請參考上方的說明圖示，以取得每個角色的說明。
1. （選用）與所有收件者共用內嵌的專案元件（區段、計算量度和日期範圍）。
共用後，這些元件會顯示在收件者工作區的「元件」下拉式清單中。 請注意，此設定不會持續存在——這是共用時的單一動作。
1. （可選）將此頁面設為收件者的登陸頁面。
這項動作不會沿用，僅在單次共用中有效。
1. 按一下「共用」。您也可以按一下「 **[!UICONTROL 組織」和「共用]** 」，自動套用專案組織。 如果專案已共用，這些按鈕會顯示「 **[!UICONTROL 更新]****[!UICONTROL 」和「組織與更新」]**。 進一步瞭解專 [案組織](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-workspace/curate-share/curate.html)。

![](assets/share-proj-modal.png)

## 共用給收件者群組 {#Groups}

所有使用者都可以將專案共用給群組，而群組是收件者的集合。 在Adobe Analytics中，群組是由 [Adobe Experience Cloud管理控制台中的產品設定檔所定義](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/manage-users-and-products/admin-getting-started.html)。

* 管理員可以共用給任何群組，包括「全部」。
* 非管理員可以共用給他們所屬的群組，但「全部」除外。

## Share a project link {#Links}

您可以在「共用>取得專案」連結 **[!UICONTROL 下取得][!UICONTROL 專案連結]**。 按一下後，收件者必須先登入，才能登入專案。 如果收件者尚未被置於角色中，他們將會收到預設角色。 管理員會 **[!UICONTROL 收到]** 「可以編輯」，非管理員會收到「 **[!UICONTROL 可以複製」]**。

## 在專案經理中共用專案 {#Manager}

您也可以從「元件 **[!UICONTROL >專案」共]用專案**。 依照上述相同步驟，可共用單一專案。  如果選取多個專案以進行共用，收件者將會新增至每個專案的現有收件者清單。

例如：

* 專案A會共用給收件者1、2、3
* 專案B會共用給收件者4、5、6

在選取專案A和B後，收件者4和7會新增至共用清單。 現在，每個專案的新共用清單為：

* 專案A: 1, 2, 3, 4, 7
* 項目B: 4, 5, 6, 7

![](assets/mult-proj-sharing.png)

## 常見問題解答 {#FAQs}

| 問題 | 回答 |
|---|---|
| 如果兩個編輯器同時儲存專案，會發生什麼情況？ | 不會合併變更，並保留上次儲存的專案版本。 分析工作區目前不支援即時協作。 |
| 身為管理員，我將看到哪些專案體驗？ | 被置於「可以 **[!UICONTROL 」或「]****** 可以檢視」角色的管理員，在開啟專案時，會收到這些有限的體驗。 視需要，管理員可將其角色增加為 **[!UICONTROL 隨時透過「元件]** >專案」 **[!UICONTROL 進行][!UICONTROL 編輯]**。 |
| 如果收件者以個人身分被置於某個角色，而以群組成員身分被置於另一個角色，會發生什麼情況？ | 如果收件者被置於多個角色中，他們將永遠獲得更高的體驗。 例如，如果收件者獲得「可以 **[!UICONTROL 編輯]** 」角色作為個人，而「可以 **[!UICONTROL 」角色作為群組的成員查看，他們將會收到「可以編輯]****** 」專案體驗。 |
| 如果收件者開啟專案連結，會獲得哪些體驗？ | 收件者會收到您在分享模式中置入他們的角色。 如果收件者未獲指派角色，並收到專案的連結(**[!UICONTROL Share]>[!UICONTROL Get project link]**)，則預設會將他們置於角色中。 管理員會 **[!UICONTROL 收到]** 「可以編輯」，非管理員會收到「 **[!UICONTROL 可以複製」]**。 |
