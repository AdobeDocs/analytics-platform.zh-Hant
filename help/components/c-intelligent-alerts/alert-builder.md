---
description: 瞭解如何在Analysis Workspace中建立警報。
title: 建立警報
feature: Workspace Basics
role: User, Admin
exl-id: 5b4b2e2b-0a73-48df-a40c-98d2c47f94c8
source-git-commit: 65e46a5d2a6759dd83b24bba2d1d4ee283b907c9
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 69%

---

# 建立警報 {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="時間顆粒度"
>abstract="時間顆粒度是指系統檢查警報的頻率。"

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>僅擁有 Customer Journey Analytics Prime 或 Ultimate 套件的組織才能使用具有異常偵測的警報 (也稱為&#x200B;_智慧型警報_)。

Customer Journey Analytics 中的警報可讓您根據變更的百分比或特定資料點來接收通知。根據您的 Customer Journey Analytics 套件，您還可以使用根據異常臨界值觸發的警報。

有關警報的更多詳細資訊，請參閱[警報概觀](/help/components/c-intelligent-alerts/intelligent-alerts.md)。

若要建立警報：

<!-- Note that there are difference in how alerts are created in CJA vs AA. In AA you can create alerts from the Workspace menu and using a shortcut; these are not possible in CJA... -->

1. 在Customer Journey Analytics中，選取&#x200B;**[!UICONTROL 元件]** > **[!UICONTROL 警報]**。 在[警報管理器](alert-manager.md)中，選取 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 「新增」]**&#x200B;以建立新警報，或取所列的任何警報來修訂現有警報。

1. 在Analysis Workspace中，在自由表格中選取一或多個行專案，從內容功能表選取&#x200B;**[!UICONTROL 從選取範圍建立警報]**。 此動作會立即預先填入警報產生器，使用正確的量度和區段建立警報。

[警報產生器](#alert-builder)介面會顯示。


## 警報產生器

警報產生器的介面與您在Customer Journey Analytics中建立區段或計算量度時所用的介面類似：

![警報產生器介面](assets/alert-builder.png)

在警報產生器中為警報指定以下詳細資訊：

| 元素 | 說明 |
|---------|----------|
| **[!UICONTROL 標題]** | 指定警示的名稱。 警報名稱中可以包含報表的名稱或量度臨界值。 |
| **[!UICONTROL 說明 (選用)]** | 指定警報的說明。 |
| **[!UICONTROL 時間顆粒度]** | 選取您希望檢查量度的頻率：每日、每週或每月。<p><b>注意</b>：對於具有[自訂行事曆](/help/data-views/create-dataview.md#calendar)的資料檢視，警報產生器不支援每月粒度。<!--true?--></p> |
| **[!UICONTROL 收件者]** | 指定可傳送警報的位置。警報可以傳送給 Analytics 用戶、Analytics 群組、原始電子郵件地址或電話號碼。<p><b>重要提示</b>：電話號碼前面必須加上 `+` 和[國家/地區代碼](https://countrycode.org/)。</p><p>使用者在警示後收到的電子郵件：</p><p>![警報電子郵件](assets/alerts-email.PNG)</p> |
| **[!UICONTROL 過期日]** | 設定警報過期的日期和時間。 |
| **[!UICONTROL 延遲]** | 資料完整並可在 Customer Journey Analytics 中報告以前所需的時間因組織而異，通常是資料事件時間過後的 3 到 9 小時。為了確保警報準確，特定事件範圍的事件資料必須完整，這表示 Adob&#x200B;&#x200B;e 不再接收指定事件範圍的任何事件資料。<p>為了解決攝取時間的延遲，警報發送前的預設延遲時間為 9 小時。</p><p>您可以將預設延遲時間從 9 小時調整為 0 至 24 小時之間的任意值。但是，將延遲時間減少到 9 小時以下可能表示您報告的資料不完整，這會導致警報資訊不準確。</p><p>減少延遲時間時，請考慮以下事項：</p><ul><li>**瞭解資料可用性與資料完整性**：批次資料只會在3到9個小時後擷取到Experience Platform資料集中。 為了確保警報準確，資料攝取必須完整，並且所有批次資料在資料集中都可供使用。</li><li>**確定資料需要多長時間才會完整並可在資料集中供使用**：資料攝取時間因組織而異。請確認所選的警報傳遞延遲時間等同或短於批次資料在 Platform 資料集中可供使用所需的時間<!--add link? -->。</li><p>**秘訣：**&#x200B;要瞭解完成所有批次資料並將其擷取到Experience Platform資料集所需的時間，最準確的方式是諮詢貴組織的資料工程師。</p><p>或者，您也可以大致瞭解組織中的批次傳送需要多久才能在Platform資料集中使用。 在Analysis Workspace中建立下列自由表格：</p><ol><li>在 Analysis Workspace 中的自由格式表格中，新增一個「[!UICONTROL **事件**]」量度和一個「[!UICONTROL **天**]」維度。</li><li>使用「[!UICONTROL **小時**]」維度來劃分「[!UICONTROL **天**]」維度。<p>沒有資料的小時會顯示為 0。</p></li></ol><li>**解決計算中的錯誤**：如果您減少預設延遲時間，此延遲時間必須設定為比您的組織完成資料擷取所需時間至少多一個小時。例如，如果資料擷取完成之前有 3 小時的延遲，那麼您應該將延遲設為 4 小時。</li></ul><p>若要了解更多資訊，請參閱文章「[警報功能比較：Customer Journey Analytics 和 Adob&#x200B;&#x200B;e Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)」中的「[Customer Journey Analytics 中的資料攝取時間有所不同](/help/components/c-intelligent-alerts/alerts-feature-comparison.md#data-ingestion-times-vary-in-customer-journey-analytics)」。 |
| **[!UICONTROL 傳送警報的時機]** | [!UICONTROL **這些量度觸發器的任一項**]： <ol><li>拖放量度（包括計算量度）以建立警報的觸發程式。<p>如果警報中並非所有量度、維度或區段都與目前所選報表套裝相容，則會出現&#x200B;*不相容的元件*&#x200B;訊息。</p><p>決定設定警報前，量度必須超過或使用的值（若為上、下、等於或百分比變更）的臨界值（適用於異常）。</li><li>選取下列條件之一：<ul><li>異常存在</li><li>異常高於預期</li><li>異常低於預期</li><li>高於或等於</li><li>低於或等於</li><li>變更者</li></ul></li><li>選取臨界值或輸入值。</li></ol>[!UICONTROL **包括所有篩選器**]：拖放區段或維度以新增篩選器至警報中。例如，新增「*僅限行動裝置*」區段代表只有行動裝置才會觸發這項規則。您可以透過使用 AND 陳述式新增其他篩選器。您可按一下齒輪圖示，新增 AND 或 OR 規則。</p><p>請參閱「[警報 - 使用案例](alerts-use-cases.md)」，了解用例範例。</p> |
| **[!UICONTROL 預覽]** | 互動式警報預覽會根據過去經驗，顯示觸發警報的大約頻率。<p>例如，如果您將時間顆粒度設為每日，則預覽將告訴您在過去 30 或 31 天裡，此警報會因為某個量度而被觸發 x 次。</p><p>如果您發現警報觸發次數過多，可在「[管理警報](/help/components/c-intelligent-alerts/alert-manager.md)」中調整臨界值。</p><p>![](assets/alert-preview.png){width="50%"}</p> |
