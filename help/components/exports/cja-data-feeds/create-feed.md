---
title: 建立資料摘要
description: 了解如何建立資料摘要，以及需提供給 Adobe 的檔案資訊。
hide: true
feature: Components
autotag-review: '2026-05-19T08:45:44.870Z'
TQID: 'https://experienceleague.adobe.com/QgBD7vCkw4YA568XOLlwTnw8eZVZybXr3DFbM1ZKYDw'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 06e88df9fddaf292cfeef11e9b7d9a08e47cc7c5
workflow-type: tm+mt
source-wordcount: 3709
ht-degree: 22%

---

# 建立資料摘要

{{release-limited-testing}}

建立資料摘要時，您需要向 Adobe 提供：

* 關於原始資料檔案傳送目標的相關資訊

* 您要在每個檔案中包含的資料

* 傳送資料的頻率（包括擷取延遲抵達事件的處理延遲）

在建立資料摘要之前，務必先對資料摘要有基本的了解，並確認您已滿足所有先決條件。 如需詳細資訊，請參閱[資料摘要概觀](data-feed-overview.md)。

## 建立並設定資料摘要 {#create-and-configure-data-feed}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_export_file"
>title="manifest"
>abstract="選擇是否在每次傳送資料摘要時包含資訊清單檔案。 資訊清單檔案包含資料摘要中所包含之每個檔案的相關資訊。 在以單一封裝傳送資料摘要的資料時，您也可以選擇包含完成檔案，但建議包含資訊清單檔案。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_notify"
>title="完成時通知"
>abstract="指定一或多個電子郵件地址，在傳送資料摘要後，向其傳送通知。 多個電子郵件地址必須以逗號分隔。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_lookback_date_range"
>title="回顧日期範圍"
>abstract="控制Customer Journey Analytics在尋找符合資料摘要傳送資格的事件時回顧的時間範圍。<br/>如果事件發生在回顧日期範圍內，則仍可包含落在頻率範圍（特定小時或日）以外的事件。 是否包含事件取決於下列因素：區段資格、工作階段計算、衍生欄位轉換，以及維度持續性。<br/>較長的回顧日期範圍通常會產生更多事件；較短的範圍會產生較佳的傳遞效能。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_lookback_date_range"
>title="回顧日期範圍"
>abstract="控制Customer Journey Analytics在尋找符合資料摘要傳送資格的事件時回顧的時間範圍。 此設定類似於Analysis Workspace報告視窗，但有一些重要差異。<br/>如果事件發生在回顧日期範圍內，則仍可包含落在頻率範圍（特定小時或日）以外的事件。 是否包含事件取決於下列因素：區段資格、工作階段計算、衍生欄位轉換，以及維度持續性。<br/>較長的回顧日期範圍通常會產生更多事件；較短的範圍會產生較佳的傳遞效能。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_processing_delay"
>title="處理延遲"
>abstract="在處理資料摘要檔案之前，等候延遲送達事件的時間長度。 在處理延遲時段傳入的任何延遲送達點選都會納入資料摘要中。 <p>處理延遲因各種原因而相當實用，例如讓行動實施有機會讓離線裝置上線並傳送資料，或是在管理先前處理的檔案時容納組織的伺服器端程式。</p><p>工作階段必須在處理延遲截止之後開始才能納入；在截止之前開始並在處理延遲內結束的工作階段不包括在內。</p><p>Customer Journey Analytics會根據摘要延遲送達事件通常需要的時間，以動態方式決定最佳延遲，但您可以手動將其設定為延遲2、3、4或8小時。</p>"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_user-agent"
>title=""
>abstract="使用者代理資料和裝置查詢資料不得存在於相同的資料摘要設定中。"

<!-- markdownlint-enable MD034 -->

1. 使用您的 Adobe ID 認證登入 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。

1. 在介面右上方選取 [!UICONTROL **Customer Journey Analytics**] (透過應用程式切換器![應用程式](/help/assets/icons/Apps.svg))。

1. 在頂端導覽列中，前往&#x200B;[!UICONTROL **元件**] > [!UICONTROL **匯出**]。

1. 選取&#x200B;[!UICONTROL **資料摘要**]&#x200B;標籤。

1. 選取畫面右上角的&#x200B;[!UICONTROL **建立**]。

   或者，如果先前未建立任何資料摘要，請選取空白表格中的&#x200B;[!UICONTROL **建立資料摘要**]。

   會顯示包含以下索引標籤的頁面： [!UICONTROL **詳細資料**]、[!UICONTROL **資料結構**]&#x200B;和&#x200B;[!UICONTROL **傳遞**]。

   ![新資料摘要頁面](assets/data-feed-new.png)

1. 在&#x200B;[!UICONTROL **詳細資料**]&#x200B;標籤上，完成下列欄位：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **名稱**] | 資料摘要的名稱 名稱在選取的資料檢視中必須是唯一的，而且長度最多可為255個字元。<!--[Learn more](/help/export/analytics-data-feed/df-faq.md#must-feed-names-be-unique)--> |
   | [!UICONTROL **標記**] | 將任何標籤套用到資料摘要以方便分類。<!--You can filter on tags as described in [Filter and search the list of data feeds](/help/export/analytics-data-feed/df-manage-feeds.md#filter-and-search-the-list-of-data-feeds) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md).--> |
   | [!UICONTROL **說明**] | 指定資料摘要的說明（最多500個字元）。 編輯資料摘要時，會顯示您新增的說明。 |
   | [!UICONTROL **資料檢視**] | 選取包含您要匯出之資料的資料檢視。<p>選取資料檢視時，請考量下列事項：</p> <ul><li>如果相同資料檢視建立了多個資料摘要，則每個資料摘要都必須有不同的欄定義。</li><li>可用欄的清單取決於所選資料檢視所屬的登入公司。 如果您變更資料檢視，可用欄的清單可能會變更。 </li></ul> |

1. 選取&#x200B;[!UICONTROL **「下一步」**]。

1. 在&#x200B;[!UICONTROL **資料結構**]&#x200B;索引標籤上，確定在&#x200B;**[!UICONTROL 資料檢視]**&#x200B;欄位中選取了正確的資料檢視。

   <!--add screenshot-->

1. 在&#x200B;[!UICONTROL **區段**]&#x200B;下拉式功能表中，搜尋並選取任何區段以篩選摘要中包含的資料。

   套用多個區段時，它們會與AND運運算元連結。 若要使用OR運運算元聯結區段，您必須先在區段產生器中建立新區段，然後將新區段套用至資料摘要。

1. 將元件新增至資料摘要設定。 左側欄僅顯示對資料摘要有效的元件。

   * **拖放**：將元件從左側邊欄拖曳至畫布。 按住&#x200B;**[!UICONTROL Shift]**，或按住&#x200B;**[!UICONTROL Command]** (macOS)或&#x200B;**[!UICONTROL Ctrl]** (Windows)，一次選取和拖曳多個元件。
   * **加號按鈕**：選取左側邊欄中任何元件旁的加號![新增](/help/assets/icons/Add.svg)圖示，以將它新增至畫布。
   * **[!UICONTROL 全部顯示]**：選取元件清單底部的&#x200B;**[!UICONTROL 全部顯示]**&#x200B;以開啟顯示所有可用元件的對話方塊。 選取您要新增的每個元件旁的核取方塊，然後選取&#x200B;**[!UICONTROL 新增選取的專案]**。 當搜尋字詞或篩選器標籤在左側邊欄中作用中時，也會出現「**[!UICONTROL 新增全部]**」按鈕，讓您一次新增所有篩選結果。

   當您新增屬於XDM陣列欄位的元件（例如Adobe Journey Optimizer主張欄位）時，它會在畫布上顯示為可收合的巢狀群組，而不是平面專案。 群組會反映基礎資料結構，並輸出為匯出檔案中的巢狀陣列。

   <!--add screenshot-->

   +++ 資料摘要中一律包含的維度

   下列維度預設會包含在每個資料摘要中，且無法移除：

   | 維度名稱 | 附註 | 資料饋送 | 其他報告 |
   |---|---|---|---|
   | 時間戳記 UTC | 事件發生日期和時間，以UTC時區表示。 支援次秒（微秒）粒度。 | 強制 | 未提供 |
   | 列 ID | 資料摘要中包含的每列的唯一識別碼。 | 強制 | 未提供 |
   | 工作階段 ID | 資料摘要中包含的每個工作階段的唯一識別碼。 | 強制 | 未提供 |
   | 人員 ID | 資料檢視和連線的個人識別碼 | 強制 | 可選標準 |
   | 帳戶ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 使用帳戶容器時的帳戶ID | 強制 | 可選標準 |

   +++

   +++ 無法納入資料摘要的維度

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

   +++

   +++ 無法在資料摘要中搭配使用的維度

   >[!IMPORTANT]
   >
   >某些維度無法在Experience Platform資料集中一起使用，因此無法包含在相同的資料摘要中。
   >
   >如果您選擇在您的資料摘要中加入&#x200B;**使用者代理**&#x200B;或&#x200B;**行動識別碼**&#x200B;維度，則下列維度無法新增至資料摘要。
   >
   >如果您使用Web SDK，此限制會在資料到達Experience Platform資料集之前在資料串流中強制執行。 如需詳細資訊，請參閱資料收集指南中[建立及設定資料串流](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/datastreams/configure)中的[設定裝置查詢](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/datastreams/configure#geolocation-device-lookup)。

   下列維度無法與&#x200B;**使用者代理程式**&#x200B;或&#x200B;**行動識別碼**&#x200B;維度搭配使用：

   * 瀏覽器類型
   * 瀏覽器
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

   +++

   +++ 在資料摘要中必須替代的量度

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

   +++

   +++ 可選標準元件

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

   +++

1. （選用）拖曳畫布上的元件以重新排序元件。 您定義的順序會保留為匯出的資料摘要檔案中的欄順序。

1. （選用）變更資料摘要輸出中顯示的元件ID。

   1. 將滑鼠懸停在畫布上的元件上，然後選取資訊圖示。

   1. 在「元件ID」欄位中，指定新元件ID。

      <!--add screenshot-->

1. （選擇性）在繼續之前，請使用頁面右側的&#x200B;**[!UICONTROL 摘要摘要]**&#x200B;和&#x200B;**[!UICONTROL 結構描述預覽]**&#x200B;面板來檢閱您的資料結構：

   * **[!UICONTROL 摘要摘要]**&#x200B;會顯示您所新增的元件、欄、維度和量度總計即時計數。
   * **[!UICONTROL 結構描述預覽]**&#x200B;會顯示資料摘要結構描述的JSON表示法，此結構描述會隨著您新增或重新排序元件而更新。
   * **[!UICONTROL 範例列]**&#x200B;按鈕會開啟顯示範例輸出列的對話方塊，以便您驗證結構看起來是否正確。 此對話方塊只會顯示範例資料，不會反映您的實際資料。

   <!--add screenshot-->

1. 在&#x200B;[!UICONTROL **傳遞**]&#x200B;索引標籤的&#x200B;[!UICONTROL **排程**]&#x200B;區段中，選擇要建立的摘要型別（即時或回填），然後指定報告時段、頻率和其他設定選項：

   <!--add screenshot-->

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **摘要型別**] | 選取您要建立的摘要型別：<ul><li>[!UICONTROL **即時摘要**]：匯出目前和未來的資料。</li><li>[!UICONTROL **回填摘要**]：匯出歷史資料。 </li></ul> |
   | [!UICONTROL **開始日期**] | 資料摘要開始的日期。 對於即時摘要，這必須是今天或未來的日期。 對於回填摘要，這必須是資料檢視資料保留期間內的過去日期。 開始日期取決於資料檢視的時區。 |
   | [!UICONTROL **到期日**] <br/>僅供即時摘要使用 | 資料摘要到期且不再執行的日期。 日期取決於資料檢視的時區。 |
   | [!UICONTROL **結束日期**]<br/>&#x200B;僅供回填摘要使用 | 資料摘要結束的日期。 結束日期不能為未來日期。 日期取決於資料檢視的時區。 |
   | [!UICONTROL **頻率**] | 選取資料摘要的傳送頻率。 時間戳記屬於頻率視窗的事件會包含在資料摘要傳送中。 [!UICONTROL **回顧日期範圍**]&#x200B;及&#x200B;[!UICONTROL **處理延遲**]&#x200B;欄位也會影響哪些事件包含在您所選擇傳遞頻率的資料中。<p>對於即時摘要，選取此選項可包含一小時的資料量或一天的資料量。 對於回填摘要，此欄位已鎖定為&#x200B;**每日**，無法變更。</p><ul><li>**每日**：摘要包含一整天的資料，從資料檢視時區的午夜到午夜。 <p>回填摘要需要此選項，而即時摘要則是選用選項。</p></li><li>**小時**：摘要包含一個小時的資料量。 <p>此選項僅適用於即時摘要。</p></li></ul> |
   | [!UICONTROL **回顧日期範圍**] | 控制 Customer Journey Analytics 在處理資料摘要傳送時回顧的時間範圍。 預設值為30天。 <p>設定此選項時，請考量下列重要概念：</p><ul><li>較長的回顧日期範圍通常會導致更多事件；較短的範圍會導致更好的傳送效能。</li><li>資料摘要中的回顧日期範圍類似於Analysis Workspace中的報告日期範圍，但有[主要差異](/help/components/exports/cja-data-feeds/df-comparison-workspace.md#differences)。 這些差異可能會導致Workspace報表與資料摘要傳送之間的資料差異。 </li><li>此設定不會改變頻率視窗（小時或天），其定義要包含在資料摘要輸出中的事件時間範圍。 <p>如果事件發生在回顧日期範圍內，則仍可包含落於頻率期間之外的事件，具體取決於以下因素： </p><ul><li>**區段資格**：將區段套用至您的資料摘要定義時，回顧日期範圍內的任何事件都會決定某人是否符合資格。 區段的容器設定會決定範圍。 (可能的容器包括：「人員」、「工作階段」或「事件」。 B2B包括下列額外的容器：全域帳戶、帳戶、商機、購買群組。)  <p>例如，如果套用名為&#x200B;_購買_&#x200B;的訪客的區段，則一週的回顧將包含過去7天中購買的訪客在特定小時或當天（頻率視窗）的事件。 90天回顧會包含過去90天內購買者的活動</p></li><li>**工作階段計算**：工作階段範圍是使用回顧日期範圍內的資料計算。</li><li>**衍生欄位轉換**：參考容器的任何衍生欄位函式都會在資料摘要匯出中使用回顧日期範圍。</li><li>**Dimension持續性**：如果您選擇在個別維度上設定持續性，您也可選擇有效期限，以決定維度專案在其設定的事件之後持續多長時間。 設定為永續的維度會使用回顧日期範圍，以判斷資料摘要匯出的資格。  <p>當資料檢視中的到期日設定為下列任一選項時，回顧日期範圍會影響維度持續性：</p><ul><li>對於資料摘要定義中每個使用&#x200B;[!UICONTROL **報告期間**]&#x200B;作為到期日的維度，回顧日期範圍都會變成新的報告期間。</li><li>對於資料摘要定義中以&#x200B;[!UICONTROL **自訂時間**]&#x200B;作為到期時間的每個維度，如果選取的自訂時間超過回顧日期範圍，則忽略自訂時間，並將回顧日期範圍用於維度到期日。<p>如需有關在資料檢視中設定維度的持續性的詳細資訊，請參閱[持續性元件設定](/help/data-views/component-settings/persistence.md)。</p></li></ul><p>將回顧日期範圍設為等於或大於資料中維度所設定的持續性的值。 例如，如果促銷活動維度的到期日為30天，且某人兩週前點選該促銷活動時，則7天的回顧日期範圍不會儲存該值。</p></ul> |
   | [!UICONTROL **處理延遲**] | 選擇在處理資料摘要檔案之前要等待的時間長度。 預設值為2小時。 在處理延遲期間傳入的任何延遲送達事件都會納入資料摘要中。 <p>處理延遲因各種原因而相當實用，例如讓行動實施有機會讓離線裝置上線並傳送資料，或是在管理先前處理的檔案時容納組織的伺服器端程式。 </p><p>工作階段必須在處理延遲截止之後開始才能納入；在截止之前開始並在處理延遲內結束的工作階段不包括在內。</p><p>Customer Journey Analytics會根據摘要延遲送達事件通常需要的時間，以動態方式決定最佳延遲，但您可以手動將其設定為延遲2、3、4或8小時。</p> |
   | [!UICONTROL **壓縮格式**] | 為傳送到雲端目的地的Parquet輸出檔案選取壓縮格式。 從下列格式中選擇：<ul><li>[!UICONTROL **快取**]：檔案大小適中，可快速壓縮與解壓縮。 受到現代化資料平台（例如BigQuery、Snowflake和Apache Spark）的廣泛支援。</li><li>[!UICONTROL **GZip**]：廣泛相容，包括本機不支援Snappy的工具。 如果您的下游管道需要廣泛認可的壓縮標準，則建議使用。</li><li>[!UICONTROL **Z標準(Zstd)**]：快速解壓縮的高壓縮效率。 如果優先考慮檔案大小最小化，且您的工具支援Zstd，則適合使用。</li></ul> |

1. 在&#x200B;[!UICONTROL **傳遞**]&#x200B;標籤的&#x200B;[!UICONTROL **目的地**]&#x200B;區段中，設定您要傳送資料的目的地。

   >[!NOTE]
   >
   >設定報告目標時，請考慮以下事項：
   >
   ><!--* Adobe recommends using a cloud account for your report destination. [Legacy FTP and SFTP accounts](/help/components/locations/configure-import-accounts.md) are available, but are not recommended.-->
   >* 您先前設定的任何雲端帳戶都可用於資料摘要。 您可以從「位置」管理員的[元件>匯出>位置帳戶](/help/components/exports/cloud-export-accounts.md)中設定雲端帳戶。
   >
   >* 雲端帳戶與您的Customer Journey Analytics使用者帳戶相關聯。 其他使用者無法使用或檢視您設定的雲端帳戶，除非您提供這些帳戶給組織中的所有使用者。
   >
   >* 您可以在[元件>匯出>位置](/help/components/exports/cloud-export-locations.md)中，編輯從「位置」管理員建立的任何位置。

   填入下列欄位：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **檢視所有使用者的目的地**] | 如果您是系統管理員，則可以啟用此選項以檢視組織中所有使用者建立的目的地。 停用此選項時，只會顯示您建立的目的地。 |
   | [!UICONTROL **帳戶**] | 進行下列一項：<ul><li>**使用現有帳戶：**&#x200B;選取&#x200B;**[!UICONTROL 帳戶]**&#x200B;欄位旁的下拉式功能表。 或者，開始輸入帳戶名稱，然後從下拉式選單中選取。 <p>只有在您已設定帳戶，或帳戶與您所屬的某個組織共用時，您才可使用帳戶。</p></li><li>**建立新帳戶：**&#x200B;在&#x200B;**[!UICONTROL 帳戶]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 新增帳戶]**。 如需有關如何設定帳戶的資訊，請參閱[設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md)。</li></ul> |
   | [!UICONTROL **位置**] | 進行下列一項：<ul><li>**使用現有的位置：**&#x200B;選取&#x200B;**[!UICONTROL 位置]**&#x200B;欄位旁的下拉式功能表。 或者，開始輸入位置名稱，然後從下拉式選單中選取它。</li><li>**建立新位置：**&#x200B;在&#x200B;**[!UICONTROL 位置]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 新增位置]**。 如需有關如何設定位置的資訊，請參閱[設定雲端匯出位置](/help/components/exports/cloud-export-locations.md)。</li></ul> |
   | [!UICONTROL **完成時通知**] | 指定一或多個電子郵件地址，在資料摘要成功傳送或無法傳送後，應傳送通知。 多個電子郵件地址必須以逗號分隔。 |
   | [!UICONTROL **啟用資訊清單**] | 選擇是否在每次傳送資料摘要時包含資訊清單檔案。 資訊清單檔案包含資料摘要中所包含每個檔案的資訊。 |

1. 選取&#x200B;**[!UICONTROL 「儲存」]**。


