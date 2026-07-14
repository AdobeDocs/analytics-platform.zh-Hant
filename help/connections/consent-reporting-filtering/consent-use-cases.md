---
title: 同意報表和篩選使用案例
description: 探索在Customer Journey Analytics中報告訪客同意原則會籍和篩選擷取時間非同意訪客的使用案例。
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2: id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: eafeab50e86b3e98f372c70a0fd43494015ca002
workflow-type: tm+mt
source-wordcount: 585
ht-degree: 0%

---

# 同意報告和篩選使用案例

同意報表和篩選可協助您報告訪客同意原則成員資格，並可選擇在資料進入Customer Journey Analytics之前排除非同意的訪客。 如需概述資訊，請參閱[同意報告和篩選概述](/help/connections/consent-reporting-filtering/consent-overview.md)。

本文會說明範例使用案例。 檢閱前，請熟悉下列考量事項，因為這些事項會影響您在報表中看到的結果。

## 報表考量事項

* **篩選套用至連線層級**：當您啟用篩選時，設定之連線下的所有資料檢視都會繼承相同的行為。 您無法在一個連線下以不同方式篩選一個資料檢視。

* **篩選使用包含邏輯**：只有在訪客符合所有適用於已啟用行銷動作的同意原則時，才會擷取訪客的資料。 系統會排除缺少任何適用原則的訪客。

* **排除的資料無法復原**：因為篩選會在擷取時進行，所以排除的資料不會儲存在Customer Journey Analytics中。 稍後變更您的設定並不會復原過去日期的已排除資料。

* **同意原則會籍來自設定檔資料集**：報告反映設定檔資料集的`consentPoliciesIDMap`欄位中存在的同意原則會籍。 訪客的連線中必須有對應的事件，才能顯示在報表中。

## 範例使用案例

### 使用案例1：報告同意但不篩選資料

瞭解符合每個同意原則的訪客數量，然後再決定是否篩選，以回答下列問題：

* _「有多少訪客同意使用Analytics？」_
* _「哪些同意原則對訪客的涵蓋範圍最大且最少？」_

**設定流程：**

1. 建立設定並選取包含同意原則成員資格資料的沙箱、設定檔資料集和連線。

1. 讓&#x200B;**[!UICONTROL Analytics]**&#x200B;和&#x200B;**[!UICONTROL 資料科學]**&#x200B;篩選功能保持關閉。

1. 在Analysis Workspace中，使用&#x200B;**[!UICONTROL 原則名稱]**&#x200B;維度和&#x200B;**[!UICONTROL 具有同意的訪客]**&#x200B;量度來建立自由表格，以檢視每個原則的涵蓋範圍。

使用這些見解來決定是否啟用篩選以及針對哪些行銷動作。

### 使用案例2：從Analytics報表中排除非同意的訪客

請確認標準報表僅包含同意使用Analytics的訪客，以回答下列問題：

* _「我們的對象只報告同意的訪客時會有何行為？」_
* _「我們可以確定未獲得同意的訪客資料從未進入我們的分析報表嗎？」_

**設定流程：**

1. 建立或編輯連線的設定，以支援分析報告。

1. 啟用&#x200B;**[!UICONTROL Analytics]**&#x200B;篩選切換。

1. 確認設定。 此後，Customer Journey Analytics只有在訪客符合套用至Analytics行銷動作的所有同意原則時，才會擷取訪客的資料。

由於篩選會在擷取時進行，因此下游報表、匯出和API只會自動反映同意的訪客，不需要變更報表時間。

### 使用案例3：分別篩選分析和資料科學使用案例

將不同的同意要求套用至標準報告和資料科學使用案例，以回答下列問題：

* _「我們可以在Analytics中包含更廣的訪客集，同時對機器學習套用更嚴格的同意嗎？」_

**設定流程：**

1. 建立或編輯相關連線的設定。

1. 根據每個使用案例的同意要求，啟用&#x200B;**[!UICONTROL Analytics]**&#x200B;切換、**[!UICONTROL 資料科學]**&#x200B;切換，或兩者同時啟用。

1. 確認設定。 Customer Journey Analytics會獨立評估適用於每個已啟用行銷動作的同意政策。

當您的組織針對不同的資料使用類別套用不同的同意要求時，請使用此方法。
