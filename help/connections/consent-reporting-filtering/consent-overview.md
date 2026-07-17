---
title: 同意報表和篩選概觀
description: 瞭解如何在Customer Journey Analytics中報告訪客同意原則成員資格，並在擷取時篩選非同意的訪客。
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 91cd8d3d5c290f52e4ae15713693be1fc83baa92
workflow-type: tm+mt
source-wordcount: 1058
ht-degree: 2%

---

# 同意報表和篩選概觀

同意報表和篩選會使用儲存在Adobe Experience Platform設定檔資料集中的同意原則成員資格資料，協助您報告訪客同意，並可選擇在未經同意的訪客資料內嵌至Customer Journey Analytics之前將其排除。

## 先決條件

在設定同意報告和篩選之前，請確定：

* 您的組織已授權Adobe Healthcare Shield或Privacy &amp; Security Shield。
* 您在Customer Journey Analytics中擁有系統管理員許可權。
* 您要使用的沙箱包含設定檔資料集，其中的`consentPoliciesIDMap`欄位中有同意原則成員資格資料。
* 您要設定的連線已經存在。 如需詳細資訊，請參閱[建立或編輯連線](/help/connections/create-connection.md)。

下圖和相關表格高階呈現同意報告和篩選如何在Analysis Workspace中使用同意原則資料，以及篩選內嵌時的訪客資料：

![同意報告和篩選概觀](assets/consent-overview.png)

| 數字 | 功能 | 函數 |
|---------|----------|---------|
| 1 | 同意報告和篩選設定 | Customer Journey Analytics中的設定介面用於啟用同意報告及（選擇性）同意篩選。 |
| 2 | 沙箱 | 必須包含包含您要報告的同意原則成員資格資料的設定檔資料集。 |
| 3 | 輪廓資料集 | 包括每位訪客的同意原則成員資格資料。 同意原則會籍儲存在設定檔資料集的`consentPoliciesIDMap`欄位中。 此設定檔資料集已新增至您選取的連線。 <p>每位訪客的個人資料都會列出訪客相符的同意原則。 Customer Journey Analytics會讀取此欄位，讓同意政策可用於報告，並評估在擷取期間要包含哪些訪客。</p> |
| 4 | 同意原則查詢資料集 | 提供好記的原則名稱和報表說明。 系統會自動建立查詢資料集，並與Experience Platform保持同步。 每個沙箱最多存在一個同意原則查詢資料集。 |
| 5 | 連線 | 套用同意報告和篩選的連線。 連線下的所有資料檢視都會繼承設定。 |
| 6 | 同意原則元件 | 代表同意原則成員資格的新維度、量度和衍生欄位。 這些元件會自動建立，並可在Analysis Workspace中用於製作報表。 |
| 7 | 擷取時間篩選 | 啟用篩選時，系統會根據您設定的行銷動作，在擷取期間排除非同意的訪客。 |

## 同意報告與篩選

同意報告和篩選是兩項不同的功能。 您可以自行啟用同意報告，或同時啟用報告和篩選。

### 同意報告

當您啟用同意報告時，Customer Journey Analytics會在設定的連線下將一組同意原則元件新增至資料檢視。 這些元件可讓您使用Analysis Workspace，透過Experience Platform設定檔資料集中的同意原則成員資格資料，報告哪些訪客符合各種同意原則。

為了保持報表可讀性，Customer Journey Analytics會將Experience Platform中的原則名稱和說明同步至同意原則查詢資料集。 在Experience Platform中建立、更新、重新命名或刪除原則時，查詢資料集會自動更新。

如需同意報告所建立之元件的相關資訊，請參閱[分析同意原則資料](/help/connections/consent-reporting-filtering/consent-analyze.md)。

### 同意篩選

>[!IMPORTANT]
>
>篩選掉（已排除）的同意資料不會儲存在Customer Journey Analytics中，且無法透過更新設定針對過去的日期復原。

當您啟用同意篩選時，Customer Journey Analytics會在擷取時排除非同意的訪客。 由於篩選會在擷取時進行，因此排除的訪客資料永遠不會進入Customer Journey Analytics，因此無法用於報表。

使用同意篩選時，請考慮下列事項：

* Customer Journey Analytics會決定套用至您設定之行銷動作的同意政策。

  行銷動作代表資料使用的類別。 Customer Journey Analytics會決定哪些同意原則適用於每個行銷動作，而且您在[建立您的設定](/help/connections/consent-reporting-filtering/consent-configure.md#create-a-configuration)時，會個別啟用每個行銷動作的篩選功能。

  | 行銷動作 | 說明 |
  |---------|----------|
  | **[!UICONTROL Analytics]** | Analysis Workspace中的標準Customer Journey Analytics報表。 |
  | **[!UICONTROL 資料科學]** | 進階分析、機器學習和資料科學使用案例。 |

* 只有當訪客符合&#x200B;**所有**&#x200B;適用的同意原則時，才會擷取訪客的資料。 如果訪客缺少任何適用的原則，則會排除該訪客的資料。

## 設定同意報告和篩選

當您設定同意報表和篩選時，請選取包含您同意原則成員資格資料的沙箱和設定檔資料集，選擇要設定的連線或連線，並選擇是否篩選每個行銷動作的資料。 Customer Journey Analytics接著會自動建立同意原則查詢資料集和同意原則元件。

如需詳細資訊，請參閱[設定同意報告和篩選](/help/connections/consent-reporting-filtering/consent-configure.md)。

## 管理同意報告和篩選設定

您可以在設定建立後管理同意報表和篩選設定。 您可以檢視、編輯和刪除組態。

如需有關管理現有設定的資訊，請參閱[管理同意報告和篩選設定](/help/connections/consent-reporting-filtering/consent-manage.md)。

## 分析同意原則資料

有了Customer Journey Analytics提供的同意原則資料，您可以報告哪些訪客符合哪些同意原則，並使用該insight來瞭解您報告中的同意對象。

如需詳細資訊，請參閱[分析同意原則資料](/help/connections/consent-reporting-filtering/consent-analyze.md)。

## 同意報告及篩選角色和許可權需求

同意報表和篩選需要下列Customer Journey Analytics角色和Experience Platform許可權：

| 功能 | Customer Journey Analytics角色或許可權需求 | Experience Platform許可權需求 |
|---------|----------|----------|
| [建立同意報告和篩選設定](/help/connections/consent-reporting-filtering/consent-configure.md) | 系統管理員 | <ul><li>資料集：讀取、寫入</li><li>結構描述：讀取、寫入</li></ul> <p>包含同意原則成員資格資料的設定檔資料集需要讀取許可權。 需要寫入許可權，因為會建立同意原則查詢資料集並維持同步。</p> |
| 在資料檢視中檢視同意原則元件 | 指派資料檢視的產品設定檔的產品設定檔管理員 <p>如需詳細資訊，請參閱[存取控制](/help/technotes/access-control.md)。</p> | 不適用 |
| 在Analysis Workspace中使用同意原則元件 | 存取已新增同意原則元件的資料檢視 | 不適用 |

## 同意報告和篩選使用案例

例如，強調同意報告和篩選所提供的值的使用案例，請參閱[同意報告和篩選使用案例](/help/connections/consent-reporting-filtering/consent-use-cases.md)。

## 同意報告和篩選限制

在[設定同意報告及篩選](/help/connections/consent-reporting-filtering/consent-configure.md)時，請考量下列限制：

* 單一沙箱只能有一個同意原則查詢資料集。 相同沙箱中的多個設定共用該查詢資料集。

* 一個連線只能與一個同意報告和篩選設定相關聯。
