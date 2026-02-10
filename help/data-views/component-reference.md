---
title: 標準元件參考
description: 瞭解您可以新增到任何資料檢視的所有標準元件的詳細資訊和資訊。
exl-id: e23ce27a-77ab-4641-a126-93f00d4e6e14
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 4f1299595077a1756a6ad0c4f5ef5e0247ab4973
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 88%

---

# 標準元件參考

Customer Journey Analytics 中的大多數維度和量度都根據 Adobe Experience Platform 資料集中的結構描述元素。但是，無論您使用何種連線，都可以將多個元件新增到資料檢視中。

[!UICONTROL 標準元件]是不是從資料集結構欄位產生，而是從系統產生的元件。需要一些系統元件，以利 Analysis Workspace 的報告功能，而其他系統元件則是選用的。

![標準元件](assets/dataview-standard-components.png)

## 必要標準元件 {#required}

依預設，這些必要的標準元件會新增至每個資料檢視。它們對於 Customer Journey Analytics 提供的報告功能至關重要。

### 標準維度

{{standard-dimensions}}


### 標準量度

{{standard-metrics}}


## 可選標準元件 {#optional}

可選的標準元件位於「**[!UICONTROL 資料檢視]** > **[!UICONTROL 編輯資料檢視]** > **[!UICONTROL 元件]** tab > **[!UICONTROL 標準元件]**」標籤下。

| 元件名稱 | 維度或量度 | 附註和值 |
| --- | --- | --- |
| [!UICONTROL 上午/下午] | 時間分段維度 | 上午或下午 |
| [!UICONTROL 批次 ID]  | 維度 | [!UICONTROL 事件]所屬的Experience Platform批次識別碼。 |
| [!UICONTROL 資料集 ID] | 維度 | [!UICONTROL 事件]所屬之Experience Platform資料集的識別碼。 |
| [!UICONTROL 日期] | 時間分段維度 | 1-31 |
| [!UICONTROL 星期] | 時間分段維度 | 星期一、星期二、星期三、星期四、星期五、星期六、星期日 |
| [!UICONTROL 一年當中的第幾天] | 時間分段維度 | 1-366 |
| [!UICONTROL 小時] | 時間分段維度 | 0-23 |
| [!UICONTROL  月份] | 時間分段維度 | 1 月至 12 月 |
| [!UICONTROL 首次工作階段] | 量度 | 個人在報告時段內定義的首次工作階段。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#new-repeat) |
| [!UICONTROL 重返工作階段] | 量度 | 不是個人的首次工作階段的工作階段數量。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#new-repeat) |
| [!UICONTROL 個人 ID] | 維度 | 在 Experience Platform 中定義的每個資料集結構描述，都可以各自擁有一組已定義且與身分識別命名空間相互關聯的一個或多個身分識別。任何一個身分識別碼都可當做人員 ID 使用。範例包括 Cookie ID、彙整 ID、使用者 ID、追蹤程式碼等。「[!UICONTROL 人員 ID]」維度是 Customer Journey Analytics 中結合資料集和識別不重複人員的基礎。<p>可能的使用案例包含：<ul><li>在特定人員ID值上建立區段，以將所有專案細分為該使用者的行為。</li><li>偵錯：確定有特定 Cookie ID (或特定客戶 ID) 的資料。</li><li>識別致電呼叫中心的用戶。</li></ul> |
| [!UICONTROL 人員 ID 命名空間] | 維度 | 組成[!UICONTROL 人員 ID] 的 ID 類型。範例有：`email address`、`cookie ID`、`Analytics ID` |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL 全域帳戶 ID] | 維度 | 當您在連線中使用全域帳戶容器時，請輸入[!UICONTROL 全域帳戶 ID]。 |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL 帳戶 ID] | 維度 | [!UICONTROL 帳戶ID]，當您在連線中使用帳戶容器時。 |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL 機會 ID] | 維度 | 當您在連線中使用機會容器時，請輸入[!UICONTROL 機會 ID]。 |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL 購買群組 ID] | 維度 | 當您在連線中使用購買群組容器時，請輸入[!UICONTROL 購買群組 ID]。 |
| [!UICONTROL 季別] | 時間分段維度 | 第 1 季、第 2 季、第 3 季、第 4 季 |
| [!UICONTROL 重複工作階段] | 量度 | 不是個人的首次工作階段的工作階段數量。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#new-repeat) |
| [!UICONTROL 工作階段類型] | 維度 | 此維度有兩個值：1. [!UICONTROL 首次]和 2. 回訪。[!UICONTROL 首次]條列項目包含已確定為個人定義的首次工作階段之工作階段中所有行為，即此維度的量度。所有其他資料都會包含在[!UICONTROL 回訪]條列項目中 (假設所有資料都屬於一個工作階段)。如果量度不屬於任何工作階段，則將屬於此維度的「不適用」貯體。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#new-repeat) |
| [!UICONTROL 每個事件逗留時間] | 維度 | 將「[!UICONTROL 逗留時間]」量度儲存至「[!UICONTROL 事件]」值區。 |
| [!UICONTROL 每個工作階段逗留時間] | 維度 | 將「[!UICONTROL 逗留時間]」量度儲存至「[!UICONTROL 工作階段]」值區。 |
| [!UICONTROL 每人逗留時間] | 維度 | 將「[!UICONTROL 逗留時間]」量度儲存至「[!UICONTROL 人員]」值區。 |
| [!UICONTROL 週末]/[!UICONTROL 平常日] | 時間分段維度 | 週末或平常日 |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[利用事件深度功能探索更深入的客戶洞察](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/discover-deeper-customer-insights-with-adobe-customer-journey/ba-p/753947#M576?lang=zh-Hant)
>