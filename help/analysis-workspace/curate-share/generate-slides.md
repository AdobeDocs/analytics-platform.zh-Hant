---
description: 瞭解如何從Workspace報表產生pptx格式的簡報。
keywords: Analysis Workspace
title: 從Workspace報表產生簡報
feature: Curate and Share
role: User
hide: true
hidefromtoc: true
source-git-commit: 680799fdf18703acbd0569e25b41e6ecbc154d62
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 3%

---

# 資料storytelling：從Workspace報表產生投影片簡報 {#generate-powerpoint}

您可以從Analysis Workspace專案自動產生.pptx簡報。 產生簡報時，Customer Journey Analytics會自動識別關鍵深入分析，並將其轉換為利害關係人就緒的投影片。

此功能可減少呈現Workspace專案中的發現專案所需的時間和精力，並可讓您快速建立主管敘事並傳達業務影響。

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

1. 移至包含您要用來作為簡報基礎之資料的Workspace專案。

1. 選取頁面右上角的&#x200B;**[!UICONTROL 產生投影片]**。

1. 註明下列資訊：

   | 選項 | 說明 |
   |---------|----------|
   | **[!UICONTROL 封面標題]** | 指定簡報的標題。 此標題會顯示在簡報的標題投影片上。 |
   | **[!UICONTROL 包含簡報者名稱]** | 指定簡報者的名稱。 此名稱會出現在簡報標題投影片上，位於封面標題下方。 |
   | **[!UICONTROL 要包含的面板和視覺效果]** | 選擇要包含在簡報中的面板和視覺效果。 您最多可以包含50個視覺效果。<p>支援大部分的面板和視覺效果。 如需有關不支援的面板和視覺效果的資訊，請參閱[不支援的專案元素和功能](#unsupported-project-elements-and-features)。</p> |
   | **[!UICONTROL 面板和視覺效果說明]** | |
   | **[!UICONTROL 註解]** | |
   | **[!UICONTROL 強調元件]** | 從您要在簡報中強調的視覺效果中選擇最多5個量度和5個維度。<p>未套用強調時，元件在簡報中顯示如下：<ul><li>**度量和維度：**&#x200B;斜體</li><li>**Dimension專案：**&#x200B;引號</li></ul></p><p>當套用強調時，元件在簡報中顯示如下：</p><ul><li>**量度和維度：**&#x200B;斜體與粗體</li><li>**Dimension專案：**&#x200B;強調對應維度時為粗體<p>在圖表中反白顯示維度專案時，也會將顏色套用至維度專案。</p></li></ul> |

（視條件而定）如果您想要以預設主題產生投影片，請選取&#x200B;**[!UICONTROL 預設主題]**。

1. 選取要使用預設主題或上傳自訂範本：

   * **[!UICONTROL 預設佈景主題]**：

   * **[!UICONTROL 上傳範本]**：





## 從先前產生的簡報編輯投影片


## 下載產生的.pptx簡報

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


