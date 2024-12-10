---
title: 使用拼接
description: 如何使用拼接
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
source-git-commit: 5e25cb4d974ab85cca3aa2bb777675e12f63038b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 使用拼接

當您的組織符合所有[必要條件](#prerequisites)並瞭解常見的[限制](#limitations)和拼接方法特定限制（[欄位式](#limitations-1)和[圖形式](#limitations-2)）時，您可以依照這些步驟開始在Customer Journey Analytics中使用拼接。

## 選取選項

您有權使用的Customer Journey Analytics套件會決定可用的拼接方法、初始回填持續時間、回顧視窗、重播頻率以及允許拼接的資料集數目上限。 如需詳細資訊，請參閱[Customer Journey Analytics產品說明](https://helpx.adobe.com/tw/legal/product-descriptions/customer-journey-analytics.html)。 在請求支援之前，請先決定可用的選項。

| | Customer Journey Analytics<br/>選取 | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| 可用的拼接方法 | <li>欄位式拚接</li> | <li>欄位式拚接</li><li>圖表式匯整</li> | <li>欄位式拚接</li><li>圖表式匯整</li> |
| 一次性拼接回填持續時間 | 13 個月 | 13 個月 | 25 個月 |
| 回顧期間和重播頻率 | <li>1天，每天</li><li>最長7天，每週</li> | <li>1天，每天</li><li>最長14天，每週</li> | <li>1天，每天</li><li>最長30天，每週</li> |
| 拼接允許的資料集數量上限 | 5 | 10 | 50 |

## 要求支援

1. 請聯絡 Adobe 客戶支援，提供下列資訊：

   - 啟用銜接的要求。
   - 您要重新輸入金鑰之資料集的資料集ID。
   - 所需資料集的永久ID欄名稱（身分路徑和名稱空間） （每列顯示的識別碼）。
   - 對於欄位式拚接，所需資料集的暫時ID欄名稱（人員ID，也會作為連線內容中資料集之間的連結）。 對於圖表式拚接，為用於查詢身分圖表的身分名稱空間。
   - 您的回顧視窗和重播頻率偏好設定。 檢視您可用的[選項](#options)的Customer Journey Analytics套件。
   - 沙箱名稱。


2. Adobe客戶支援與Adobe工程部門合作，以便在收到您的請求時啟用拼接。 啟用後，Adobe Experience Platform中會出現一個包含新拼接ID欄的新的重設金鑰資料集。 Adobe客戶支援可提供新資料集的ID。

3. 首次開啟時，Adobe會提供拼接資料的回填。 檢視您可用的[選項](#options)的Customer Journey Analytics套件。

4. 如果您想在跨管道分析中使用新的拼接資料集，您需要將新的拼接資料集新增到Customer Journey Analytics中的[連線](../connections/overview.md)。 然後新增跨管道分析所需的任何其他資料集，並為每個資料集選取正確的人員ID。

5. 根據連線[建立資料檢視](/help/data-views/create-dataview.md)。

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

設定資料檢視後，您可以跨管道和裝置執行Customer Journey Analytics報表分析。

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->



