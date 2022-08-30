---
title: 標籤和原則
description: 了解在 AEP 中定義的資料標籤和原則如何影響 CJA 中的資料檢視和報告。
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
source-git-commit: 7962114aaab42a283f1cb35a312b0a707038c31a
workflow-type: ht
source-wordcount: '468'
ht-degree: 100%

---

# 標籤和原則

在 Experience Platform 中建立資料集時，您可以針對資料集中的部分或全部元素建立[資料使用標籤](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=zh-Hant)。到目前為止，這些標籤尚未在 CJA 中公開。有了此版本，您可以在 CJA 中檢視這些標籤和原則。

這些標籤與 CJA 特別有關：

* `C8` 標籤 - **[!UICONTROL 無測量]**。此標籤表示資料無法用於組織網站或應用程式上的分析。

* `C12` 標籤 - **[!UICONTROL 無一般資料匯出]**。依此方式標示的結構元素欄位無法從 CJA (透過報告、匯出、API 等) 匯出或下載。

當中的標示並不表示已強制執行資料使用標籤。那是使用原則之處。您透過 Experience Platform 中的[原則服務 API](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=zh-Hant) 建立您的原則。

兩個 Adobe 定義的原則會在 CJA 中出現，並影響報告和下載/共用：

* **[!UICONTROL 強制執行 Analytics]** 原則
* **[!UICONTROL 強制執行下載]**&#x200B;原則

## 檢視 CJA 資料檢視中的資料標籤

在 Experience Platform 中建立的資料標籤會在資料檢視使用者介面中的三個位置中出現：

| 位置 | 說明 |
| --- | --- |
| 結構描述欄位上的資訊按鈕 | 按一下此按鈕表示哪些[!UICONTROL 資料使用標籤]目前套用至欄位：<p>![](assets/data-label-left.png) |
| 右邊邊欄在[元件設定](/help/data-views/component-settings/overview.md)下方 | 此處列出任何[!UICONTROL 資料使用標籤]：<p>![](assets/data-label-right.png) |
| 將資料標籤做為一欄新增 | 您可以將[!UICONTROL 資料使用標籤]做為一欄新增到資料檢視中的「[!UICONTROL 包含的元件]」欄。按一下欄選擇棄，然後選取&#x200B;**[!UICONTROL 資料使用標籤]**：<p>![](assets/data-label-column.png) |

{style=&quot;table-layout:auto&quot;}

## 篩選資料檢視中的資料控管標籤

在資料檢視編輯器中，按一下左側邊欄中的篩選圖示，然後依&#x200B;**[!UICONTROL 資料控管]**&#x200B;和&#x200B;**[!UICONTROL 標籤]**&#x200B;類型篩選資料檢視元件：

![](assets/filter-labels.png)

按一下「**[!UICONTROL 套用]**」，以查看哪些元件附加標籤。

## 篩選資料檢視中的資料控管原則

您可以查看是否開啟原則 (封鎖將某些 CJA 資料檢視元素用於分析或匯出)。

再次按一下左側邊欄中的篩選圖示，然後在「**[!UICONTROL 資料控管]**」下方按一下「**[!UICONTROL 原則]**」。

![](assets/filter-policies.png)

按一下「**[!UICONTROL 套用]**」，以查看已啟用哪些原則。

## 啟用的原則如何影響資料檢視

如果已開啟&#x200B;**[!UICONTROL 強制執行分析]**&#x200B;或&#x200B;**[!UICONTROL 強制執行下載]**&#x200B;原則，這些關聯某些資料標籤 (C8 或 C12) 的結構描述元件無法新增到資料檢視。

這些元件會在左側邊欄「[!UICONTROL 結構描述」欄位]清單中反灰：

![](assets/component-greyed.png)

您無法儲存當中有已封鎖欄位的資料檢視。

>[!MORELIKETHIS]
>[下載敏感性資料](/help/analysis-workspace/curate-share/download-send.md)

>[!MORELIKETHIS]
>[什麼是 Report Builder 中受限制的標籤？](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/restricted-labels.html?lang=zh-Hant)


