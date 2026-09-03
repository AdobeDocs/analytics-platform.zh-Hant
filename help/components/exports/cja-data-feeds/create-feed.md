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
source-git-commit: f5a7272f80aaba167974f2218bc84408d47f62d4
workflow-type: tm+mt
source-wordcount: 4217
ht-degree: 30%

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
>title="通知問題、完成時間和到期時間"
>abstract="指定一個或多個電子郵件地址，在資料摘要完成、即將到期或遇到問題時，應向這些地址傳送通知。 請使用逗號分隔多個電子郵件地址。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_processing_delay"
>title="處理延遲"
>abstract="處理資料摘要檔案前，等待延遲送達事件所花費的時間。 在處理延遲時段內到達的任何延遲送達事件資料，都會納入資料摘要。 <p>處理延遲在很多方面都很實用，例如讓行動實施有機會讓離線裝置恢復連線並傳送資料，或配合您組織伺服器端管理先前處理之檔案的程序。</p><p>工作階段必須在處理延遲截止時間之後開始，才能納入；在截止時間之前開始、並在處理延遲期間以內結束的工作階段則不會納入。</p><p>Customer Journey Analytics 會根據延遲送達事件通常花費多少時間傳送至您的摘要，動態判斷最佳延遲時間，但您也可以手動將延遲時間設定為 2、3、4 或 8 小時。</p>"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_user-agent"
>title=""
>abstract="使用者代理資料和裝置查詢資料不得存在於相同的資料摘要設定中。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_required_dimensions"
>title="必要維度"
>abstract="每個資料摘要都必須包含特定維度，以維度名稱旁的&#x200B;**必要**&#x200B;標籤來識別。 這些維度提供事件層級分析所需的最低結構。"

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

   您在此處套用的區段，是可能已在資料檢視中套用的任何區段以外的區段。

1. （選擇性）在左側邊欄中，使用&#x200B;**搜尋**&#x200B;欄位來找出特定元件。 或者，選取&#x200B;**排序**&#x200B;圖示![排序元件圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)以套用下列任何排序選項：

   | 選項 | 函數 |
   | --------- | ---------- |
   | [!UICONTROL **建議**] | 以建議置於清單頂端的元件來對元件進行排序。 您或貴組織中其他人近期最頻繁使用的元件會顯示在清單的較高位置。 |
   | [!UICONTROL **字母順序**] | 依字母順序對元件進行排序。 |
   | [!UICONTROL **分類**] | 排序類似於&#x200B;[!UICONTROL **建議**]&#x200B;的元件，只是計算量度和標準量度會分開分組，而非混合在一起。 |

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
   | 時間戳記 UTC | 事件發生日期和時間，以UTC時區表示。 支援次秒（微秒）粒度。 | 必填 | 未提供 |
   | 列 ID | 資料摘要中包含的每列的唯一識別碼。 | 必填 | 未提供 |
   | 工作階段 ID | 資料摘要中包含的每個工作階段的唯一識別碼。 | 必填 | 未提供 |
   | 人員 ID | 資料檢視和連線的個人識別碼 | 必填 | 可選標準 |
   | 帳戶ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 使用帳戶容器時的帳戶ID | 必填 | 可選標準 |

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

   +++ 無法納入資料摘要的量度

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
   | [!UICONTROL **頻率**] | 選取資料摘要的傳送頻率。 時間戳記屬於頻率視窗的事件會包含在資料摘要傳送中。 [!UICONTROL **回顧日期範圍**]&#x200B;及&#x200B;[!UICONTROL **處理延遲**]&#x200B;欄位也會影響哪些事件包含在您所選擇傳遞頻率的資料中。<p>對於即時摘要，選取此選項可包含一小時的資料量或一天的資料量。 對於回填摘要，此欄位已鎖定為&#x200B;**每日**，表示資料會分組為每日區塊。</p><ul><li>**每日**：摘要包含一整天的資料，從資料檢視時區的午夜到午夜。 <p>回填摘要需要此選項，而即時摘要則是選用選項。</p></li><li>**小時**：摘要包含一個小時的資料量。 <p>此選項僅適用於即時摘要。</p></li></ul> |
   | [!UICONTROL **回顧日期範圍**] | 控制 Customer Journey Analytics 在處理資料摘要傳送時回顧的時間範圍。 預設值為30天。<p>頻率時段 (小時或日) 會決定哪些事件包含在資料摘要中，而&#x200B;**回顧日期範圍**&#x200B;則提供正確分類這些事件所需的歷史情境。</p><p>細分資格篩選、維度持續性、工作階段計算和衍生欄位轉換都會影響包含的事件。</p> <p>在設定此選項之前，請參閱以下章節中說明的詳細資訊和範例，[瞭解回顧日期範圍](#understand-the-lookback-date-range)。</p> |
   | [!UICONTROL **處理延遲**] | 選擇在處理資料摘要檔案之前要等待的時間長度。 預設值為2小時。 在處理延遲期間傳入的任何延遲送達事件都會納入資料摘要中。 <p>處理延遲在很多方面都很實用，例如讓行動實施有機會讓離線裝置恢復連線並傳送資料，或配合您組織伺服器端管理先前處理之檔案的程序。 </p><p>工作階段必須在處理延遲截止時間之後開始，才能納入；在截止時間之前開始、並在處理延遲期間以內結束的工作階段則不會納入。</p><p>Customer Journey Analytics 會根據延遲送達事件通常花費多少時間傳送至您的摘要，動態判斷最佳延遲時間，但您也可以手動將延遲時間設定為 2、3、4 或 8 小時。</p> |
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
   | [!UICONTROL **完成時透過電子郵件通知**] | 指定一或多個電子郵件地址，在資料摘要成功傳送或無法傳送後，應傳送通知。 多個電子郵件地址必須以逗號分隔。 |
   | [!UICONTROL **啟用資訊清單**] | 選擇是否在每次傳送資料摘要時包含資訊清單檔案。 資訊清單檔案包含資料摘要中所包含每個檔案的資訊。 |

1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

## 了解回顧日期範圍 {#data-feed-lookback-date-range}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_lookback_date_range"
>title="回顧日期範圍"
>abstract="控制 Customer Journey Analytics 在處理每次傳遞時所回顧的時間範圍。<p>頻率時段 (小時或日) 會決定哪些事件包含在資料摘要中，而&#x200B;**回顧日期範圍**&#x200B;則提供正確分類這些事件所需的歷史情境。</p><p>細分資格篩選、維度持續性、工作階段計算和衍生欄位轉換都會影響包含的事件。</p><p>較長的回顧可提高準確性；較短的回顧則可提高效能。</p>"

<!-- markdownlint-enable MD034 -->

回顧日期範圍可控制Customer Journey Analytics在處理每個資料摘要傳遞時回顧的時間範圍。

事件仍必須有屬於頻率期間（小時或天）的時間戳記才能納入傳送中，但屬於&#x200B;**回顧日期範圍**&#x200B;的資料提供正確分類這些事件所需的歷史內容。

設定此選項時，請考量下列重要概念：

* 較長的回顧日期範圍通常可產生較準確的資料；較短的範圍則可產生較佳的傳送效能。
* 回顧日期範圍及頻率視窗的運作方式與Analysis Workspace報表日期範圍類似。 不過，有[主要差異](/help/components/exports/cja-data-feeds/df-comparison-workspace.md#differences)。 這些差異可能會導致Workspace報表與資料摘要傳送之間的資料差異。

處理回顧日期範圍內的資料時，會分別考慮區段資格、工作階段計算、維度持續性以及衍生欄位轉換：

### 細分資格篩選

將區段套用至您的資料摘要定義時，回顧日期範圍內的資料會決定哪些事件、工作階段或人員符合區段的資格。 區段的容器設定會決定範圍。 (可能的容器包括：「人員」、「工作階段」或「事件」。 B2B包括下列額外的容器：全域帳戶、帳戶、商機、購買群組。)

>[!BEGINSHADEBOX]

**範例：**

假設您要建立資料摘要，以瞭解屬於特定行銷活動（行銷活動B）之使用者行為。

若要完成此操作，請將區段套用至促銷活動B _中名為_&#x200B;使用者的資料摘要，以表示資料摘要中只應包含繫結至此區段中使用者的事件。

在此情況下，使用者必須同時符合&#x200B;**兩者**&#x200B;以下條件，才能納入資料摘要中：

* 使用者的事件時間戳記在資料摘要頻率視窗（資料摘要的指定小時或日期）內。
* 使用者在回顧日期範圍&#x200B;**內的某個時間符合&#x200B;_促銷活動B_區段**&#x200B;的資格。

  針對9天前發生的合格事件，這表示如果回顧日期範圍設定為30天，使用者&#x200B;**將會包含在資料摘要中**，但是如果回顧日期範圍設定為7天，使用者&#x200B;**將不會包含在資料摘要中**。

>[!ENDSHADEBOX]

### 工作階段計算

工作階段邊界是使用回顧日期範圍內的資料來計算。<!--Maybe this matters more regarding what the session ID is? Could it impact the Session ID? This could impact several factors, such as session-based persistence.-->

### Dimension持續性

當您在個別維度上設定持續性時，您也會設定到期時間，以決定維度專案在其設定的事件之後持續多久。

當資料檢視中的到期日設定為下列任一選項時，回顧日期範圍會影響維度持續性：

* [!UICONTROL **人員報告期間**]：回顧日期範圍會變成資料摘要定義中每個使用&#x200B;[!UICONTROL **人員報告期間**]&#x200B;作為到期日之維度的新報告期間。
* [!UICONTROL **自訂時間**]：如果選取的自訂時間超過回顧日期範圍，則會忽略自訂時間，而回顧日期範圍會用於資料摘要定義中每個使用&#x200B;[!UICONTROL **自訂時間**]&#x200B;作為到期日的維度的維度到期日。 系統不會考量回顧日期範圍之前發生的值。

  如需有關在資料檢視中設定維度的持續性的詳細資訊，請參閱[持續性元件設定](/help/data-views/component-settings/persistence.md)。

若要取得最準確的資料，請考慮將回顧日期範圍設為等於或大於資料中維度上設定的持續性的值。 但請記住，較短的回顧日期範圍可導致資料摘要傳送的效能提高。

>[!BEGINSHADEBOX]

**範例：**

假設您想要在您的資料摘要中，知道使用者在造訪您的網站前最初看到了哪些行銷活動。

若要完成此操作，請在「行銷活動」維度上設定持續性，並將「原始」作為配置模式。

在此情況下，只有當使用者同時符合&#x200B;**兩個**&#x200B;的下列條件時，原始行銷活動才會顯示在資料摘要輸出中：

* 使用者的事件時間戳記在資料摘要頻率視窗（資料摘要的指定小時或日期）內。

* 使用者在回顧日期範圍&#x200B;**內的某個時間符合原始行銷活動**&#x200B;的資格。

  如果使用者在9天前符合原始促銷活動的資格，則回顧日期範圍設為30天時，資料摘要會包含&#x200B;**原始促銷活動，但是如果回顧日期範圍設為7天，則資料摘要不會包含**&#x200B;原始促銷活動。****

>[!ENDSHADEBOX]

### 衍生欄位轉換

參考容器的任何衍生欄位函式會在資料摘要匯出中使用回顧日期範圍。 衍生欄位中有哪些日期功能？<!--Not sure how this applies.-->



