---
title: Customer Journey Analytics B2B edition概念和功能
description: Customer Journey Analytics B2B edition的概念和功能。
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: df2cc922-d214-49b9-8fdb-443cc1dac05b
source-git-commit: 3c13ae26a9ef48454467fc21b8faaa9e078c7f9f
workflow-type: tm+mt
source-wordcount: '1470'
ht-degree: 2%

---


# B2B edition概念和功能

本文說明在Customer Journey Analytics中常用的連線、識別碼、容器和資料集等概念。 以及Customer Journey Analytics B2B edition如何在這些概念中新增其他功能。


## 連線和識別碼

在Customer Journey Analytics中，您會挑選通用識別碼（稱為人員ID），將事件資料與其他資料集連線，例如設定檔資料集和查詢資料集。 這種型別的連線稱為以人為本的連線，有助於進行以人為本的報表和分析。

在Customer Journey Analytics B2B edition中，您可以在以人員為基礎的連線或帳戶為基礎的連線之間選取。 以帳戶為基礎的連線有助於以帳戶為基礎的報表和分析。

* 針對以人員為基礎的連線，您選取「人員」作為主要識別碼。 然後您可以設定並設定連線、資料檢視和工作區專案，以製作以人物為基礎的報表。
* 對於以帳戶為基礎的連線，您可以選取「帳戶」作為主要識別碼。 然後，您可以選擇性地為「全域帳戶」、「購買群組」和「商機」新增額外的容器。 根據您是否新增全域帳戶，您的主要識別碼是帳戶識別碼或全域帳戶識別碼。


## 容器

在Customer Journey Analytics中，容器是在連線和資料檢視的設定過程中產生，並提供資料結構和範圍。 容器儲存識別碼群組，以依據唯一識別碼排序所有事件時間戳記。 該儲存空間有助於快速且高效執行分段、歸因和視覺效果等功能。

### 標準容器

Customer Journey Analytics是圍繞三個容器的概念所建置：人員、工作階段和事件。 在設定期間，會以隱含方式產生這些容器。

當您設定資料檢視時，可以重新定義這些容器的命名方式，但容器之間的階層與關係是預先確定的。 工作階段容器是根據您在資料檢視中的[工作階段設定](/help/data-views/session-settings.md)中定義工作階段的方式而產生。

![B2C](assets/b2c-containers.svg){zoomable="yes"}


### B2B 容器

在Customer Journey Analytics B2B edition中，帳戶容器會新增至產生的容器清單中。 您可以選擇設定產生其他容器，例如「全域帳戶」、「購買群組」和「商機」。

容器之間的階層與關係是預先設定的。 商機、購買群組及人員都是帳戶容器的同層級容器。 在該階層中，會根據您在資料檢視中的[工作階段設定](/help/data-views/session-settings.md)中定義工作階段的方式，產生「人員」容器和「事件」容器之間的工作階段容器。 目前不產生和支援其他工作階段容器，例如帳戶容器和事件容器之間的容器。 如需B2B容器的說明和基本用法，請參閱下表。

![B2B](assets/b2b-containers.svg){zoomable="yes"}

| B2B容器 | 說明<br/>基本使用案例 |
|---|---|
| 帳戶 | 屬於您企業的客戶或潛在客戶的公司。 公司可以是大型組織的子公司或部門。 帳戶代表您銷售的目標組織，且您要在該組織層次追蹤。 |
| 全域帳戶（選擇性） | 一組關聯公司的頂級母公司。 全域帳戶沒有母公司，但可能有屬於全域帳戶的子公司或部門。 當您在連線中設定了「全域帳戶」容器時，沒有父系或子系的帳戶應同時列在「帳戶」欄位和「全域帳戶」欄位中。 |
| 機會（選擇性） | 一起銷售的產品和服務集合。 在銷售週期中，銷售機會通常涉及不同的階段，直到銷售結束為止。<br>您會使用資料來測量透過銷售漏斗的商機進展。 例如，提供從階段3移至階段4之熱門商機詳細資訊的報表。 |
| 購買群組（選擇性） | 組織內參與決策流程以購買產品或服務的人員集合。 <br/>您可以使用購買群組資料，透過行銷活動管理追蹤購買群組。 例如，建立主要購買群組的對象區段。<br/>您最可能想要從購買群組查詢個人資料，以便報告購買群組中的人員。 |
| 個人 | 個人，通常由與公司互動的唯一電子郵件地址識別。 <br/>您可以使用設定檔資料來識別帳戶員工。 例如：將目標鎖定在已註冊會議的帳戶中的所有人員。 |

>[!IMPORTANT]
>
>* 若您在以帳戶為基礎的連線中&#x200B;**已啟用**&#x200B;全域帳戶容器，則事件資料集中的每筆記錄都應包含帳戶ID和全域帳戶ID。 如果沒有，則會略過記錄。
>* 如果您&#x200B;**未啟用**&#x200B;以帳戶為基礎的連線中的全域帳戶容器，則事件資料集中的每筆記錄都應包含帳戶ID。 如果沒有，則會略過記錄。

您可以在Analysis Workspace中，針對特定B2B功能使用B2B容器：

* **區段**： [B2B區段容器](/help/components/segments/seg-overview.md#b2b-containers)可讓您建立其容器範圍超出人員、工作階段或事件的區段。 例如：具有事件登記節段的科目，或具有購買群組與階段5商機節段的美國科目。

  >[!NOTE]
  >
  >Customer Journey Analytics B2B edition中以帳戶為基礎設定的B2B事件資料，可能包含不含個人或工作階段的資料列。 例如：詳細說明商機階段進展的資料列。 評估區段時，請記住，人員和工作階段可能不再是正確的標準。
  >

* **歸因**：您可以在[歸因面板](/help/analysis-workspace/c-panels/attribution.md)、[歸因元件設定](/help/data-views/component-settings/attribution.md)、[計算量度](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md)或自由表格](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)中的[欄中使用新的B2B容器。 帳戶回顧期間延長至13個月。

* **視覺效果**： [流失](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)、[流量](/help/analysis-workspace/visualizations/c-flow/flow.md)、[歷程畫布](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)和[同類群組表格](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)視覺效果支援新的B2B容器。 例如：您可以使用新的容器來瞭解購買群組如何耗用內容，或機會同類群組如何接近銷售結尾。
您也可以在[使用者偏好設定](/help/analysis-workspace/user-preferences.md#visualizations-preferences)中設定這些視覺效果的預設容器。

區段、歸因和視覺效果以及B2B容器可支援您進行深入的B2B分析和深入分析。


## 資料集

Customer Journey Analytics B2B會區分下列資料型別和資料集。

| 資料類型 | 時間序列 | 容器記錄 | 欄位記錄 |
|---|---|---|---|
| **資料集** | **事件資料集**<br/>&#x200B;例如：<ul><li>數位分析</li><li>CRM事件</li><li>面對面活動</li><li>呼叫中心資料</li></ul> | **設定檔資料集**<br/>&#x200B;例如：<ul><li>CRM記錄</li><li>AJO B2B記錄</li><li>CDP記錄</li><ul> | **類別**<br/>&#x200B;例如：<ul><li>行銷活動記錄</li><li>行銷清單記錄</li><li>內容中繼資料</li><li>產品記錄</li></ul> |
| 要求 | **時間戳記**<br>&#x200B;每個記錄都需要：<ul><li>帳戶 ID</li><li>全域帳戶 ID</li><li>人員 ID</li></ul> | **帳戶ID**<br>&#x200B;記錄需要容器ID，例如：<ul><li>帳戶</li><li>個人</li><li>機會</li><li>購買群組</li></ul> | **相符的索引鍵**<br>&#x200B;記錄需要包含在容器或事件資料集中的識別碼，例如：<ul><li>行銷活動 ID</li><li>內容 ID</li><li>產品 ID</li></ul> |

{style="table-layout:fixed"}

Customer Journey Analytics B2B edition中以帳戶為基礎的連線範例：

![以帳戶為基礎的連線範例](assets/b2b-datasets.svg)

Customer Journey Analytics B2B edition提供[連線圖](/help/connections/create-connection.md#connection-map)介面，讓您概略瞭解連線中資料集之間的關係。


與Customer Journey Analytics類似，事件型時間序列資料是Customer Journey Analytics B2B edition的核心。 帳戶型連線的主要差異在於，您事件資料集中的每個記錄都需要一個帳戶ID，而不是人員ID。

當您在Customer Journey Analytics B2B edition中為帳戶型連線設定[資料集設定](/help/connections/create-connection.md#dataset-settings)時，部分設定可用的選項取決於[資料集型別](/help/connections/create-connection.md#dataset-types)。 例如，您必須：

* 為您為事件資料集設定的每個容器指定識別碼。
* 為您的設定檔資料集定義帳戶欄位或全域帳戶欄位。
* 為查詢資料集定義索引鍵以及如何比對這些索引鍵（依欄位容器）。

## 依容器或欄位比對

您可以為每個查詢資料集定義，不論您是依欄位或容器比對資料集。

### 依容器比對

如果記錄資料集依容器使用相符專案，系統會將記錄資料集視為設定檔資料集型別，並在使用者介面中將其視為設定檔資料集。 在包含容器記錄並支援您設定之容器的資料集上使用依容器比對。 例如，「購買群組」資料集。

### 依欄位比對

如果記錄資料集使用依欄位比對，系統會將記錄資料集視為查詢資料集型別，並在使用者介面中視為查詢資料集。 在包含透過查詢的其他分類詳細資料的資料集上使用依欄位比對。 例如，「行銷清單成員」資料集或「產品詳細資訊」資料集。


## 以個人和帳戶為基礎的資料報表

如果您想要報告以人員為基礎的容器（和人員身分）和以帳戶為基礎的容器（和帳戶身分），您應在Customer Journey Analytics中設定兩個個別的連線。 一個是您選取「人員」作為主要ID的連線，另一個是您選取「帳戶」作為主要ID的連線。 Customer Journey Analytics不支援來自單一容器階層的個人型和帳戶型報表。

