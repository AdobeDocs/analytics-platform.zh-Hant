---
description: 當專案元件達到特定臨界值時，收到警報。
title: 建立警報(Analysis Workspace)
feature: Workspace Basics
role: User, Admin
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '974'
ht-degree: 19%

---

# 建立警報 {#create-alerts}

>[!NOTE]
>
>使用具有異常偵測的警報（也稱為&#x200B;_智慧型警報_）僅適用於具有Select、Prime或UltimateCustomer Journey Analytics封裝的組織。

Customer Journey Analytics中的警報可讓您根據變更的百分比或特定資料點收到通知。 視您的Customer Journey Analytics封裝而定，您也可以使用要根據異常臨界值觸發的警報。

如需警示的詳細概觀資訊，請參閱[警示概觀](/help/components/c-intelligent-alerts/intelligent-alerts.md)。

若要建立警示：

1. 在Customer Journey Analytics<!-- add this back in after the other methods are available like in AA and make a bulleted list: "You can access the alert builder in any of the following ways:" -->中，選取&#x200B;**[!UICONTROL 元件]** > **[!UICONTROL 警示]**。 在[警示管理員](alert-manager.md)中，選取![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]**&#x200B;來建立新警示，或選取列出的任何警示來修改現有警示。

   [警報產生器](#alert-builder)介面隨即顯示。

1. 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存警示。 選取&#x200B;**[!UICONTROL 另存新檔]**&#x200B;以儲存警示的復本。


## 警報產生器

警報產生器的介面與在Customer Journey Analytics中建立篩選器或計算量度類似：

![](assets/alert-builder.png)

在「警報產生器」中指定警報的下列詳細資料：

| 元素 | 說明 |
|---------|----------|
| **[!UICONTROL 標題]** | 指定警報的名稱。警報名稱中可以包含報表的名稱或量度臨界值。 |
| **[!UICONTROL 描述（選擇性）]** | 指定警示的說明。 |
| **[!UICONTROL 時間粒度]** | 選取您希望檢查量度的頻率：每日、每週或每月。<p><b>注意：</b>對於使用自訂日曆的資料檢視，警報產生器不支援每月粒度。<!--true?--></p> |
| **[!UICONTROL 收件者]** | 指定可傳送警報的位置。警報可以傳送給 Analytics 用戶、Analytics 群組、原始電子郵件地址或電話號碼。<p><b>重要：</b>電話號碼前面必須加上「+」和[國家/地區代碼](https://countrycode.org/)。</p><p>使用者在警報觸發後收到的電子郵件顯示如下：</p><p>![警示電子郵件](assets/alerts-email.PNG)</p> |
| **[!UICONTROL 到期日]** | 設定您想要警報到期的日期和時間。 |
| **[!UICONTROL 延遲]** | 完成資料並可在Customer Journey Analytics中報告之前所需的時間因組織而異，通常比資料事件時間晚3到9個小時。 為了警示準確，指定事件範圍的事件資料必須完整，這表示Adobe不再接收指定事件範圍的任何事件資料。<p>考慮到這種擷取時間延遲，警報在傳送前的預設延遲為9小時。</p><p>您可以將9小時的預設延遲調整為0到24小時之間的任何時間。 但是，將延遲減少到9小時以下可能表示您報告的是不完整的資料，這會導致不準確的警報資訊。</p><p>減少延遲時間時，請考量下列事項：</p><ul><li>**瞭解資料可用性與資料完整性**：雖然某些資料可能可以在更早的時間內提供報告，但所有批次資料只會在3到9個小時後擷取到Platform資料集中。 若要讓警報準確，資料擷取必須完成，且資料集中提供所有批次資料。</li><li>**決定完成您的資料並在資料集中取得所需的時間**：資料擷取時間會因組織而異。 請確定您選擇的警示傳送延遲時間，與批次資料在Platform資料集<!--add link? -->中可用的時間相同或較短。</li><p>**秘訣：**&#x200B;要瞭解完成所有批次資料並擷取到Platform資料集所需的時間，最準確的方式是諮詢貴組織的資料工程師。</p><p>或者，您可以在Analysis Workspace中建立下列自由表格，大致瞭解組織中的批次傳送需要多久才能在Platform資料集中使用：</p><ol><li>在Analysis Workspace的自由格式表格中，新增&#x200B;[!UICONTROL **事件**]&#x200B;量度和&#x200B;[!UICONTROL **日**]&#x200B;維度。</li><li>使用&#x200B;[!UICONTROL **小時**]&#x200B;維度劃分&#x200B;[!UICONTROL **天**]&#x200B;維度。<p>沒有資料的時數會顯示為0。</p></li></ol><li>**計算錯誤的原因**：如果您減少預設的延遲時間，我們建議您設定延遲時間，至少比貴組織完成資料擷取所花的時間長一小時。 例如，如果資料擷取完成之前有3小時的延遲，則應將延遲設定為4小時。</li></ul><p>如需詳細資訊，請參閱文章[警示功能比較：Customer Journey Analytics和Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)中的[資料擷取時間在Customer Journey Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md#data-ingestion-times-vary-in-customer-journey-analytics)中不同。 |
| **[!UICONTROL 傳送警報的時機]** | [!UICONTROL **這些量度觸發器的任一項**]：將量度（包括計算量度）拖放到這裡，以建立警示的觸發器。<p>如果警報中並非所有量度、維度或區段都與目前選取的資料檢視相容，則會出現&#x200B;**「不相容的元件」**&#x200B;訊息。</p><p>確定觸發警報前必須超過的量度臨界值。您可以將此值設為臨界值以及下列其中一個條件：</p><ul><li>存在異常</li><li>異常超出預期</li><li>異常低於預期</li><li>高於或等於</li><li>低於或等於</li><li>變更者</li><li>您可以設定 90%、95%、99%、99.75% 或 99.9% 的臨界值。</li></ul><p>[!UICONTROL **包含所有這些篩選器**]：拖放區段或維度以新增篩選器。 例如，新增「僅限行動裝置」區段表示規則僅會針對行動裝置觸發。 您可以使用AND陳述式來新增其他篩選器。 您可按一下齒輪圖示，新增 AND 或 OR 規則。</p><p>檢視[警示 — 使用案例](/help/components/c-intelligent-alerts/alerts-use-cases.md)的使用案例範例。</p> |
| **[!UICONTROL 預覽]** | 互動式警報預覽會根據過去經驗，顯示觸發警報的大約頻率。<p>例如，如果您將時間詳細程度設為每日，則預覽可告訴您在過去 30 或 31 天裡，針對某個量度觸發了 x 次警報。</p><p>如果您發現觸發的警報次數過多，可在[管理警報](/help/components/c-intelligent-alerts/alert-manager.md)中調整臨界值。</p><p>![](assets/alert-preview.png){width="50%"}</p> |

