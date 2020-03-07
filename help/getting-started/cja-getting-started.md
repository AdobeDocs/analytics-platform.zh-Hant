---
title: 客戶歷程分析快速入門
description: 客戶歷程分析快速入門。
translation-type: tm+mt
source-git-commit: 1aebe79040b6c8b9eb8a336e158f5ce6d2ea16a4

---


# 客戶歷程分析快速入門

若要實作客戶歷程分析，您必須遵循此工作流程。 有些初始工作是在Adobe Experience Platform中執行，有些則在客戶歷程分析中執行。

## 必備條件

客戶歷程分析適用於

* Adobe Analytics [Select、Prime或Ultimate客戶](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html)
* 已針對 [Adobe Experience Platform布建](https://www.adobe.com/experience-platform.html)
* 已購買客戶歷程分析SKU

## 工作流程

| 任務 | 其中 執行 | 詳細資料 |
|---|---|---|
| **步驟1:準備您的資料結構** | Adobe Experience Platform | 使用 [Adobe Experience Data Model(XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) ，標準化客戶體驗資料並定義客戶體驗管理的架構。 |
| **步驟2:根據模式建立資料集** | Adobe Experience Platform | Platform中的資料由資料集組成，例如電子郵件資料集、CRM資料集、POS資料集、Adobe Analytics資料集等。 每個資料集都由模式和批資料組成。 您可以在Experience Platform中建 [立資料集](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md)。<br>雖然可匯入客戶歷程分析的資料集架構是有彈性的，但它必須符合一些基本規則。 最好先確定您的資料符合這些要求，再將其上傳至平台。 （請注意，結構同時包含量度和維度。）<br>有三種資料類型與客戶歷程分析相容：<ul><li>**事件資料**:代表及時事件的資料（例如，網站瀏覽、互動、交易、POS資料、調查資料、廣告曝光資料等）。 這是典型的點按流資料，包含客戶ID或Cookie ID，以及時間戳記。 透過事件資料，我們允許您使用任何您想要的ID。</li><li>**查閱資料**:此資料用於查閱在「事件」或「描述檔」資料中找到的值或索引鍵。 例如，您可以上傳將事件資料中的數值ID對應至產品名稱的查閱資料。</li><li>**描述檔資料**:在「事件」資料中套用至訪客、使用者或客戶的資料。 例如，可讓您上傳有關客戶的CRM資料。</li></ul> |
| **步驟3：建立平台資料集和客戶歷程分析之間的連線** | 客戶歷程分析 | 請參 [閱建立連接](/help/connections/create-connection.md)。 |
| **步驟4:建立資料檢視** | 客戶歷程分析 | See [Create a data view](/help/data-views/create-dataview.md). |
| **步驟5:在工作區中報告跨通道資料** | 客戶歷程分析 | 請參 [閱執行基本分析](/help/projects/perform-basic-analysis.md)[和執行進階分析](/help/projects/perform-adv-analysis.md)。 |

## 準備您的資料結構

[使用架構編輯器建立架構](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)


