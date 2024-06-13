---
title: 標籤和原則
description: 了解 Adobe Experience Platform 中所定義的資料標籤和原則如何影響 Customer Journey Analytics 中的資料檢視和報告。
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
role: Admin
source-git-commit: 6526ca2b7caaf64acf29d97c859c3e813d003d2d
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 45%

---

# 標籤和原則

當您在Experience Platform中建立資料集時，可以建立 [資料使用情況標籤](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/reference) 資料集中的部分或全部元素。 您可以在 Customer Journey Analytics 中檢視這些標籤和原則。

以下是對 Customer Journey Analytics 特別重要的標籤：

* `C8` 標籤 - **[!UICONTROL 無測量]**。此標籤表示資料無法供貴組織的網站或應用程式進行分析之用。

* 此 `C12` 標籤 —  **[!UICONTROL 無一般資料匯出]**. 依此方式標示的綱要欄位無法從 Customer Journey Analytics (透過報告、匯出、API 等) 匯出或下載。

>[!NOTE]
>
>資料使用標籤不會自動傳播到合成資料集。不過可以手動新增。

加上標籤並不表示已強制執行這些資料使用標籤。使用標籤的方式由各項原則決定。您可以使用以下專案建立您的原則 [EXPERIENCE PLATFORMUI](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/policies/user-guide) 或透過 [原則服務API](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/api/overview) 在Experience Platform中。

Experience Platform中有兩個Adobe定義的原則會在Customer Journey Analytics中出現，並影響報表和資料匯出：

* **[!UICONTROL 限制使用分析和以使用者為基礎的測量]** 原則，使用 `C8` 標籤，和
* **[!UICONTROL 限制資料匯出]** 原則，使用 `C12` 標籤。

## 檢視 Customer Journey Analytics 資料檢視中的資料標籤

您或其他人在Experience Platform中建立的資料標籤會顯示在資料檢視使用者介面的三個位置：

| 位置 | 說明 |
| --- | --- |
| 結構描述欄位上的資訊按鈕 | 按一下此按鈕表示哪些[!UICONTROL 資料使用標籤]目前套用至欄位：<p>![](assets/data-label-left.png) |
| 右邊邊欄在[元件設定](/help/data-views/component-settings/overview.md)下方 | 此處列出任何[!UICONTROL 資料使用標籤]：<p>![](assets/data-label-right.png) |
| 將資料標籤做為一欄新增 | 您可以將[!UICONTROL 資料使用標籤]做為一欄新增到資料檢視中的「[!UICONTROL 包含的元件]」欄。只需選取欄選擇器圖示，然後選取 **[!UICONTROL 資料使用情況標籤]**：<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## 篩選資料檢視中的資料控管標籤

在資料檢視編輯器中，選取 [!UICONTROL 篩選] 圖示並以下列方式篩選資料檢視元件： **[!UICONTROL 資料控管]** 和型別 **[!UICONTROL 標籤]**：

![](assets/filter-labels.png)

按一下「**[!UICONTROL 套用]**」，以查看哪些元件附加標籤。

## 篩選資料檢視中的資料控管原則

您可以檢視原則(例如，您建立且名為 **[!UICONTROL 強制執行分析]**)已開啟。 以及該原則是否封鎖將某些Customer Journey Analytics資料檢視元素用於分析或資料匯出。

再次選取 [!UICONTROL 篩選] 圖示加以識別 **[!UICONTROL 資料控管]**，選取 **[!UICONTROL 原則]**：

![依顯示「限制使用分析」和已選取之使用者型測量的清單來篩選包含的元件](assets/filter-policies.png)

按一下 **[!UICONTROL 套用]** 以檢視已啟用哪些原則。

## 啟用的原則如何影響資料檢視

如果使用C8或C12標籤開啟一或多個原則，則套用某些資料標籤的結構描述元件無法新增到資料檢視。

這些元件會在左側邊欄中顯示為灰色 [!UICONTROL 結構描述欄位] 清單：

![反灰元件和原則訊息指出原則已套用到此限制資料使用的欄位](assets/component-greyed.png)

您無法儲存當中有已封鎖欄位的資料檢視。

在Experience Platform的欄位或欄位群組（您已在資料檢視中為其定義元件）上嘗試套用存取權和資料控管標籤（透過原則）時，請務必謹慎。 您可能會看到此對話方塊。

![違規](assets/violation.png)

您首先需要解決違規（例如從資料檢視中移除元件）。


>[!MORELIKETHIS]
>
>[下載敏感性資料](/help/analysis-workspace/export/download-send.md)

>[!MORELIKETHIS]
>
>[什麼是 Report Builder 中受限制的標籤？](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-reportbuilder/restricted-labels)


