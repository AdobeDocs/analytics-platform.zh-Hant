---
title: 建立資料摘要
description: 了解如何建立資料摘要，以及需提供給 Adobe 的檔案資訊。
hide: true
feature: Components
autotag-review: '2026-05-19T08:45:44.870Z'
TQID: 'https://experienceleague.adobe.com/QgBD7vCkw4YA568XOLlwTnw8eZVZybXr3DFbM1ZKYDw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 0cc15e1c3dcbd8609a47954af8602ad617c67a51
workflow-type: tm+mt
source-wordcount: 2774
ht-degree: 28%

---

# 建立資料摘要

{{release-limited-testing}}

建立資料摘要時，您需要向 Adobe 提供：

* 關於原始資料檔案傳送目標的相關資訊

* 您要在每個檔案中包含的資料

* 傳送資料的頻率（包括擷取延遲送達點選的處理延遲）

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
>abstract="控制 Customer Journey Analytics 在處理資料摘要傳送時回顧的時間範圍。<br/>此設定不會更改頻率時段 (小時或日)。 不過，回顧日期範圍可能會影響傳送的資料。 細分資格篩選、工作階段計算、部分衍生欄位轉換和維度持續性，都會受到回顧日期範圍的影響。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_user-agent"
>title=""
>abstract="使用者代理程式資料和裝置查詢資料不得存在於相同的資料摘要設定中。"

<!-- markdownlint-enable MD034 -->

1. 使用您的 Adobe ID 認證登入 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。

1. 在介面右上方選取 [!UICONTROL **Customer Journey Analytics**] (透過應用程式切換器![應用程式](/help/assets/icons/Apps.svg))。

1. 在頂端導覽列中，前往&#x200B;[!UICONTROL **元件**] > [!UICONTROL **資料摘要**]。

1. 選取畫面右上角的&#x200B;[!UICONTROL **建立**]。

   或者，如果先前未建立任何資料摘要，請選取空白表格中的&#x200B;[!UICONTROL **建立資料摘要**]。

   會顯示包含以下索引標籤的頁面： [!UICONTROL **詳細資料**]、[!UICONTROL **資料結構**]&#x200B;和&#x200B;[!UICONTROL **傳遞**]。

   ![新資料摘要頁面](assets/data-feed-new.png)

1. 在&#x200B;[!UICONTROL **詳細資料**]&#x200B;標籤上，完成下列欄位：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **名稱**] | 資料摘要的名稱 名稱在選取的資料檢視中必須是唯一的，而且長度最多可為255個字元。<!--[Learn more](/help/export/analytics-data-feed/df-faq.md#must-feed-names-be-unique)--> |
   | [!UICONTROL **標記**] | 將任何標籤套用到資料摘要以方便分類。<!--You can filter on tags as described in [Filter and search the list of data feeds](/help/export/analytics-data-feed/df-manage-feeds.md#filter-and-search-the-list-of-data-feeds) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md).--> |
   | [!UICONTROL **說明**] | 指定資料摘要的說明。 編輯資料摘要時，會顯示您新增的說明。 |
   | [!UICONTROL **資料檢視**] | 選取包含您要匯出之資料的資料檢視。<p>選取資料檢視時，請考量下列事項：</p> <ul><li>如果相同資料檢視建立了多個資料摘要，則每個資料摘要都必須有不同的欄定義。</li><li>可用欄的清單取決於所選資料檢視所屬的登入公司。 如果您變更資料檢視，可用欄的清單可能會變更。 </li></ul> |

1. 選取&#x200B;[!UICONTROL **「下一步」**]。

1. 在&#x200B;[!UICONTROL **資料結構**]&#x200B;索引標籤上，確定在&#x200B;**[!UICONTROL 資料檢視]**&#x200B;欄位中選取了正確的資料檢視。

1. 在&#x200B;[!UICONTROL **區段**]&#x200B;下拉式功能表中，搜尋並選取任何區段以篩選摘要中包含的資料。

   套用多個區段時，它們會與AND運運算元連結。 （若要使用OR運運算元聯結區段，您必須先在區段產生器中建立新區段，然後將新區段套用至資料摘要。）

1. 將元件新增至資料摘要設定。 在左側欄中，找出您要包含的任何元件，然後將其拖曳至畫布以建置您的資料結構。 按住 **[!UICONTROL Shift]** 或按住 **[!UICONTROL Command]** (macOS 版) 或 **[!UICONTROL Ctrl]** (Windows 版)，即可選取多個元件。

   >[!NOTE]
   >
   >使用者代理程式資料和裝置查詢資料不得存在於相同的資料摘要設定中。 如果您嘗試新增衝突的元件，則會顯示錯誤。 如需詳細資訊，請參閱資料收集指南中[建立及設定資料串流](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/datastreams/configure)中的[設定裝置查詢](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/datastreams/configure#geolocation-device-lookup)。


   使用下列資訊來瞭解一律包含的維度、不可包含的維度以及必須替代的量度：

   +++ 資料摘要中一律包含的維度

   下列維度預設會包含在每個資料摘要中，且無法移除：

   | 維度名稱 | 附註 | 資料饋送 | 其他報告 |
   |---|---|---|---|
   | 時間戳記UTC | 事件發生日期和時間，以UTC時區表示。 支援次秒（微秒）粒度。 | 強制 | 未提供 |
   | 列ID | 資料摘要中包含之每一列的唯一識別碼。 | 強制 | 未提供 |
   | 工作階段ID | 資料摘要中包含之每個工作階段的唯一識別碼。 | 強制 | 未提供 |
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


1. 在&#x200B;[!UICONTROL **傳遞**]&#x200B;索引標籤上，指定下列資訊：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **摘要型別**] | 選取您要建立的摘要型別：<ul><li>[!UICONTROL **即時摘要**]：匯出目前和未來的資料。</li><li>[!UICONTROL **回填摘要**]：匯出兩個過去日期之間的歷史資料。</li></ul> |
   | [!UICONTROL **開始日期**] | 指定資料摘要的開始日期。 若要立即開始處理歷史資料的資料摘要，請確定已選取&#x200B;[!UICONTROL **回填摘要**]，然後將此日期設定為收集資料時的任何過去日期。 開始日期取決於資料檢視的時區。 |
   | [!UICONTROL **結束日期**] | 指定資料摘要的結束日期。 結束日期取決於資料檢視的時區。 |
   | [!UICONTROL **頻率**] | 選取資料摘要的傳送頻率。 時間戳記屬於頻率視窗的事件會包含在資料摘要傳送中。 [!UICONTROL **回顧日期範圍**]&#x200B;及&#x200B;[!UICONTROL **處理延遲**]&#x200B;欄位也會影響哪些事件包含在您所選擇傳遞頻率的資料中。<p>對於即時摘要，選取此選項可包含一小時的資料量或一天的資料量。 回填摘要必須為每日。</p><ul><li>**每日**：摘要包含一整天的資料，從資料檢視時區的午夜到午夜。 此選項可用於回填摘要或即時摘要。</li><li>**小時**：摘要包含一個小時的資料量。 對即時摘要使用此選項。</li></ul> |
   | [!UICONTROL **回顧日期範圍**] | 控制 Customer Journey Analytics 在處理資料摘要傳送時回顧的時間範圍。 <p>此設定不會改變頻率視窗（小時或天），其定義要包含在資料摘要輸出中的事件時間範圍。 不過，回顧日期範圍可能會透過下列方式影響傳送的資料： </p><ul><li>**區段資格**：將區段套用至您的資料摘要定義時，回顧日期範圍內的任何事件都會決定某人是否符合資格。 區段的容器設定會決定範圍。 (可能的容器包括：「人員」、「工作階段」或「事件」。 B2B有下列額外的容器：全域帳戶、帳戶、商機、購買群組。)  <p>例如，如果使用「人員」容器，且該人員在回顧日期範圍內符合資格，則其在頻率期間的所有事件也符合資格。</p></li><li>**工作階段計算**：工作階段範圍是使用回顧日期範圍內的資料計算。</li><li>**衍生欄位轉換**：參考容器的任何衍生欄位函式都會在資料摘要匯出中使用回顧日期範圍。</li><li>**Dimension持續性**：如果您選擇在個別維度上設定持續性，您也可選擇有效期限，以決定維度專案在其設定的事件之後持續多長時間。 <p>當資料檢視中的到期日設定為下列任一選項時，回顧日期範圍會影響維度持續性：</p><ul><li>對於資料摘要定義中每個使用&#x200B;[!UICONTROL **報告期間**]&#x200B;作為到期日的維度，回顧日期範圍都會變成新的報告期間。</li><li>對於資料摘要定義中以&#x200B;[!UICONTROL **自訂時間**]&#x200B;作為到期時間的每個維度，如果選取的自訂時間超過回顧日期範圍，則忽略自訂時間，並將回顧日期範圍用於維度到期日。<p>如需有關在資料檢視中設定維度的持續性的詳細資訊，請參閱[持續性元件設定](/help/data-views/component-settings/persistence.md)。</p></li></ul> |
   | [!UICONTROL **處理延遲**] | 選擇在處理資料摘要檔案之前要等待的時間長度。 在處理延遲期間傳入的任何延遲送達點選都會納入資料摘要中。 <p>處理延遲因各種原因而相當實用，例如讓行動實施有機會讓離線裝置上線並傳送資料，或是在管理先前處理的檔案時容納組織的伺服器端程式。 </p><p>您可以將摘要延遲2、3、4或8小時。<p>工作階段必須在處理延遲截止之後開始才能納入；在截止之前開始並在處理延遲內結束的工作階段不包括在內。</p> |
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


