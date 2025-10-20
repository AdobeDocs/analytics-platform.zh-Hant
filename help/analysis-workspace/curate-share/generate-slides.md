---
description: 瞭解如何從Workspace報表產生pptx格式的簡報。
keywords: Analysis Workspace
title: 從Workspace報表產生簡報
feature: Curate and Share
role: User
hide: true
hidefromtoc: true
source-git-commit: 9e23382800326440ed2a583e80029c9f27bb2494
workflow-type: tm+mt
source-wordcount: '1134'
ht-degree: 4%

---

# 資料storytelling：從Workspace報表產生投影片簡報 {#generate-powerpoint}

擁有[必要許可權](#permission-requirements-to-generate-slides)的使用者可以從Analysis Workspace專案自動產生.pptx簡報。 在產生這些投影片簡報時，Customer Journey Analytics會識別關鍵深入分析，並將其轉換為利害關係人就緒的投影片，自動從您的資料建立故事。

此功能可減少呈現Workspace專案中的發現專案所需的時間和精力，並可讓您快速建立主管敘述，並將業務影響傳達給利害關係人。

這個自動產生的資料故事可讓分析師專注於資料探索，而Customer Journey Analytics會組織分析人員的發現，並將其格式化為利害關係人消費的形式。

## 瞭解投影片簡報中的資料故事

Analysis Workspace使用創作AI在投影片簡報中建立資料故事。 這些資料故事提供額外情境、呈現重要焦點，並為後續步驟提供概念，以補充指定Workspace專案的分析。 指出隱藏的趨勢、異常、貢獻因素、關鍵驅動因素

### 資料內文提供的其他值

資料內文可透過以下方式補充指定Workspace專案的分析：

* 提供其他內容

* 強調重要深入分析

* 指出隱藏的趨勢、異常和其他因素

* 識別關鍵驅動因素

* 提出後續步驟的想法

### 塑造資料內文的專案元素

Analysis Workspace會考慮下列專案元素來建立資料內文：

* 維度間和量度間關係

* 構成分析基礎的個別元素：維度、量度、篩選器、自由表格結構、視覺效果和面板

* 為面板、表格和視覺效果指定的名稱

* 自由格式表格中的量度順序（用於決定優先順序）

* 摘要數字和摘要文字（用於決定需要在資料本文中反白顯示的量度）

### 資料劇本的簡報元素

資料內文包含執行摘要幻燈片、詳細投影片和區段分隔線。

**執行摘要：**&#x200B;優先處理最高價值的深入分析，並製作長度介於1到5個句子的整體故事。

**詳細投影片：**&#x200B;產生與Workspace專案中任何表格、面板或視覺效果相關的深入分析。 深入分析包括趨勢、季節性、異常和關聯。

**區段分隔線：**&#x200B;以適當放置和命名的區段分隔線來劃分深入分析。

## 根據Workspace專案產生.pptx簡報

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-powerpoint-include-visualizations"
>title="包含的面板和視覺效果"
>abstract="選擇要包含在簡報中的面板和視覺效果。 您最多可以包含50個視覺效果。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-presentation-emphasized-components"
>title="強調的元件"
>abstract="從您要在簡報中強調的視覺效果中選擇最多5個量度和5個維度。 您選擇的量度會以斜體顯示、維度會以粗體顯示，而維度專案則會以對比顏色顯示。"

<!-- markdownlint-enable MD034 -->

1. 移至包含您要用來作為投影片簡報基礎之資料的Workspace專案。

1. 選取頁面右上角的&#x200B;**[!UICONTROL 產生投影片]**。

   「產生幻燈片」對話方塊隨即顯示。

   ![產生幻燈片對話方塊](assets/generate-slides.png)

1. 註明下列資訊：

   | 選項 | 說明 |
   |---------|----------|
   | **[!UICONTROL 封面標題]** | 指定簡報的標題。 此標題會顯示在簡報的標題投影片上。 |
   | **[!UICONTROL 包含簡報者名稱]** | 指定簡報者的名稱。 此名稱會出現在簡報標題投影片上，位於封面標題下方。 |
   | **[!UICONTROL 要包含的面板和視覺效果]** | 選擇要包含在簡報中的面板和視覺效果。 您最多可以包含50個視覺效果。<p>支援大部分的面板和視覺效果。 如需有關不支援的面板和視覺效果的資訊，請參閱[不支援的專案元素和功能](#unsupported-project-elements-and-features)。</p> |
   | **[!UICONTROL 面板和視覺效果說明]** | |
   | **[!UICONTROL 註解]** | |
   | **[!UICONTROL 強調元件]** | 從您要在簡報中強調的視覺效果中選擇最多5個量度和5個維度。<p>未套用強調時，元件在簡報中顯示如下：<ul><li>**度量和維度：**&#x200B;斜體</li><li>**Dimension專案：**&#x200B;引號</li></ul></p><p>當套用強調時，元件在簡報中顯示如下：</p><ul><li>**量度和維度：**&#x200B;斜體與粗體</li><li>**Dimension專案：**&#x200B;強調對應維度時為粗體<p>在圖表中反白顯示維度專案時，也會將顏色套用至維度專案。</p></li></ul> |

1. （視條件而定）如果您想要以較少的步驟快速產生投影片，而且您的投影片簡報不需要公司佈景主題，請選取&#x200B;**[!UICONTROL 預設佈景主題]**。

   只要選取想要的顏色，即可選擇簡報的顏色主題。

   ![產生預設主題的投影片](assets/generate-slides-default-theme.png)

1. （視條件而定）如果您的投影片簡報需要符合公司主題，請選取&#x200B;**[!UICONTROL 上傳範本]**。 此選項需要您上傳自訂範本並套用自訂樣式。

   ![使用自訂範本產生投影片](assets/generate-slides-upload-template.png)

   若要上傳自訂範本，請執行下列其中一項操作：

   * （建議）下載空白範本並加以修改。

      1. 下載此空白範本。<!--add link-->

      1. 將自訂樣式套用至空白範本。

      1. 重新上傳範本而不變更任何主版面配置名稱。

   * 直接上傳自訂範本。

      1. 從您的檔案系統，將自訂範本拖曳至拖放區域。

         或

         選取「**[!UICONTROL 瀏覽]**」，然後瀏覽並從檔案系統中選取自訂範本。

         請確定上傳的檔案具有下列名稱的主版面配置： &quot;Title_Slide&quot;、&quot;Section_Divider&quot;、&quot;Title_Text&quot;、&quot;Title_Chart&quot;、&quot;Title_Two_Content_Mixed&quot;、&quot;Title_Three_Content_Mixed&quot;

         支援大小最大為25MB的.pptx和.potx檔案。

1. 選取&#x200B;**[!UICONTROL 匯出PPT]**。

1. （建議）檢閱並編輯.ppt簡報，並進行任何必要的變更，如下一節所述，[從先前產生的簡報編輯投影片](#edit-slides-from-a-previously-generated-presentation)。

## 從先前產生的簡報編輯投影片


## 下載產生的.pptx簡報



## 產生幻燈片的許可權需求

>[!AVAILABILITY]
>
>如果您的組織無權從Workspace專案產生投影片簡報，請聯絡您的Adobe客戶代表以瞭解更多授權的相關資訊。
>
>組織中擁有必要授權的所有使用者，預設都會啟用此功能。

如有需要，其組織擁有產生投影片授權的產品設定檔管理員可停用存取權。

在[!UICONTROL Adobe Admin Console]中，[!UICONTROL 報告工具] **[!UICONTROL 資料storytelling]**&#x200B;許可權會決定此功能的存取權。 如果[產品設定檔管理員](https://helpx.adobe.com/tw/enterprise/using/manage-product-profiles.html)想要停用存取權，必須遵循[!UICONTROL Admin Console]中的下列步驟：
1. 請前往「**[!UICONTROL Admin Console]** > **[!UICONTROL 產品與服務]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 產品設定檔]**」。
1. 選取您要為其提供[!UICONTROL 資料storytelling]存取權的產品設定檔標題。
1. 在特定的產品設定檔中，選取「**[!UICONTROL 權限]**」。
1. 選取「![編輯](/help/assets/icons/Edit.svg)」，可編輯「**[!UICONTROL 報告工具]**」。
1. 選取![AddCircle](/help/assets/icons/RemoveCircle.svg)以從&#x200B;**包含的許可權專案**&#x200B;移除&#x200B;**[!UICONTROL 資料storytelling]**。

   <!--add screenshot of permission in the admin console-->

1. 選取「**[!UICONTROL 儲存]**」，儲存權限。

如需詳細資訊，請參閱[存取控制](/help/technotes/access-control.md#user-level-access)中的[使用者層級存取](/help/technotes/access-control.md#access-control)。

## 不支援的專案元素和功能 {#unsupported}

產生幻燈片時，不支援專案中使用的下列Analysis Workspace元素和功能：

* 歸因面板

  當顯示組態選項時，此面板會以灰色顯示。

  所有其他面板可包含在從Workspace專案產生的幻燈片中。

* 部分視覺效果

  大部分的視覺效果都可包含在從Workspace專案產生的幻燈片中。 不過，下列視覺效果無法納入，並在顯示組態選項時顯示為灰色：

   * 同類群組表格

   * 歷程畫布

   * 項目符號

   * 組合

   * 散佈圖

   * 樹狀圖

* 劃分

* 引導分析


