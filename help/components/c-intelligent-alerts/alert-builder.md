---
description: 瞭解如何在Analysis Workspace中建立警報。
title: 建立警報
feature: Workspace Basics
role: User, Admin
exl-id: 5b4b2e2b-0a73-48df-a40c-98d2c47f94c8
source-git-commit: 0e9dc47b80db142801a94dcbf31470d99a610949
workflow-type: tm+mt
source-wordcount: '967'
ht-degree: 68%

---

# 建立警報 {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="時間詳細程度"
>abstract="時間詳細程度是指系統檢查警報的頻率。"

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>僅擁有 Customer Journey Analytics Prime 或 Ultimate 套件的組織才能使用具有異常偵測的警報 (也稱為&#x200B;_智慧型警報_)。

Customer Journey Analytics 中的警報可讓您根據變更的百分比或特定資料點來接收通知。根據您的 Customer Journey Analytics 套件，您還可以使用根據異常臨界值觸發的警報。

如需有關警示的詳細資訊，請參閱[警示概述](/help/components/c-intelligent-alerts/intelligent-alerts.md)。

若要建立警報：

<!-- Note that there are difference in how alerts are created in CJA vs AA. In AA you can create alerts from the Workspace menu and using a shortcut; these are not possible in CJA... -->

1. 在Customer Journey Analytics中，選取&#x200B;**[!UICONTROL 元件]** > **[!UICONTROL 警報]**。 在[警報管理器](alert-manager.md)中，選取 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 「新增」]**&#x200B;以建立新警報，或取所列的任何警報來修訂現有警報。

   [警報產生器](#alert-builder)介面會顯示。

1. 選取「**[!UICONTROL 儲存]**」以儲存警報。選取「**[!UICONTROL 另存新檔]**」以儲存警報的副本。


## 警報產生器

警報產生器的介面與您在Customer Journey Analytics中建立區段或計算量度時所用的介面類似：

![警報產生器介面](assets/alert-builder.png)

在警報產生器中為警報指定以下詳細資訊：

| 元素 | 說明 |
|---------|----------|
| **[!UICONTROL 標題]** | 指定警報的名稱。警報名稱中可以包含報表的名稱或量度臨界值。 |
| **[!UICONTROL 說明 (選用)]** | 指定警報的說明。 |
| **[!UICONTROL 時間詳細程度]** | 選取您希望檢查量度的頻率：每日、每週或每月。<p><b>注意</b>：對於具有[自訂行事曆](/help/data-views/create-dataview.md#calendar)的資料檢視，警報產生器不支援每月粒度。<!--true?--></p> |
| **[!UICONTROL 收件者]** | 指定可傳送警報的位置。警報可以傳送給 Analytics 用戶、Analytics 群組、原始電子郵件地址或電話號碼。<p><b>重要</b>：電話號碼前面必須加上`+`和[國家/地區代碼](https://countrycode.org/)。</p><p>使用者在警示後收到的電子郵件：</p><p>![警報電子郵件](assets/alerts-email.PNG)</p> |
| **[!UICONTROL 過期日]** | 設定警報過期的日期和時間。 |
| **[!UICONTROL 延遲]** | 資料完整並可在 Customer Journey Analytics 中報告以前所需的時間因組織而異，通常是資料事件時間過後的 3 到 9 小時。為了確保警報準確，特定事件範圍的事件資料必須完整，這表示 Adob&#x200B;&#x200B;e 不再接收指定事件範圍的任何事件資料。<p>為了解決攝取時間的延遲，警報發送前的預設延遲時間為 9 小時。</p><p>您可以將預設延遲時間從 9 小時調整為 0 至 24 小時之間的任意值。但是，將延遲時間減少到 9 小時以下可能表示您報告的資料不完整，這會導致警報資訊不準確。</p><p>減少延遲時間時，請考慮以下事項：</p><ul><li>**瞭解資料可用性與資料完整性**：批次資料只會在3到9個小時後擷取到Experience Platform資料集中。 為了確保警報準確，資料攝取必須完整，並且所有大量資料在資料集中都可供使用。</li><li>**確定資料需要多長時間才會完整並可在資料集中供使用**：資料攝取時間因組織而異。您必須確保為警報傳遞選擇的延遲時間與大量資料在 Platform 資料集中可供使用所需的時間相同或更短<!--add link? -->。</li><p>**秘訣：**&#x200B;要瞭解完成所有批次資料並將其擷取到Experience Platform資料集所需的時間，最準確的方式是諮詢貴組織的資料工程師。</p><p>或者，您也可以大致瞭解組織中的批次傳送需要多久才能在Platform資料集中使用。 在Analysis Workspace中建立下列自由表格：</p><ol><li>在 Analysis Workspace 中的自由格式表格中，新增一個「[!UICONTROL **事件**]」量度和一個「[!UICONTROL **天**]」維度。</li><li>使用「[!UICONTROL **小時**]」維度來劃分「[!UICONTROL **天**]」維度。<p>沒有資料的時數顯示為0。</p></li></ol><li>**計算錯誤的原因**：如果您減少預設的延遲時間，請將延遲時間設定為至少比貴組織完成資料擷取所花的時間長一小時。 例如，如果得到完整資料攝取之前有 3 小時的延遲，那麼您應該將延遲設為 4 小時。</li></ul><p>若要了解更多資訊，請參閱文章「[警報功能比較：Customer Journey Analytics 和 Adob&#x200B;&#x200B;e Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)」中的「[Customer Journey Analytics 中的資料攝取時間有所不同](/help/components/c-intelligent-alerts/alerts-feature-comparison.md#data-ingestion-times-vary-in-customer-journey-analytics)」。 |
| **[!UICONTROL 傳送警報的時機]** | [!UICONTROL **這些量度中的任何一個均會觸發**]：將量度 (包括計算量度) 拖放至此處，以建立警報觸發程式。<p>如果並非所有警報中的量度、維度或區段均與目前選取資料檢視相容，系統會顯示&#x200B;**「不相容的元件」**&#x200B;訊息。</p><p>確定觸發警報前必須超過的量度臨界值。您可以將此值設為臨界值以及下列其中一個條件：</p><ul><li>存在異常</li><li>異常超出預期</li><li>異常低於預期</li><li>高於或等於</li><li>低於或等於</li><li>變更者</li><li>您可以設定 90%、95%、99%、99.75% 或 99.9% 的臨界值。</li></ul><p>[!UICONTROL **包含所有這些篩選器**]：拖放區段或維度以將篩選器新增至警報。 例如，新增&#x200B;*僅限行動裝置*&#x200B;區段可能表示規則僅會針對行動裝置觸發。 您可以透過使用 AND 陳述式新增其他篩選器。您可按一下齒輪圖示，新增 AND 或 OR 規則。</p><p>檢視[警示 — 使用案例](/help/components/c-intelligent-alerts/alerts-use-cases.md)使用案例。</p> |
| **[!UICONTROL 預覽]** | 互動式警報預覽會根據先前的體驗，向您顯示警報觸發的頻率（近似值）。<p>例如，如果您將時間詳細程度設為每日，則預覽可告訴您在過去 30 或 31 天裡，針對某個量度觸發了 x 次警報。</p><p>如果您發現觸發的警示過多，可以在[管理警示](/help/components/c-intelligent-alerts/alert-manager.md)中調整臨界值。</p><p>![](assets/alert-preview.png){width="50%"}</p> |
