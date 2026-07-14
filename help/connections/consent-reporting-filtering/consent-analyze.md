---
title: 在Customer Journey Analytics中分析同意原則資料
description: 瞭解如何使用同意原則維度、量度和範本，報告Analysis Workspace中的訪客同意原則成員資格。
solution: Customer Journey Analytics
feature: Privacy
role: Admin, User
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
source-git-commit: eafeab50e86b3e98f372c70a0fd43494015ca002
workflow-type: tm+mt
source-wordcount: 385
ht-degree: 2%

---

# 分析同意原則資料

您可以將Experience Platform設定檔資料集的同意原則資料擷取到Customer Journey Analytics連線。

在您[建立同意報告及篩選設定](/help/connections/consent-reporting-filtering/consent-configure.md)後，同意原則資料在已設定連線的資料檢視中成為新的元件。 如果您有權存取存在這些元件的資料檢視，您可以在Analysis Workspace中的任何地方使用這些元件。

## 同意原則元件

同意報告會將下列元件新增至您的資料檢視。 這些元件會從您設定檔資料集中的`consentPoliciesIDMap`欄位讀取，而原則名稱和說明則來自同意原則查詢資料集。

### 維度

| 維度 | 說明 |
|---------|----------|
| **[!UICONTROL 同意原則ID]** | 訪客符合的同意原則識別碼。 |
| **[!UICONTROL 原則名稱]** | 同意原則查詢資料集中的同意原則的易記名稱。 |
| **[!UICONTROL 原則描述]** | 同意原則的描述，來自同意原則查詢資料集。 |

### 量度

| 量度 | 說明 |
|---------|----------|
| **[!UICONTROL 有同意的訪客]** | 符合約意原則的訪客數量。 |
| **[!UICONTROL 同意的事件]** | 與符合約意原則的訪客相關聯的事件數。 |
| **[!UICONTROL 唯一的同意原則]** | 在報告時段中表示的不同同意政策的數量。 |

### 衍生欄位

衍生欄位參考`consentPoliciesIDMap`欄位以擷取同意原則ID。 您可以使用此衍生欄位作為其他同意型維度的基礎。 如需衍生欄位的詳細資訊，請參閱[衍生欄位](/help/data-views/derived-fields/derived-fields.md)。

## 在Analysis Workspace中使用同意原則元件

若要報告同意原則成員資格：

1. 在Analysis Workspace中，開啟使用為同意報告所設定資料檢視的專案。

1. 從元件面板，將同意原則維度（例如&#x200B;**[!UICONTROL 原則名稱]**）拖曳至自由表格。

1. 新增同意量度，例如&#x200B;**[!UICONTROL 有同意的訪客]**，到資料表。

1. 依任何其他維度（例如頁面或頻道）劃分結果，以瞭解同意訪客的行為。

## 使用同意原則分析範本

當資料檢視設定為同意報表時，Customer Journey Analytics會自動在Analysis Workspace中使用同意原則分析範本。 此範本提供報告訪客同意原則成員資格的起點。

如需有關如何存取範本的資訊，請參閱[存取並執行範本](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template)。
