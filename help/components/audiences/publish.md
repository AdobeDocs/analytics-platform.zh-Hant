---
title: 建立及發佈客群
description: 了解如何從 Customer Journey Analytics 發佈客群
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
feature: Audiences
role: User
source-git-commit: be062e350a8c1989be41aeb2774471a3fe1bf524
workflow-type: ht
source-wordcount: '2368'
ht-degree: 100%

---

# 建立及發佈客群 {#create-and-publish-audiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_audiences_refreshfrequency"
>title="重新整理頻率"
>abstract="查看重新評估對象會籍的頻率。<br/>一次性對象僅會評估一次。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_audiences_audiencelimit"
>title="對象限制"
>abstract="重新整理對象作業會受到其重新整理頻率的限制。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_audiences_refreshlookbackwindow"
>title="重新整理回顧期間"
>abstract="定義從評估對象的今天所開始的回顧天數。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_audiences_audiencesizelimit"
>title="客群規模限制"
>abstract="對象不得超過 2000 萬個會員。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_audiences_namespacesincluded"
>title="包含的命名空間"
>abstract="此對象中的身分識別是由以下命名空間組成的。"

<!-- markdownlint-enable MD034 -->




本主題說明如何將在 Customer Journey Analytics 中發現的客群建立並發佈到 Adobe Experience Platform 中的[即時客戶輪廓](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/profile/home)，以用於客戶目標選擇和個人化。

請閱讀此[概觀](/help/components/audiences/audiences-overview.md)，熟悉 Customer Journey Analytics 對象的概念。

## 建立及發佈客群 {#create}

1. 若要建立並發佈客群，請執行以下操作之一：

   | 建立方法 | 詳細資料 |
   | --- | --- |
   | 從&#x200B;**[!UICONTROL 客群]**&#x200B;介面內 | 從 Customer Journey Analytics 選單中，選取「**[!UICONTROL 元件]** > **[!UICONTROL 客群]**」。客群介面會顯示。選取「**[!UICONTROL 建立客群]**」，然後[!UICONTROL 客群產生器]會開啟。 |
   | 從 Analysis Workspace 中的視覺效果 | Analysis Workspace 中的許多視覺效果可讓您使用內容選單建立客群。例如，您可以從[自由格式表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)一個項目或[歷程畫布](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)一個節點的內容選單中選取「**[!UICONTROL 建立客群]**」。<p>使用此方法會以您選取的維度或維度項目，在客群產生器中預先填入區段。</p><p>以下視覺效果可讓您使用滑鼠右鍵功能表建立客群：</p><ul><li>[同類群組表格](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)</li><li>[流失](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)</li><li>[流量](/help/analysis-workspace/visualizations/c-flow/flow.md)</li><li>[自由格式表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)</li><li>[歷程畫布](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)</li><li>[文氏圖表](/help/analysis-workspace/visualizations/venn.md)</li></ul><p>**注意：** 客群不能包含計算量度。如果您嘗試建立包含計算量度的客群，則該計算量度不會包含在客群定義中。</p> |
   | 從區段建立/編輯使用者介面 | 勾選顯示「**[!UICONTROL 藉由此區段建立客群]**」的方塊。使用此方法預先填入區段。如需詳細資訊，請參閱[建立區段](/help/components/filters/create-filters.md)。 |

   {style="table-layout:auto"}

1. 使用[客群產生器](#audience-builder)建立客群。

1. 使用[日期預覽](#data-preview)面板解讀資料。

1. 選取「**[!UICONTROL [!UICONTROL 檢視範例 ID]]**」，可檢視此客群中的 ID 範例。在「**[!UICONTROL 樣本 ID]**」對話框中，您可以使用 ![搜尋](/help/assets/icons/Search.svg) [!UICONTROL *「搜尋範例 ID」*] 來搜尋範例 ID。

1. 仔細檢查您的對象組態，然後選取「**[!UICONTROL 發佈]**」。您會收到一封客群已發佈的確認訊息。發佈只需一兩分鐘，此客群就會出現在 Experience Platform 中。

1. 選取同一則訊息中的「**[!UICONTROL 在 AEP 中檢視客群]**」，您會被帶到 Adobe Experience Platform 中的「[區段 UI](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/segmentation/ui/overview)」。請參閱下方以了解更多資訊。

## 客群產生器

進行這些設定來定義或更新您的客群。

![建立一個顯示下一節所示設定的客群螢幕截圖。](assets/create-audience.png)

| 設定 | 說明 |
| --- | --- |
| ![資料](/help/assets/icons/Data.svg) | 選取用來建立客群的資料檢視。 |
| **[!UICONTROL 名稱]** | 客群名稱。例如， `Really Interested in Potential Car Buyers` |
| **[!UICONTROL 標記]** | 為組織目的而要指派給客群的任何標記。您可以選取一個或多個預先存在的標記，也可以輸入一個新標記。 |
| **[!UICONTROL 說明]** | 客群的說明，用來其他客群區分開來。例如， `Build an audience of really interested potential car buyers` |
| **[!UICONTROL 重新整理頻率]** | 您想要重新整理客群的頻率。<p/>您可在二者之間選擇： <ul><li>**[!UICONTROL 一次性]**&#x200B;客群：無需重新整理的客群 (預設)。例如，此選項可能適合用於特定一次性行銷活動。<br/>您必須指定&#x200B;**[!UICONTROL 一次性日期範圍]**。您可以使用![行事曆](/help/assets/icons/Calendar.svg)來輸入日期範圍。</li><li>重新整理客群。您可選取下列選項：<ul><li>**[!UICONTROL 每 4 小時]**：每 4 小時重新整理一次的客群。</li><li>**[!UICONTROL 每日]**：每日重新整理一次的客群</li><li>**[!UICONTROL 每週]**：每週重新整理一次的客群。</li><li>**[!UICONTROL 每月]**：每月重新整理一次的客群</li></ul></li>為了重新整理客群，您必須指定：<ul><li>**[!UICONTROL 重新整理回顧期間]**。定義從評估客群的今天所開始的回顧天數。您可以從選項中選取或定義自訂時間。最長 90 天。</li><li>**[!UICONTROL 到期日]**：定義客群停止重新整理的時間。您可以使用![行事曆](/help/assets/icons/Calendar.svg)來選取日期。預設到期日是從建立日期算起的 1 年後。到期客群與到期排程報告的處理方式類似。管理員會在客群到期前的一個月收到一封電子郵件。</li></ul> 請注意，客群重新整理次數限制為 75 到 150 次，具體取決於您的 Customer Journey Analytics 授權權利。</li></ul> |
| **[!UICONTROL 篩選器]** | 篩選條件是客群的主要輸入項目。將一個或多個區段從左側的 ![Segmentation](/help/assets/icons/Segmentation.svg) **[!UICONTROL 區段]**&#x200B;面板拖放至區段區域。您可以使用 ![Search](/help/assets/icons/Search.svg) [!UICONTROL *搜尋區段*]&#x200B;來搜尋區段。您可以新增最多 20 個區段。區段可以使用 **[!UICONTROL And]** 或 **[!UICONTROL Or]** 等運算子來連接。<p>從 Analysis Workspace 中的視覺效果 (例如自由格式表格或歷程畫布) 建立客群時，套用於面板或資料欄的任何區段都會保留。您可以移除任何自動套用的區段。</p> |
| **[!UICONTROL 資料預覽]** | 選取「![資訊](/help/assets/icons/Info.svg)」以顯示或隱藏所選日期範圍的[資料預覽](#data-preview)。 |

## 資料預覽

資料預覽面板提供以下資訊。

| 元素 | 說明 |
| --- | --- |
| **[!UICONTROL 總人數]** | 此客群中總人數的摘要數字。最大規模為 2000 萬人。如果您的客群超過 2 千萬人，您必須減少客群規模後才能發佈。 |
| **[!UICONTROL 客群規模限制]** | 視覺效果可顯示此客群距離 2000 萬人限制還差多少。 |
| **[!UICONTROL 預估的客群回訪]** | 您可以使用此值重新定位此客群中返回您的網站、行動應用程式或其他頻道的使用者。<p>您可以選取可能回訪的估計客戶數量的時間範圍 (**[!UICONTROL 接下來 7 天]**、**[!UICONTROL 接下來 2 週]**&#x200B;或&#x200B;**[!UICONTROL 下個月]**)。 |
| **[!UICONTROL 預估回訪]** | 此數字可提供在您所選時間範圍內的回訪客戶估計數量。這是使用歷史流失率為此客群預測的數字。 |
| **[!UICONTROL 預覽量度]** | 您可以選取一個特定量度，了解該量度的資料如何根據您定義的客群來計算。每個預覽量度都會根據客群顯示該量度的總數。還有，是以客群為主的量度佔整體量度總數 (如資料檢視的定義) 的百分比。例如，381 人 (您選取的量度) 是根據您客群定義的結果，佔資料檢視中可用總人數的 5%。您可以選取資料檢視中可用的任何量度。 |
| **[!UICONTROL 包含的命名空間]** | 與客群中的個人相關聯的特定命名空間。範例包括 ECID、CRM ID、電子郵件地址等。 |
| **[!UICONTROL 沙箱]** | 此客群所在的 [Experience Platform 沙箱](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sandbox/home)。當您將此客群佈到 Platform 時，您只能在此沙箱的範圍內使用客群。 |

{style="table-layout:auto"}

## 客群建立和發佈後會如何？ {#after-audience-created}

在 Customer Journey Analytics 中建立並發佈客群後，在 Experience Platform 中即可使用該客群，且能於 [Audience Portal](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/segmentation/ui/audience-portal) 內檢視。由於在 Experience Platform 中可以使用客群，所以在其他 Experience Platform 應用程式 (例如 Adobe Journey Optimizer) 也可以使用客群。

唯有您的組織完成串流區段相關設定，才會建立 Adobe Experience Platform 串流區段。

在處理從 Customer Journey Analytics 發佈至 Experience Platform 的客群時，請考慮以下事項：

* Experience Platform 中的客群與 Customer Journey Analytics 客群共用相同的名稱和描述。該名稱附有 Customer Journey Analytics 客群 ID，可確保客群的獨特性。
* 在 Customer Journey Analytics 中對客群名稱或描述所做的任何變更都會反映在 Experience Platform 中。
* 如果在 Customer Journey Analytics 中刪除一個客群，則該客群仍可在 Experience Platform 中繼續使用，直到該客群的設定檔會籍到期為止。若是一次性客群，設定檔會籍將在 420 天後到期；若是定期客群，設定檔會籍將在 16 天後到期。

## 延遲的注意事項 {#latency}

在客群發布前後及期間的幾個時間點，可能會出現延遲。 以下是可能的延遲的概觀。

![本節所述的客群發佈的延遲。](assets/latency-diagram.svg)

|  | 延遲點 | 延遲期間 |
| --- | --- | --- |
| 未顯示 | Adobe Analytics 至 Analytics 來源連接器 (A4T) | 最多需 30 分鐘 |
| 1 | 資料攝取至資料湖 (來自 Analytics 來源連接器或其他來源) | 最多需 90 分鐘 |
| 2 | 從 Experience Platform Data Lake 將資料攝取至 Customer Journey Analytics | 最多需 90 分鐘 |
| 3 | 客群發佈至即時客戶輪廓，包括自動建立串流細分群體並允許該細分群體準備接收資料。 | 幾秒 |
| 4 | 客群的更新頻率 | <ul><li>一次性重新整理 (延遲時間小於 5 分鐘)</li><li>每 4 小時、每天、每週、每月重新整理一次 (延遲與重新整理頻率息息相關) |
| 5 | 在 Adobe Experience Platform 中建立目標：啟動新區段 | 1-2 小時 |

{style="table-layout:auto"}

## 在 Experience Platform 中使用 Customer Journey Analytics 客群 {#audiences-aep}

Customer Journey Analytics 現在會從您發佈的客群中取得所有命名空間和 ID 組合，並將其串流傳送至 Real-Time Customer Data Platform。Customer Journey Analytics 會將客群傳送到有主要身分設定的 Experience Platform；這是根據設定連線時選取作為[!UICONTROL 個人 ID] 的身分設定。

接著 Real-Time Customer Data Platform 會檢查每個命名空間/ID 組合，並尋找它可能屬於的個人檔案。設定檔基本上是一組連結的命名空間、ID 和裝置。如果找到個人檔案，則會將命名空間和 ID 新增到此個人檔案中的其他 ID，做為區段會籍屬性。例如，現在在所有裝置和頻道都可以 <user@adobe.com> 為目標。如果找不到設定檔，則會建立一個新的。

若要在 Platform 中檢視 Customer Journey Analytics 客群：

1. 擴展左側面板中的「**[!UICONTROL 客戶]**」，然後選取「**[!UICONTROL 客群]**」。<!-- is there a folder called "Customer Journey Analytics? -->

1. 選取「**[!UICONTROL 瀏覽]**」索引標籤。

1. 若要找到您從 Customer Journey Analytics 發佈的客群，請執行以下操作之一：

   ![左側面板中的客群選項](assets/aep-audiences.png)

   * 依「**[!UICONTROL 來源]**」資料欄為表格排序，以便檢視顯示 [!UICONTROL **Customer Journey Analytics**] 為來源的客群。

   * ![篩選器](/help/assets/icons/Filter.svg) 對「**[!UICONTROL 來源]**」進行篩選並選取 **[!UICONTROL Customer Journey Analytics]**。

   * 使用「![搜尋](/help/assets/icons/Search.svg)」來搜尋欄位。

有關在 Platform 中使用客群的更多資訊，請參閱 Experience Platform 文件中「[客戶細分工具使用者介面指南](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/segmentation/ui/segment-builder)」的「[客群](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/segmentation/ui/segment-builder)」部分。

### 了解客群計數差異

Customer Journey Analytics 和 Real-Time Customer Data Platform 之間可能會出現客群計數差異。

<!--
![Infographic on audience differences between Customer Journey Analytics and Real-Time CDP.](/help/components/audiences/assets/infographic-cja-rtcdp.png)
-->

#### 預估計數與確定計數

兩個應用程式計算客群會籍數量的方法有所不同，如下所述。

* **Customer Journey Analytics**：Customer Journey Analytics 中的&#x200B;**[!UICONTROL 總人數]**&#x200B;是一個預估值。這表示計數是根據客群規則進行的預估值，並且在重新整理間隔之間可能會有所變更。
* **Real-Time Customer Data Platform**：Real-Time Customer Data Platform 中的計數是確定的，以每日的評估工作為基礎，並固定為客群完成向客群入口網站發佈的時間點。

#### 發佈間隔和速率

客群以 1500 筆記錄/每秒 (RPS) 的速率發佈至 Real-Time Customer Data Platform。例如，擁有 2000 萬會員的客群大約需要 3.7 小時才能完全發佈完畢 (20M / 1500 RPS / 每小時 3600 秒)。於此情況下，兩個應用程式的客群會籍數量可能會有所不同。

#### 輪廓片段化

從 Customer Journey Analytics 匯入的輪廓若已存在於 Real-Time Customer Data Platform 中，則不會計為新輪廓。這可能導致 Real-Time Customer Data Platform 中的輪廓計數低於預期。

#### 批次客群與串流客群

Customer Journey Analytics 客群不包括在每日批量評估工作中，並且會維持不變，直到下一個發佈間隔。相對地，Real-Time Customer Data Platform 中的其他批次客群每 24 小時便會重新評估一次。

### 應記住的關鍵重點

* **Customer Journey Analytics 中的預估計數**：了解 Customer Journey Analytics 中的&#x200B;**[!UICONTROL 總人數]**&#x200B;計數為預估值，且可能因串流資料和身分行為而有所不同。
* **Real-Time Customer Data Platform 中的確定計數**：Real-Time Customer Data Platform 中的計數是固定的，直到下一個發佈間隔才會變更。
* **輪廓片段化**：應注意，從 Customer Journey Analytics 匯入時，Real-Time Customer Data Platform 中的現有輪廓可能不會計入新的輪廓計數。

明確區別這些方面的差異後，您便能更加了解 Customer Journey Analytics 和 Real-Time Customer Data Platform 兩者間的客群資料，並達到更好的管理。--->

## 常見問題 {#faq}

客群發佈的常見問題。

+++**如果使用者不再是 Customer Journey Analytics 中的客群成員，會如何？**

發生這種情況時，會從 Customer Journey Analytics 傳送退出事件到 Experience Platform。

+++

+++**如果您在 Customer Journey Analytics 中刪除客群，會如何？**

刪除 Customer Journey Analytics 客群後，該客群將不會再顯示於 Experience Platform UI 中。然而，在 Platform 中與該客群相關聯的設定檔不會被刪除。

+++

+++**如果 Real-Time Customer Data Platform 中不存在相應的設定檔，新設定檔是否會建立？**

是，會建立。

+++

+++**Customer Journey Analytics 是否會以管道事件或以也會前往資料湖的平面檔案形式傳送客群資料？**

Customer Journey Analytics 會透過管道將資料串流至 Real-Time Customer Data Platform，並且這類資料也會被收集到資料湖中的系統資料集中。

+++

+++**Customer Journey Analytics 會傳送哪些身分識別？**

在[連線設定](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-connections/create-connection)中指定的任何身分識別/命名空間組。具體而言，就是使用者選取要作為「個人 ID」之欄位時的步驟。

+++

+++**選擇哪個 ID 作為主要身分識別？**

請參閱上述內容。每位 Customer Journey Analytics 個人僅會傳送一個身分識別。

+++

+++**Real-Time Customer Data Platform 是否也會處理 Customer Journey Analytics 訊息？Customer Journey Analytics 是否可透過客群共用將身分識別新增至設定檔身分識別圖？**

否。每個人只傳送一個身份識別，因此 Real-Time Customer Data Platform 將沒有圖形邊可供使用。

+++

+++**每日、每周和每月的重新整理會在一天中的什麼時間發生？每週重新整理會在一週的哪一天會進行？**

重新整理的時間取決於原始客群的發佈時間，並錨定在一天中的哪個時間 (以及一週中的某天或一個月中的某天)。

+++

+++**您可以設定每天、每週、每月的重新整理時間嗎？**

不可以，使用者無法設定重新整理時間。

+++


## 後續步驟

* 若要管理此客群，請前往[「管理 UI」](/help/components/audiences/manage.md)。
