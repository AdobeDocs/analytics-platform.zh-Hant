---
title: 衍生欄位指南
description: 瞭解在Customer Journey Analytics中使用衍生欄位的准則，包括最佳實務、護欄和最佳化效能和資料正確性的常見陷阱。
solution: Customer Journey Analytics
feature: Derived Fields
exl-id: bcd172b2-cd13-421a-92c6-e8c53fa95936
role: Admin
hide: true
source-git-commit: ee6eb18fc2a720e61670c571847bacf836b0b039
workflow-type: tm+mt
source-wordcount: '2741'
ht-degree: 1%

---


# 衍生欄位准則

Customer Journey Analytics [衍生欄位](./derived-fields.md)可讓您在查詢時轉換、分類及擴充資料，而不需修改來源資料集。 如果沒有紀律性的規範，這種靈活性可能會帶來複雜性、效能問題和維護開銷。

本文提供使用衍生欄位的准則（最佳做法、護欄和常見陷阱）。 目標對象是資料架構師、產品管理員和分析師，他們需要：

* **最佳化效能**：找出拖慢查詢執行速度或達到系統限制的模式，為工作選取正確的工具：

   * [衍生欄位](./derived-fields.md)
   * [資料檢視設定](/help/data-views/component-settings/overview.md)
   * [資料準備](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/data-prep/home)
   * [計算量度](/help/components/calc-metrics/calc-metr-overview.md)
   * [查詢資料集](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)

* **改善可維護性**：建置清晰、模組化且容易更新的衍生欄位邏輯。
* **確保正確性**：避免分類、歸因和資料轉換中常見的邏輯錯誤。

本文章各節按主題組織。 從過於複雜的規則鏈結，到誤用[Lookup](./derived-fields.md#lookup)、[Regex Replace](./derived-fields.md#regex-replace)和[Next或Previous](./derived-fields.md#next-or-previous)等函式。 每個區段包含：

* 要偵測的&#x200B;**模式**：衍生欄位定義中的可觀察訊號。
* **風險診斷**：為什麼模式有問題。 可能的原因為&#x200B;**效能**、**資料品質**&#x200B;或&#x200B;**維護**&#x200B;的負面影響。
* **建議**：重構或改善實作的具體步驟。

這些准則可協助您在Customer Journey Analytics中建立有效率、可擴充且語義正確的實作。 稽核現有的資料檢視、設計新的衍生欄位或建立治理工具時，請套用這些准則。


## 高基數衍生欄位

本節將討論參考高基數衍生欄位的資料檢視預設區段。

### 模式

* 參照建置在高基數維度上的衍生欄位（大約一百萬或多個不同值）的資料檢視預設區段。 例如：完整頁面URL。
* 簡單操作，例如[小寫](./derived-fields.md#lowercase)、[Trim](./derived-fields.md#trim)或[Case When](./derived-fields.md#case-when)檢查頁面URL通常比檢查低基數欄位（例如頁面名稱、網站區段或URL群組）的相同邏輯更昂貴。

### 風險診斷：效能

* 在接觸頁面URL或其他高基數維度的衍生欄位上篩選的預設區段，會為針對資料檢視的每個查詢新增延遲。

### 推薦

* 避免直接在資料檢視預設區段中參考完整頁面URL或類似的高基數元件。 將大量URL邏輯（複雜的[大小寫條件](./derived-fields.md#case-when)，[Regex取代](./derived-fields.md#regex-replace)，多個字串函式）向上推播至[資料準備](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/data-prep/home)或[查詢資料集](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)，因此產生的分類會以較簡單、較低基數維度為基礎。
* 偏好較低基數索引鍵，例如標準化頁面名稱、網站區段或預先分類的URL群組。
* 定期稽核現有資料檢視預設區段和衍生欄位，以參考高基數維度（頁面URL、促銷活動ID、原始查詢字串），並重構為標準化或分組的索引鍵。

## 規則鏈結時過度複雜的大小寫

本節討論[Case When](./derived-fields.md#case-when)規則的過於複雜鏈結。

Customer Journey Analytics會針對每個衍生欄位強制執行明確的[函式與運運算元限制](derived-fields.md#limitations) （例如，運運算元數目上限、每種型別的函式數目上限）。 過於複雜的函式以及函式中的鏈結更難維護，也更容易出錯。

### 模式

* 具有複雜[If](./derived-fields.md#case-when)和&#x200B;**[!UICONTROL Else If]**&#x200B;鏈結的&#x200B;**[!UICONTROL 函式時非常大的]**&#x200B;案例：
   * 許多條件（例如：超過20個運運算元）或深層巢狀（超過3或4層巢狀[Case When](./derived-fields.md#case-when) **[!UICONTROL If]**&#x200B;和&#x200B;**[!UICONTROL Else If]**&#x200B;邏輯）。
   * 相同欄位上具有不同值的重複條件。
* 重複的常數字串比對。

  +++ 範例

  ![最佳實務 — 重複的常數字串比對範例](assets/best-practices-over-complex-case-when.png)

  +++


### 風險診斷：效能、資料品質、高度維護

* 可維護性和錯誤風險：邏輯編碼為單一規則區塊時，很難除錯和更新。
* 潛在效能和限制風險：您可能會點選或接近[運運算元或函式限制](./derived-fields.md#limitations)，尤其是使用類似分類的模式。

### 推薦

* 分割成多個衍生欄位。 例如，將&#x200B;*行銷活動標準化* （將不一致的行銷活動識別碼對應到標準值）與管道分組分開，而不是在一個巨大規則中組合所有內容。
* 使用查詢資料集。 許多&#x200B;**[!UICONTROL 如果值&#x200B;_值_條件&#x200B;_條件_然後將&#x200B;_值_設定為值]**&#x200B;條件較適合實作為[查詢資料集](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)結合[查詢](./derived-fields.md#lookup)函式，而非使用長[Case When](./derived-fields.md#case-when)鏈結。
* 使用資料檢視元件篩選器。 如果邏輯的一部分只是篩選掉錯誤值，請在資料檢視元件層級使用[包含排除](/help/data-views/component-settings/include-exclude-values.md)，而不是將該邏輯內嵌在衍生欄位中。

## 使用錯誤

本節討論衍生欄位的錯誤使用。 尤其是當替代方案是更好的解決方案時。

>[!NOTE]
>
>將邏輯從衍生欄位移至資料檢視元件設定本身無法改善查詢效能。 兩種方法編譯成相同的基礎衍生邏輯。 本節中的建議包括清晰度、治理和重複使用，而不是速度。

### 模式

* 衍生欄位會複製元件設定中已有的行為：
   * 大小寫標準化、微調或簡單篩選（例如：排除`unknown`、`undefined`或`null`），沒有額外的複雜性。
   * 數字範圍的基本分組。

     +++ 範例

     ![基本分組使用錯誤](assets/best-practices-wrong-usage.png)

     +++

     請改為在資料檢視的維度上使用[值分組](/help/data-views/component-settings/value-bucketing.md)。
   * 以[下一個或上一個](./derived-fields.md#next-or-previous)編碼的持續性或歸因邏輯，或資料檢視[歸因](/help/data-views/component-settings/attribution.md)和[有效期](/help/data-views/component-settings/persistence.md)設定就夠的手動順序邏輯。
   * 一種衍生量度，只會計算某個條件下的現有量度。

     +++ 範例

     ![條件式邏輯使用錯誤](assets/best-practices-wrong-usage-2.png)

     +++

     這會復寫篩選量度或[包含排除值](/help/data-views/component-settings/include-exclude-values.md)所能達到的程度。

### 風險診斷：資料品質、高度維護

* 備援複雜性：衍生欄位用於存在更簡單內建資料檢視功能的地方。
* 治理風險：其他使用者可能不知道為什麼衍生欄位存在而非原生設定。 此模式會增加衍生欄位管理中的混亂。
* 降低重複使用性：將條件式標幟編碼為衍生欄位使得跨專案使用不同篩選器的基本量度更難重複使用。

### 推薦

* 修剪/小寫：除非您需要合併多步驟轉換，否則請使用[Substring](/help/data-views/component-settings/substring.md)和[Behavior](/help/data-views/component-settings/behavior.md)元件設定。
* 值排除：在資料檢視元件層級，而不是在衍生欄位中，對量度或維度值使用[包含排除值](/help/data-views/component-settings/include-exclude-values.md)。
* 歸因和持續性：使用維度資料檢視[持續性](/help/data-views/component-settings/persistence.md)設定（**[!UICONTROL 配置模式]**&#x200B;和&#x200B;**[!UICONTROL 有效期]**），而不是在具有[下一個或上一個](./derived-fields.md#next-or-previous)或其他循序邏輯的衍生欄位中模擬它們。
* 數值分組：保持衍生欄位為數值，並讓資料檢視在頂端建立分組維度，而不是在[Case When](./derived-fields.md#case-when)鏈中硬式編碼範圍標籤。
* 條件式邏輯：將簡單的0或1標幟邏輯轉換為：
   * 原始量度包含或排除套用於Analysis Workspace的值篩選邏輯。
   * 使用資料檢視元件設定組態的篩選量度。

## 量度和維度的分類錯誤

本節將討論量度和維度的分類錯誤。

### 模式

* 衍生欄位會清楚地產生：
   * 數值輸出（計數、比率或算術），但元件已設定為維度。
   * 類別輸出（標籤或字串），但元件已設定為量度。
* 衍生欄位會將0/1標幟編碼為字串。

Customer Journey Analytics允許在資料檢視層級將數值欄位強製為維度，並將字串欄位強製為量度，但若未妥善對齊，可能會產生令人困惑的報表。

### 風險診斷：資料品質

* 語意不符：元件型別不符合衍生結果的性質，導致元件型別更難以正確分析或彙總。

### 推薦

* 如果輸出是數字：
   * 在資料檢視中將元件型別設定為&#x200B;**[!UICONTROL 量度]**。
   * 如果元件代表子集量度（例如，**[!UICONTROL 結帳頁面檢視次數]**），請在資料檢視中使用篩選量度，而不是使用衍生字串加上位於頂端的計算量度。
* 如果輸出是標籤：
   * 將元件型別設定為&#x200B;**[!UICONTROL Dimension]**，並相應地設定[持續性](/help/data-views/component-settings/persistence.md)設定（**[!UICONTROL 配置模式]**&#x200B;和&#x200B;**[!UICONTROL 有效期]**）。

## 行銷管道和行銷活動邏輯陷阱

本節將討論行銷管道和行銷活動邏輯陷阱。

>[!NOTE]
>
>考慮上游簡化：使用[資料準備](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/data-prep/home)、[查詢資料集](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)或衍生欄位函式（如[分類](./derived-fields.md#classify)）來合併類似的行銷管道規則，並減少[Case When](./derived-fields.md#case-when)邏輯中的運運算元數量。 此外，限制頻道分類邏輯中參考的高基數欄位數量（例如：許多不同的查詢引數索引鍵），因為這些欄位會增加基數和查詢成本。

### 模式

* Customer Journey Analytics行銷管道通常使用衍生欄位實作。

   * 根據URL引數、反向連結、登陸頁面等實作行銷管道或行銷活動分段的衍生欄位。
   * 可疑排序：在套用更具體的規則之前，會出現一個通用的catch-all規則。
   * 所有可能的選項的處理不完整： **[!UICONTROL 反向連結網域沒有明確的分支]**&#x200B;或未設定&#x200B;**[!UICONTROL 查詢引數]**。

### 風險診斷：資料品質

* 邏輯排序錯誤：鏈結中的後續規則可能會覆寫特定通道，並導致分類錯誤的流量。
* 直接流量錯誤標籤：不符的流量落入非預期的管道或標籤為`Other`。

### 推薦

* 強制執行由上而下的優先順序排序。 將最強的訊號放在最前（例如：要排除付費行銷活動引數的內部網域）。
* 包含最終明確&#x200B;**[!UICONTROL 否則將值設定為]**&#x200B;大小寫。 將遞補設定為&#x200B;**[!UICONTROL 沒有值]**&#x200B;以避免覆寫先前的通道。 請勿在此全包步驟中將值設為&#x200B;**[!UICONTROL 自訂字串值]**，然後將&#x200B;**[!UICONTROL 自訂字串值]**&#x200B;設為`Direct`、`None`或`Unclassified`。
* 使用範本。 儘可能利用行銷管道衍生欄位範本。 或者至少讓邏輯符合Adobe建議的行銷管道最佳實務。

## 用於查閱的非標準化字串索引鍵

本節討論在查閱中使用非標準化字串索引鍵的問題。

### 模式

* 事件或設定檔欄位上的[查詢](./derived-fields.md#lookup)函式，可饋送查詢資料集。
* 沒有前面的[小寫](./derived-fields.md#lowercase)、[Trim](./derived-fields.md#trim)或[Regex Replace](./derived-fields.md#regex-replace)將金鑰標準化。
* 常見候選人：URL、促銷活動ID、電子郵件、帳戶ID。

### 風險診斷：資料品質、高度維護

* 資料品質風險：主要大小寫或空白字元與查詢表格不同時，查詢會失敗，導致&#x200B;*沒有相符專案*&#x200B;值，且報表出現間隙。

### 推薦

* 在[Lookup](./derived-fields.md#lowercase)函式之前新增[小寫](./derived-fields.md#trim)和[Trim](./derived-fields.md#lookup)函式，除非有檔案說明保留大寫或小寫的原因。
* 如果已經連結多個轉換，請驗證其順序：先標準化，然後查詢。

## Regex濫用或伸手過長

本節將討論衍生欄位規則運算式功能的濫用或過度延伸。

### 模式

* [Regex Replace](./derived-fields.md#regex-replace)或regex-based條件會使用非常廣泛的模式，其中較簡單的[Case When](./derived-fields.md#case-when)函式包含&#x200B;**[!UICONTROL Contains]**&#x200B;或&#x200B;**[!UICONTROL Starts with]**&#x200B;是較簡單且較好的替代方案。

  +++ 範例

  ![最佳實務 — Regex取代1](assets/best-practices-regex-replace-1.png)

  ![最佳實務 — Regex取代1](assets/best-practices-regex-replace-2.png)

  +++

* 多個規則運算式條件重疊或衝突。
* 大量使用規則運算式來剖析URL，而非使用[URL Parse](./derived-fields.md#url-parse)函式。

### 風險診斷：效能、資料品質、高度維護

* 效能和可維護性風險：複雜的規則運算式模式較難偵錯，而且速度可能較慢。
* 正確性風險：過於寬泛的規則運算式可能會擷取意外的值。

### 推薦

* 偏好使用標準URL元素（網域、路徑、查詢引數）的[URL剖析](./derived-fields.md#url-parse)，而非[Regex取代](./derived-fields.md#regex-replace)。
* 對於簡單模式檢查，請使用[Case When](./derived-fields.md#case-when)搭配&#x200B;**[!UICONTROL Contains]**、**[!UICONTROL Starts with]**&#x200B;或&#x200B;**[!UICONTROL Ends with]**&#x200B;邏輯，而不是搭配[Regex Replace](./derived-fields.md#regex-replace)的規則運算式。
* 標幟使用多個巢狀群組或簡單模式替代的規則運算式。 或是您可以使用衍生欄位字串函式來取代的規則運算式。

## 衍生欄位中的計算量度樣式邏輯

本節將討論在衍生欄位中使用計算樣式邏輯的問題。

>[!NOTE]
>
>衍生欄位會在彙總前的事件（列）層級進行評估，而Analysis Workspace計算量度則會對已彙總的值運作。 因此，視這些計算是作為衍生欄位還是作為計算量度實施，比率、平均值和不同樣式的計算可能會產生不同的結果。 請謹慎考慮算術所在的位置，因為評估的粒度會變更答案。

### 模式

* 在看起來像是計算量度的衍生欄位（和、減、除）內，對數值欄位執行純算術。

  +++ 範例

  ![最佳實務 — 利潤計算](assets/best-practices-profit.png)

  ![最佳實務 — 每次曝光訂購](assets/best-practices-orders-impressions.png)。

  +++

* 不使用字串操控或分類；邏輯是純數值。

### 風險診斷：資料品質

* 治理和設計問題：算術可能更適合：
   * 衍生欄位量度（如果您希望衍生欄位作為所有使用者的控管標準量度）。
   * Analysis Workspace中的計算量度（如果計算量度是分析專用的）。

### 推薦

* 如果算術結果通常對使用者和專案都很有用，請將結果保留為衍生欄位量度。 確認元件型別為量度，並在資料檢視層級設定格式（貨幣、百分比）。
* 如果結果為細分或分析人員專屬，請將結果移至計算量度並簡化資料檢視。

## 超量使用下一個或上一個或循序函式

本節討論[下一個或上一個](./derived-fields.md#next-or-previous)或循序函式的過度使用。

### 模式

* 衍生欄位多次使用[Next或Previous](./derived-fields.md#next-or-previous)函式（接近記錄的每個欄位限制）。
* [下一個或上一個](./derived-fields.md#next-or-previous)用於實作持續性類似的邏輯（例如：繼續促銷活動），而不是使用資料檢視持續性。

### 風險診斷：資料品質、高度維護

* 複雜性與脆弱性：沈重的循序邏輯較難解釋，並且可能在工作階段化規則或順序變更時中斷。
* 維度持續性的備援：某些使用案例（例如工作階段上的上次接觸管道）較適合包含在維度上的資料檢視[持續性](/help/data-views/component-settings/persistence.md)設定（**[!UICONTROL 配置模式]**）中。

### 推薦

* 對於類似標準持續性的模式（例如，跨工作階段或人員向前傳送值），請在資料檢視中使用維度的[持續性](/help/data-views/component-settings/persistence.md)設定（**[!UICONTROL 配置模式]**&#x200B;和&#x200B;**[!UICONTROL 有效期]**），而不是使用[下一個或上一個](./derived-fields.md#next-or-previous)模擬這些模式。
* 保留[下一個或上一個](./derived-fields.md#next-or-previous)，用於無法單獨實現維度持續性的進階多步驟路徑或funnel標籤（例如：管道序列串連）。

## 忽略工作階段和個人層級內容

本節討論定義衍生欄位時，忽略工作階段和個人層級內容。

>[!NOTE]
>
>在某些情況下，在Analysis Workspace中在工作階段或人員層級設定範圍的區段，其行為模型的建立可能比衍生欄位更簡單。 適當時，請考慮使用區段，而非複雜的跨範圍衍生欄位。

### 模式

* 衍生欄位隱含假設特定[容器層級](/help/getting-started/cja-b2b-concepts-features.md#containers) （事件、工作階段或人員），但：

   * 衍生欄位不會參考工作階段或人員層級屬性。
   * 資料檢視工作階段設定與預期邏輯衝突。

### 風險診斷：資料品質

* 概念不符：衍生欄位語意可能不符合分析人員預期的彙總層級（例如：可隨每個事件變更的角色型欄位）。

### 推薦

* 如果邏輯是工作階段層級：確認[工作階段設定](/help/data-views/session-settings.md)已正確設定，並考慮在Analysis Workspace或[整合式BI工具](/help/data-views/bi-extension.md)中使用工作階段範圍的元件或摘要。
* 如果邏輯旨在提供人員層級：使用設定檔資料集或查詢資料集，並在衍生欄位中參考這些資料集。
* 評估Analysis Workspace中工作階段範圍或人員範圍的區段會比衍生欄位更簡單地取得相同的結果。

## 達到或接近記錄函式限制

本節探討達到或接近記錄的衍生欄位函式限制的影響。

>[!NOTE]
>
>儘可能減少對複雜衍生欄位中高基數欄位的依賴（例如：使用標準化索引鍵或群組分類），以限制查詢成本以及達到[運運算元或函式限制](./derived-fields.md#limitations)的可能性。

Customer Journey Analytics [檔案](./derived-fields.md#limitations)每個衍生欄位的最大函式和運運算元，包括每個函式型別的限制（[Lookup](./derived-fields.md#lookup)、[Date Math](./derived-fields.md#date-math)、[Deduplicate](./derived-fields.md#deduplicate)、[Math](./derived-fields.md#math)、[Split](./derived-fields.md#split)、[URL Parse](./derived-fields.md#url-parse)等等）。

### 模式

* 衍生欄位使用許多[查詢](./derived-fields.md#lookup)、[Math](./derived-fields.md#math)作業、[分割](./derived-fields.md#split)或其他函式。
* 運運算元數目接近[記錄的限制](./derived-fields.md#limitations) （例如：超過70% - 80%的允許計數）。

### 風險診斷：效能、高度維護

* 可擴充性風險：如果欄位達到其功能限制，未來的新增可能會失敗或出現意外行為。

### 推薦

* 當使用量超過臨界值時（例如：超過任何函式或運運算元限制的70%），主動標幟。
* 將邏輯分割成鏈結在一起的多個衍生欄位(例如：衍生欄位A （標準化查閱索引鍵），以及衍生欄位Band normalize_key then lookup_label)。
* 在需要特別大型分類的情況下，使用外部資料準備或查詢資料集。

## 資料檢視專用最佳化規則

本節將討論衍生欄位的資料檢視特定最佳化規則。

同時檢查每個衍生元件的資料檢視組態。

### 模式

* 衍生維度具有預設歸因（例如：上次接觸與工作階段到期），但衍生欄位名稱表示不同的語意（例如： `First Campaign of Visit`， `Original Source`）。
* 衍生維度具有預設[持續性](/help/data-views/component-settings/persistence.md)設定（例如： **[!UICONTROL 最近]**&#x200B;配置，含&#x200B;**[!UICONTROL 工作階段]**&#x200B;有效期），但衍生維度的名稱表示不同的語意（例如`First Campaign of Visit`或`Original Source`）。


### 風險診斷：資料品質

* 語意不符：維度的標籤會建議與實際設定不同的配置或到期行為（例如，原始配置或人員層級到期日）。
* 這種不相符會增加分析人員誤解報表或比較依名稱出現類似但使用不同配置模型的元件的風險。

### 推薦

* 調整該維度上的[配置模型和有效期](/help/data-views/component-settings/persistence.md)，以對齊名稱和行為。 例如，名為`Original Source`的衍生欄位維度應使用到期日設為「人員」的「首次接觸」歸因。
* 調整維度的&#x200B;**[!UICONTROL 持續性]**&#x200B;設定中的&#x200B;**[!UICONTROL 配置模式]**&#x200B;和[有效期](/help/data-views/component-settings/persistence.md)，以對齊名稱和行為。 例如，`Original Source`應該將&#x200B;**[!UICONTROL 配置模式]**&#x200B;設定為&#x200B;**[!UICONTROL 原始]**，並將&#x200B;**[!UICONTROL 到期]**&#x200B;設定為&#x200B;**[!UICONTROL 人員]**。
