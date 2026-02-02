---
title: 請求拼接
description: 瞭解如何請求拼接。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a04c74ab-606e-45a9-a3e4-0d476c8d2426
source-git-commit: a94f3fe6821d96c76b759efa3e7eedc212252c5f
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 20%

---

# 請求拼接


>[!IMPORTANT]
>
>不再需要透過Adobe彙整請求，且此方法已過時。 [在連線UI中啟用拼接](use-stitching-ui.md)。
>

當您的組織符合一般[必要條件](overview.md#prerequisites)、瞭解一般[限制](overview.md#limitations)，以及拼接方法特定的（[欄位式](fbs.md)和[圖表式](gbs.md)）先決條件和限制時，您可以依照這些步驟來請求並開始在Customer Journey Analytics中使用拼接。

## 選取選項

您有權使用的Customer Journey Analytics套件會決定可用的拼接方法、初始回填持續時間、回顧視窗、重播頻率以及允許拼接的資料集數量上限。 如需詳細資訊，請參閱[Customer Journey Analytics產品說明](https://helpx.adobe.com/tw/legal/product-descriptions/customer-journey-analytics.html)。 在請求支援之前，請先決定可用的選項。

| | Customer Journey Analytics<br/>選取 | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| 可用的拼接方法 | 欄位型拼接 | 欄位式拚接<br/>圖表式拚接 | 欄位式拚接<br>圖表式拚接</li> |
| 一次性拼接回填持續時間 | 13 個月 | 13 個月 | 25 個月 |
| 回顧期間和重播頻率 | 1天，每天<br/>最多7天，每週 | 1天，每天<br/>最多14天，每週 | 1天，每天<br/>最多30天，每週 |
| 拼接允許的資料集數量上限 | 5 | 15 | 50 |

## 要求支援

1. 請聯絡 Adobe 客戶支援，提供下列資訊：

   - 啟用銜接的要求。
   - 您要重新輸入金鑰之資料集的資料集ID。
   - 所需資料集的永久ID欄名稱（身分路徑和名稱空間） （每列顯示的識別碼）。
   - 如果資料集支援`identityMap`：
      - 對於欄位式拼接，請指定持續和人員ID的名稱空間。
      - 對於圖表式拚接，請指定永久ID的名稱空間以及用於查詢身分圖表的身分名稱空間。
   - 如果資料集不支援`identityMap`：
      - 對於依欄位彙整，所需資料集的人員ID欄名稱（人員ID，也會做為連線內容中資料集之間的連結）。
      - 對於圖表式拼接，是指您要用於查詢身分圖表的身分名稱空間。
   - 您的回顧視窗和重播頻率偏好設定。 檢視您的Customer Journey Analytics套件，以取得可用的[選項](#options)。
   - 沙箱名稱。


2. Adobe客戶支援與Adobe工程部門合作，以便在收到您的請求時啟用拼接。 啟用後，Adobe Experience Platform中會出現一個包含拼接ID欄的已重設金鑰資料集。 Adobe客戶支援可提供新資料集的ID。
3. 首次開啟時，Adobe會提供拼接資料的回填。 檢視您的Customer Journey Analytics套件，以取得可用的[選項](#options)。

4. 如果您想要在跨管道分析中使用拼接資料集，您需要將拼接資料集新增到Customer Journey Analytics中的[連線](../connections/overview.md)。 然後新增跨管道分析所需的任何其他資料集，並為每個資料集選取正確的人員ID。

5. 根據連線[建立資料檢視](/help/data-views/create-dataview.md)。

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

設定資料檢視後，您可以跨管道和裝置執行Customer Journey Analytics報表分析。

## 限制

- 將對來源事件資料集結構描述所做的任何變更也套用至新拼接的資料集結構描述。

- 如果您移除來源資料集，拼接的資料集將停止處理並被系統移除。

- 資料使用標籤不會自動傳播到拼接資料集結構描述。如果您已將資料使用標籤套用至來源資料集結構描述，則需要將這些資料使用標籤手動套用至拼接資料集結構描述。如需更多資訊，請參閱[在 Experience Platform 中管理資料使用標籤](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/data-governance/labels/overview)。
