---
title: 標籤和策略
description: 瞭解AEP中定義的資料標籤和策略如何影響CJA中的資料視圖和報告。
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
source-git-commit: 1e2c5d79059a4804416288188ea4740dd94ca33d
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 2%

---

# 標籤和策略

>[!NOTE]
>
>此功能目前正在進行[有限測試](/help/release-notes/releases.md)。

在Experience Platform中建立資料集時，可以建立 [資料使用標籤](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) 資料集中的某些或所有元素。 到目前為止，這些標籤在CJA中還未公開。 在此版本中，您可以在CJA中查看這些標籤和策略。

CJA特別感興趣的是以下標籤：

* 的 `C8` 標籤 —  **[!UICONTROL 無測量]**。 此標籤表示無法將資料用於組織網站或應用上的分析。

* 的 `C12` 標籤 —  **[!UICONTROL 無常規資料導出]**。 無法從CJA（通過報告、導出、API等）導出或下載標有此方式的架構欄位

標籤本身並不意味著強制執行這些資料使用標籤。 這就是政策的用途。 通過 [策略服務API](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) Experience Platform。

CJA中出現了兩個Adobe定義的策略並影響報告和下載/共用：

* **[!UICONTROL 強制分析]** 政策
* **[!UICONTROL 強制下載]** 政策

## 在CJA資料視圖中查看資料標籤

在Experience Platform中建立的資料標籤顯示在資料視圖用戶介面的三個位置：

| 位置 | 說明 |
| --- | --- |
| 架構欄位上的「資訊」按鈕 | 按一下此按鈕可指示 [!UICONTROL 資料使用標籤] 當前應用於欄位：<p>![](assets/data-label-left.png) |
| 右滑軌下方 [元件設定](/help/data-views/component-settings/overview.md) | 任意 [!UICONTROL 資料使用標籤] 此處列出：<p>![](assets/data-label-right.png) |
| 將資料標籤添加為列 | 可以添加 [!UICONTROL 資料使用標籤] 列 [!UICONTROL 包括的元件] 列。 只需按一下列選擇器表徵圖並選擇 **[!UICONTROL 資料使用標籤]**:<p>![](assets/data-label-column.png) |

{style=&quot;table-layout:auto&quot;}

## 篩選資料視圖中的資料治理標籤

在資料視圖編輯器中，按一下左側路徑中的「篩選器」表徵圖，然後按 **[!UICONTROL 資料治理]** 和類型 **[!UICONTROL 標籤]**:

![](assets/filter-labels.png)

按一下 **[!UICONTROL 應用]** 查看哪些元件具有附加標籤。

## 在資料視圖中篩選資料治理策略

您可以檢查是否開啟了阻止某些CJA資料視圖元素用於分析或導出目的的策略。

再次，按一下左滑軌和下方的「過濾器」表徵圖 **[!UICONTROL 資料治理]**&#x200B;按一下 **[!UICONTROL 策略]**:

![](assets/filter-policies.png)

按一下 **[!UICONTROL 應用]** 查看已啟用的策略。

## 啟用的策略如何影響資料視圖

如果 **[!UICONTROL 強制分析]** 或 **[!UICONTROL 強制下載]** 開啟策略，那些與其關聯的某些資料標籤（如C8或C12）的架構元件不能添加到資料視圖。

這些元件在左滑軌中呈灰色顯示 [!UICONTROL 架構欄位] 清單：

![](assets/component-greyed.png)

您也無法保存已阻止其中欄位的資料視圖。

>[!MORELIKETHIS]
>[下載敏感資料](/help/analysis-workspace/curate-share/download-send.md)
