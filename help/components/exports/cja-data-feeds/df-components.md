---
title: Customer Journey Analytics資料摘要中可用的元件
description: 瞭解建立Customer Journey Analytics資料摘要時，需要、不支援、受限制或必須替代哪些維度和量度。
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 56f881fc811f0eeffb9633872b3edbe0eb2d7070
workflow-type: tm+mt
source-wordcount: '1596'
ht-degree: 39%
---
# 資料摘要中的元件可用性

{{release-limited-testing}}

並非所有Customer Journey Analytics元件都可在資料摘要中使用。 有些維度會包含在每個資料摘要中，有些元件則無法包含，而且有些量度必須以替代專案取代。

使用下列資訊來瞭解當您[建立資料摘要](/help/components/exports/cja-data-feeds/create-feed.md)時可以包含哪些元件。

## 必要的維度 {#required-dimensions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_required_dimensions"
>title="必要的維度"
>abstract="每個資料摘要都必須包含特定維度，以維度名稱旁的&#x200B;**必要**&#x200B;標籤來識別。 這些維度可提供事件層級分析所需的最低結構。"

<!-- markdownlint-enable MD034 -->

下列維度預設會包含在每個資料摘要中，且無法移除：

| 維度名稱 | 附註 | 資料饋送 | 其他報告 |
|---|---|---|---|
| 時間戳記 UTC | 事件發生日期和時間，以UTC時區表示。 支援次秒（微秒）粒度。 | 必填 | 未提供 |
| 列 ID | 資料摘要中包含的每列的唯一識別碼。 | 必填 | 未提供 |
| 工作階段 ID | 資料摘要中包含的每個工作階段的唯一識別碼。 | 必填 | 未提供 |
| 人員 ID | 資料檢視和連線的個人識別碼 | 必填 | 可選標準 |
| 帳戶ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 使用帳戶容器時的帳戶ID | 必填 | 可選標準 |

## 不支援的維度 {#unsupported-dimensions}

Customer Journey Analytics標準維度不得包含在資料摘要中。 下表列出這些維度：

| 維度名稱 | 附註 | 資料饋送 |
|---|---|---|
| 5 分鐘 | 事件發生時的五分鐘間隔（無條件舍去） | 未提供 |
| 15 分鐘 | 發生事件時的15分鐘間隔（無條件舍去） | 未提供 |
| 30 分鐘 | 發生事件時的30分鐘間隔（無條件舍去） | 未提供 |
| 日 | 事件發生日期 | 未提供 |
| 星期 | 事件發生的一週中的第幾天 | 未提供 |
| 當月日期 | 事件發生當月的第幾天 | 未提供 |
| 小時 | 發生事件的小時（無條件舍去） | 未提供 |
| 小時 | 事件發生當天的小時（無條件舍去） | 未提供 |
| 分鐘 | 發生事件的分鐘數（無條件舍去） | 未提供 |
| 小時期間各分鐘 | 發生事件當小時的分鐘（無條件舍去） | 未提供 |
| 月 | 發生事件的月份 | 未提供 |
| 月份 | 發生事件的月份 | 未提供 |
| 季 | 季度發生事件 | 未提供 |
| 季別 | 發生事件的季別 | 未提供 |
| Second | 發生事件第二次（無條件舍去） | 未提供 |
| 週 | 事件發生周 | 未提供 |
| 年度內的第幾週 | 事件發生的一年中的第幾週 | 未提供 |
| 年 | 事件發生年份 | 未提供 |

## 不支援的量度 {#unsupported-metrics}

下列Customer Journey Analytics標準量度無法納入資料摘要中：

| 量度名稱 | 附註 | 資料饋送 |
|---|---|---|
| Adobe訪客設定檔 | | 未提供 |
| Adobe機會聯盟 | | 未提供 |
| Adobe機會設定檔 | | 未提供 |
| Adobe帳戶聯合 | | 未提供 |
| Adobe帳戶設定檔 | | 未提供 |
| Adobe購買群組聯盟 | | 未提供 |
| Adobe購買群組設定檔 | | 未提供 |
| Adobe全球帳戶聯盟 | | 未提供 |
| Adobe全域帳戶設定檔 | | 未提供 |
| Adobe人員聯盟 | | 未提供 |
| Adobe人員設定檔 | | 未提供 |

## 無法搭配使用的維度 {#incompatible-dimensions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_user_agent"
>title="無法搭配使用的維度"
>abstract="使用者代理資料和裝置查詢資料不得存在於相同的資料摘要設定中。"

<!-- markdownlint-enable MD034 -->

某些維度無法在Experience Platform資料集中搭配使用。 資料摘要可以包含下列其中一個群組的維度，但不能同時包含這兩個群組的維度：

* **使用者代理程式**&#x200B;和&#x200B;**行動識別碼**&#x200B;維度。<!--UI shows "Type identifier" for device.typeID; align with docs name "Mobile ID" (open question for Danny Carmen).-->

* 裝置查詢維度，例如瀏覽器、行動裝置和作業系統維度。 如需完整清單，請參閱[裝置查詢維度](#device-lookup-dimensions)。

此限制也適用於參照這些維度的衍生欄位。

>[!NOTE]
>
>如果您使用Web SDK，此限制會在資料到達Experience Platform資料集之前在資料串流中強制執行。 如需詳細資訊，請參閱資料收集指南中[建立及設定資料串流](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/datastreams/configure)中的[設定裝置查詢](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/datastreams/configure#geolocation-device-lookup)。

<!--
SME CHECK (derived fields; from Slack thread with Ron Fulkerson, Matt Freestone, Courtney Ferguson). Assumptions to confirm:
1. Derived fields are restricted only when combined with dimensions from the other group. They aren't blocked from data feeds entirely.
2. The restriction applies in both directions. Derived fields that reference User agent or Mobile ID conflict with device lookup dimensions, not only the reverse.
3. The restriction applies to nested derived fields (a derived field that references another derived field that references a restricted dimension).
4. "Device Atlas sourced" dimensions are the same set as the device lookup dimensions listed on this page.
5. The restriction itself is permanent.
6. Derived fields get the same conflict dialog experience as dimensions (per Matt Freestone). This requires the UI to identify which derived fields reference these dimensions; Courtney Ferguson said the UI doesn't have that information today. Confirm this will be built before release.
7. The priority rules in "Resolve dimension conflicts" apply to derived fields the same way they apply to the dimensions they reference. For example, a derived field that references User agent takes priority over device lookup dimensions in the same selection.
8. Editing a derived field that is already in a data feed so that it references a conflicting dimension fails when the user adds the conflicting dimension to the derived field. Does this check every data feed that uses the derived field? What does the error say?
Open question: Can a derived field that references dimensions from BOTH groups be added to any data feed?
-->

### 解決維度衝突

當您新增無法一起使用的維度時（包括參照這些維度的衍生欄位），會出現一個對話方塊，列出將新增以及不會新增或移除的維度。 下表會根據衝突發生位置顯示相關作業：

| 衝突 | 優先順序 | 結果 |
|---|---|---|
| 您新增的維度與資料摘要中的維度發生衝突 | 您新增的維度 | 新維度會取代資料摘要中現有的衝突維度。 |
| 您新增的維度彼此衝突 | **使用者代理程式**&#x200B;和&#x200B;**行動識別碼**&#x200B;維度（以及參照它們的衍生欄位） | 選取範圍中的裝置查詢維度（以及參照這些維度的衍生欄位）不會新增。 您選取的其餘部分會新增至資料摘要。 |

{style="table-layout:auto"}

若要保持資料摘要不變，請選取&#x200B;**[!UICONTROL 取消]**。

<!--Open questions for Danny Carmen: behavior when a batch contains both groups and the feed already has conflicting dimensions; whether "add all" adds the full selection or only the listed dimensions.-->

### 裝置查詢維度 {#device-lookup-dimensions}

下列維度（以及參考這些維度的任何衍生欄位）無法與&#x200B;**使用者代理程式**&#x200B;或&#x200B;**行動識別碼**&#x200B;維度包含在相同的資料摘要中。

>[!NOTE]
>
>下列清單使用預設的維度名稱。 在資料檢視中重新命名的維度會以其自訂名稱顯示在資料摘要中。

<!--Engineering lists 30 device lookup fields; this list has 28. Likely missing: environment.operatingSystemIDStr and environment.browserIDStr. Confirm display names with Danny Carmen.-->

* 瀏覽器類型
* 瀏覽器
* 瀏覽器ID
* 行動製造商
* 行動裝置類型
* 行動音訊支援
* 行動 DRM
* 行動 Java VM
* 行動資訊服務
* 行動影像支援
* 行動色彩深度
* 行動網路通訊協定
* 行動裝置號碼
* 行動電子郵件的最大長度
* 行動郵件裝飾
* 行動即按即說 (Push To Talk)
* 行動螢幕寬度
* 行動瀏覽器 URL 的最大長度
* 行動作業系統 (已棄用)
* 行動螢幕高度
* 行動視訊支援
* 行動 Cookie 支援
* 行動書籤 的最大長度
* 行動螢幕大小
* 行動裝置名稱
* 作業系統類型
* 作業系統
* 作業系統ID

## 需要替代的量度 {#substitute-metrics}

下列Customer Journey Analytics量度必須被取代：

| 量度名稱 | 附註 | 資料饋送 |
|---|---|---|
| 帳戶 [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 根據連線中指定的帳戶ID | 無法使用。 使用帳戶ID的相異計數。 |
| 購買群組[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 根據連線中的購買群組ID購買群組 | 無法使用。 使用購買群組ID的相異計數。 |
| 活動 | 連線中所有事件資料集的列數 | 無法使用。 使用資料列ID的相異計數。 |
| 全域帳戶 [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 根據連線中的全域帳戶ID | 無法使用。 使用全域帳戶ID的相異計數。 |
| 機會 [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 根據連線中的機會ID的機會 | 無法使用。 使用與機會ID不同的計數。 |
| 使用者 | 根據連線中指定的人員ID | 無法使用。 使用人員ID的相異計數。 |
| 對話數 | 交談數 | 無法使用。 使用對話識別碼的相異計數。 |
| 工作階段結束 | 工作階段中最後一個事件的事件數 | 未提供 |
| 工作階段開始 | 工作階段中第一個事件的事件數 | 未提供 |
| 工作階段 | 根據資料檢視的工作階段設定 | 無法使用。 使用工作階段ID的相異計數。 |
| 逗留時間（秒） | 加總兩個不同維度值之間的時間 | 未提供 |

## 可選標準元件 {#optional-standard-components}

| 元件名稱 | 類型 | 附註 | 資料饋送 |
|---|---|---|---|
| 上午/下午 | 時間分段維度 | 上午或下午 | 未提供 |
| 批次 ID | 維度 | Experience Platform批次的識別碼 | 可用 |
| 資料集 ID | 維度 | Experience Platform資料集的識別碼 | 可用 |
| 當月日期 | 時間分段維度 | 1-31 | 未提供 |
| 星期 | 時間分段維度 | 星期一到星期日 | 未提供 |
| 年中的日 | 時間分段維度 | 1-366 | 未提供 |
| 事件深度 | 維度 | 循序數值（1、2、3等） 指派給工作階段中的每個事件互動<p>在每個新工作階段開始時重設</p> | 可用 |
| 小時 | 時間分段維度 | 0-23 | 未提供 |
| 月份 | 時間分段維度 | 1-12月 | 未提供 |
| 首次工作階段 | 量度 | 個人在報告時段內首次定義的工作階段 | 未提供 |
| 回訪工作階段 | 量度 | 非個人首次工作階段的工作階段 | 未提供 |
| 人員ID名稱空間 | 維度 | 組成人員ID的ID型別（例如電子郵件或Cookie ID） | 可用 |
| 全域帳戶ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 維度 | 使用全域帳戶容器時的全域帳戶ID | 可用 |
| 機會ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 維度 | 使用機會容器時的機會識別碼 | 可用 |
| 購買群組ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 維度 | 使用購買群組容器時的購買群組ID | 可用 |
| 季別 | 時間分段維度 | 第 1 季、第 2 季、第 3 季、第 4 季 | 未提供 |
| 重複工作階段 | 量度 | 不是個人的首次工作階段的工作階段 | 未提供 |
| 工作階段型別 | 維度 | 兩個值：首次或傳回 | 未提供 |
| 每個事件逗留時間 | 維度 | 將「逗留時間」量度儲存至事件值區 | 未提供 |
| 每個工作階段逗留時間 | 維度 | 將「逗留時間」量度儲存至「工作階段」值區 | 未提供 |
| 每人逗留時間 | 維度 | 將「逗留時間」量度儲存至人員值區 | 未提供 |
| 週末/平常日 | 時間分段維度 | 週末或平常日 | 未提供 |
