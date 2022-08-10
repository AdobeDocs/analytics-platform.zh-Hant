---
title: 標籤和策略
description: 瞭解AEP中定義的資料標籤和策略如何影響CJA中的資料視圖和報告。
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
source-git-commit: a28247e861e2f8853a6e2d2b81e7f6ed221caec0
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 2%

---

# 標籤和策略

>[!NOTE]
>
>此功能目前正在進行[有限測試](/help/release-notes/releases.md)。

在Experience Platform中建立資料集時，可以建立 [資料使用標籤](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) 資料集中的某些或所有元素。 到目前為止，這些標籤在CJA中還未公開。 在此版本中，您可以在CJA中查看這些標籤。 CJA特別感興趣的是以下標籤：

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
| 將資料標籤添加為列 | 可以添加 [!UICONTROL 資料標籤] 列 [!UICONTROL 包括的元件] 列。 只需按一下列選擇器表徵圖並選擇 **[!UICONTROL 資料使用標籤]**:<p>![](assets/data-label-column.png) |

{style=&quot;table-layout:auto&quot;}

## 篩選資料視圖中的資料治理標籤

在資料視圖編輯器中，按一下左側路徑中的「篩選器」表徵圖，然後按資料治理標籤/s篩選資料視圖元件：

![](assets/filter-labels.png)

按一下 **[!UICONTROL 應用]** 查看哪些元件具有附加標籤。

## 在資料視圖中篩選資料治理策略

您可以檢查是否開啟了阻止某些CJA資料視圖元素用於分析或導出目的的策略。

再次，按一下左欄中的「Filter（篩選器）」表徵圖，在「Data Governance（資料治理）」下按一下「Policies（策略）」：

![](assets/filter-policies.png)

按一下 **[!UICONTROL 應用]** 查看已啟用的策略。

## 如何 [!UICONTROL 強制分析] 策略影響工作區項目

如果開啟此策略，則與其關聯的某些資料標籤（如C8）的架構欄位不能用於CJA Workspace中的分析目的。

對於報告，這意味著

* 不能將這些欄位添加到資料視圖中，它們在左欄中呈灰色顯示 [!UICONTROL 架構欄位] 清單框。
* 無法保存已阻止其中欄位的資料視圖。

如果嘗試對包含禁止分析的項的資料視圖執行工作區分析，則會收到類似以下內容的通知：

![](assets/policy-enforce.png)

在單個元件上，消息將類似於以下內容：

![](assets/policy-enforce2.png)

## 如何 [!UICONTROL 強制下載] 策略影響工作區項目

如果開啟此策略，則Workspace項目的任何導出或下載（如電子郵件或共用pdf）都將對敏感欄位進行散列。 您仍然可以在Workspace中對這些欄位進行分析，但是，如果您嘗試通過電子郵件或以其他方式共用項目，則被阻止的欄位將作為散列項出現在.pdf檔案中。

在此處添加螢幕截圖。

## 查看Report Builder中的標籤

請參閱 _此部分_ 的子菜單。 （克莉絲汀醫生的連結）
