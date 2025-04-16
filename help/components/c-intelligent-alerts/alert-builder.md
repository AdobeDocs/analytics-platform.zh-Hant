---
description: 當專案元件達到特定臨界值時，收到警報。
title: 建立警報
feature: Workspace Basics
role: User, Admin
exl-id: 5b4b2e2b-0a73-48df-a40c-98d2c47f94c8
source-git-commit: 53069702055e0adf7abf9061c592fb15772ded73
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 95%

---

# 建立警報 {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="時間詳細程度"
>abstract="時間詳細程度指的是警報的檢查頻率以及包含的內容"

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>僅擁有 Customer Journey Analytics Prime 或 Ultimate 套件的組織才能使用具有異常偵測的警報 (也稱為&#x200B;_智慧型警報_)。

Customer Journey Analytics 中的警報可讓您根據變更的百分比或特定資料點來接收通知。根據您的 Customer Journey Analytics 套件，您還可以使用根據異常臨界值觸發的警報。

有關警報的更多詳細概觀資訊，請參閱[警報概述](/help/components/c-intelligent-alerts/intelligent-alerts.md)。

若要建立警報：

1. 在 Customer Journey Analytics<!-- add this back in after the other methods are available like in AA and make a bulleted list: "You can access the alert builder in any of the following ways:" --> 中，選取「**[!UICONTROL 元件]** > **[!UICONTROL 偏好設定]**」。在[警報管理器](alert-manager.md)中，選取 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 「新增」]**&#x200B;以建立新警報，或取所列的任何警報來修訂現有警報。

   [警報產生器](#alert-builder)介面會顯示。

1. 選取「**[!UICONTROL 儲存]**」以儲存警報。選取「**[!UICONTROL 另存新檔]**」以儲存警報的副本。


## 警報產生器

警報產生器的介面與在Customer Journey Analytics中建立區段或計算量度類似：

![](assets/alert-builder.png)

在警報產生器中為警報指定以下詳細資訊：

| 元素 | 說明 |
|---------|----------|
| **[!UICONTROL 標題]** | 指定警報的名稱。警報名稱中可以包含報表的名稱或量度臨界值。 |
| **[!UICONTROL 說明 (選用)]** | 指定警報的說明。 |
| **[!UICONTROL 時間詳細程度]** | 選取您希望檢查量度的頻率：每日、每週或每月。<p><b>註：</b>對於使用自訂行事曆的資料檢視，警報產生器不支援每月詳細程度。<!--true?--></p> |
| **[!UICONTROL 收件者]** | 指定可傳送警報的位置。警報可以傳送給 Analytics 用戶、Analytics 群組、原始電子郵件地址或電話號碼。<p><b>重要提示：</b> 電話號碼前面必須加上 &quot;+&quot; 號和[國家/地區代碼](https://countrycode.org/)。</p><p>觸發警報後，使用者收到的電子郵件類似以下內容：</p><p>![警報電子郵件](assets/alerts-email.PNG)</p> |
| **[!UICONTROL 過期日]** | 設定警報過期的日期和時間。 |
| **[!UICONTROL 延遲]** | 資料完整並可在 Customer Journey Analytics 中報告以前所需的時間因組織而異，通常是資料事件時間過後的 3 到 9 小時。為了確保警報準確，特定事件範圍的事件資料必須完整，這表示 Adob&#x200B;&#x200B;e 不再接收指定事件範圍的任何事件資料。<p>為了解決攝取時間的延遲，警報發送前的預設延遲時間為 9 小時。</p><p>您可以將預設延遲時間從 9 小時調整為 0 至 24 小時之間的任意值。但是，將延遲時間減少到 9 小時以下可能表示您報告的資料不完整，這會導致警報資訊不準確。</p><p>減少延遲時間時，請考慮以下事項：</p><ul><li>**了解資料可用性與資料完整性**：雖然有些資料可能更快可供報告，但所有大量資料都要經過 3 到 9 小時後才能被攝取至 Platform 資料集。為了確保警報準確，資料攝取必須完整，並且所有大量資料在資料集中都可供使用。</li><li>**確定資料需要多長時間才會完整並可在資料集中供使用**：資料攝取時間因組織而異。您必須確保為警報傳遞選擇的延遲時間與大量資料在 Platform 資料集中可供使用所需的時間相同或更短<!--add link? -->。</li><p>**提示：** 想要了解所有大量資料都完整並被攝取至 Platform 資料集所需的時間，最準確方法是諮詢組織中的資料工程師。</p><p>或者，您可以在 Analysis Workspace 中建立以下自由格式表格，以便大致了解組織中的大量資料傳遞在 Platform 資料集中可供使用需要多長時間：</p><ol><li>在 Analysis Workspace 中的自由格式表格中，新增一個「[!UICONTROL **事件**]」量度和一個「[!UICONTROL **天**]」維度。</li><li>使用「[!UICONTROL **小時**]」維度來劃分「[!UICONTROL **天**]」維度。<p>沒有數資料的小時維度將顯示為 0。</p></li></ol><li>**解決計算中的錯誤**：如果您減少預設延遲時間，我們建議將延遲時間設定為至少比您組織得到完整資料攝取所需的時間長一個小時。例如，如果得到完整資料攝取之前有 3 小時的延遲，那麼您應該將延遲設為 4 小時。</li></ul><p>若要了解更多資訊，請參閱文章「[警報功能比較：Customer Journey Analytics 和 Adob&#x200B;&#x200B;e Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)」中的「[Customer Journey Analytics 中的資料攝取時間有所不同](/help/components/c-intelligent-alerts/alerts-feature-comparison.md#data-ingestion-times-vary-in-customer-journey-analytics)」。 |
| **[!UICONTROL 傳送警報的時機]** | [!UICONTROL **這些量度中的任何一個均會觸發**]：將量度 (包括計算量度) 拖放至此處，以建立警報觸發程式。<p>如果並非所有警報中的量度、維度或區段均與目前選取資料檢視相容，系統會顯示&#x200B;**「不相容的元件」**&#x200B;訊息。</p><p>確定觸發警報前必須超過的量度臨界值。您可以將此值設為臨界值以及下列其中一個條件：</p><ul><li>存在異常</li><li>異常超出預期</li><li>異常低於預期</li><li>高於或等於</li><li>低於或等於</li><li>變更者</li><li>您可以設定 90%、95%、99%、99.75% 或 99.9% 的臨界值。</li></ul><p>[!UICONTROL **包含所有這些區段**]：拖放區段或維度以新增區段。 例如，新增「僅限行動裝置」區段可以代表規則僅會針對行動裝置而觸發。您可以使用AND陳述式新增其他區段。 您可按一下齒輪圖示，新增 AND 或 OR 規則。</p><p>請參閱「[警報 - 使用案例](/help/components/c-intelligent-alerts/alerts-use-cases.md)」，了解用例範例。</p> |
| **[!UICONTROL 預覽]** | 互動式警報預覽會根據過去經驗，顯示觸發警報的大約頻率。<p>例如，如果您將時間詳細程度設為每日，則預覽可告訴您在過去 30 或 31 天裡，針對某個量度觸發了 x 次警報。</p><p>如果您覺得觸發的警報次數過多，可在「[管理警報器](/help/components/c-intelligent-alerts/alert-manager.md)」中調整臨界值。</p><p>![](assets/alert-preview.png){width="50%"}</p> |
