---
title: 標籤和原則
description: 了解 Adobe Experience Platform 中所定義的資料標籤和原則如何影響 Customer Journey Analytics 中的資料檢視和報告。
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
role: Admin
source-git-commit: 6526ca2b7caaf64acf29d97c859c3e813d003d2d
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 100%

---

# 標籤和原則

在 Experience Platform 中建立資料集時，您可以為資料集中的部分或全部元素建立[資料使用情況標籤](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/data-governance/labels/reference)。您可以在 Customer Journey Analytics 中檢視這些標籤和原則。

以下是對 Customer Journey Analytics 特別重要的標籤：

* `C8` 標籤 - **[!UICONTROL 無測量]**。此標籤表示資料無法供貴組織的網站或應用程式進行分析之用。

* `C12` 標籤 - **[!UICONTROL 無一般資料匯出]**。依此方式標示的綱要欄位無法從 Customer Journey Analytics (透過報告、匯出、API 等) 匯出或下載。

>[!NOTE]
>
>資料使用標籤不會自動傳播到合成資料集。不過可以手動新增。

加上標籤並不表示已強制執行這些資料使用標籤。使用標籤的方式由各項原則決定。您可以使用 [Experience Platform UI](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/data-governance/policies/user-guide) 或透過 Experience Platform 上的[原則服務 API](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/data-governance/api/overview) 建立原則。

Experience Platform 提供兩種由 Adobe 定義的原則，這些原則可以在 Customer Journey Analytics 中顯示，並會影響報告和資料匯出：

* **[!UICONTROL 限制使用情況分析以及基於使用者的測量]**&#x200B;政策 (使用 `C8` 標籤)；以及
* **[!UICONTROL 限制資料匯出]**&#x200B;原則 (使用 `C12` 標籤)。

## 在 Customer Journey Analytics 資料視圖中檢視資料標籤

由您或其他人在 Experience Platform 中建立的資料標籤，會在資料視圖使用者介面中的三個位置顯示：

| 位置 | 說明 |
| --- | --- |
| 結構描述欄位上的資訊按鈕 | 按一下此按鈕表示哪些[!UICONTROL 資料使用標籤]目前套用至欄位：<p>![](assets/data-label-left.png) |
| 右邊邊欄在[元件設定](/help/data-views/component-settings/overview.md)下方 | 此處列出任何[!UICONTROL 資料使用標籤]：<p>![](assets/data-label-right.png) |
| 將資料標籤做為一欄新增 | 您可以將[!UICONTROL 資料使用標籤]做為一欄新增到資料檢視中的「[!UICONTROL 包含的元件]」欄。只需選取欄選擇器圖示，然後選取&#x200B;**[!UICONTROL 資料使用情況標籤]**：<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## 在資料視圖中按資料治理標籤進行篩選

在資料視圖編輯器中，選取左側邊欄中的「[!UICONTROL 篩選器]」圖示，然後依「**[!UICONTROL 資料治理]**」和「**[!UICONTROL 標籤]**」類型篩選資料視圖元件：

![](assets/filter-labels.png)

按一下「**[!UICONTROL 套用]**」，以查看哪些元件附加標籤。

## 篩選資料檢視中的資料控管原則

您可以檢查特定原則 (例如您建立的「**[!UICONTROL 強制執行 Analytics]**」原則) 是否已啟用，以該原則是否禁止特定的 Customer Journey Analytics 資料視圖元素用於分析或資料匯出。

再次選取左側邊欄中的「[!UICONTROL 篩選器]」圖示，然後在「**[!UICONTROL 資料治理]**」下方選取「**[!UICONTROL 原則]**」。

![依清單篩選包含的元件，當中顯示已選取「限制使用情況分析以及基於使用者的測量」](assets/filter-policies.png)

按一下「**[!UICONTROL 套用]**」，查看已啟用哪些原則。

## 啟用的原則如何影響資料視圖

如果啟用了帶有 C8 或 C12 標籤的一或多項原則，則已套用特定資料標籤的結構描述元件將無法加入資料視圖。

這些元件會在左側邊欄「[!UICONTROL 結構描述]」欄位清單中顯示為灰色：

![反灰元件和原則訊息指出原則已套用到此限制資料使用的欄位](assets/component-greyed.png)

您無法儲存當中有已封鎖欄位的資料檢視。

如果您已在資料視圖中為 Experience Platform 中的欄位或欄位群組定義了元件，則當您嘗試為這些欄位或欄位群組套用存取和資料治理標籤 (透過原則) 時，請務必小心謹慎。您可能會看到這個對話框。

![違規](assets/violation.png)

您需要先解決違規問題 (例如從資料視圖中移除元件)。


>[!MORELIKETHIS]
>
>[下載敏感性資料](/help/analysis-workspace/export/download-send.md)

>[!MORELIKETHIS]
>
>[什麼是 Report Builder 中受限制的標籤？](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-reportbuilder/restricted-labels)


