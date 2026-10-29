---
description: 瞭解管理員如何使用資料檢視或資料字典將說明新增至元件。
title: 新增元件說明
feature: Components
role: Admin
exl-id: 99d531cd-50e9-4e6c-adad-a66b606fd877
TQID: 'https://experienceleague.adobe.com/yXxEhHsXsAw-l9c0oVCNDtwoCUq86UZSnyiwvidKLWA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments
  - id: df28738e-9c71-4aa8-929e-edde22340cc6
    internal-label: Data Dictionary
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: b46a27ff9faca74c3c2baa7938a588b643633705
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 10%
---
# 新增元件說明

說明可協助使用者瞭解在Analysis Workspace中建置專案或檢視報表時，如何使用各種元件。

Customer Journey Analytics管理員可以在資料檢視中或使用「資料字典」，新增元件（維度、量度、區段和日期範圍）的說明。

## 資料視圖

您可以為已新增至資料檢視的元件新增說明。 請參閱[元件設定](/help/data-views/component-settings/overview.md)。

## 資料字母排序

Analysis Workspace中的資料字典可協助使用者和管理員追蹤及更瞭解其Customer Journey Analytics環境中的元件。 資料字典可讓管理員直接在Analysis Workspace中新增元件說明。

如需有關編輯資料字典中元件說明的資訊，請參閱[編輯資料字典中的元件專案](/help/components/data-dictionary/edit-entries-data-dictionary.md)。

如需資料字典的一般資訊，請參閱[資料字典概觀](/help/components/data-dictionary/data-dictionary-overview.md)。

>[!MORELIKETHIS]
>
>[資料檢視元件設定](/help/data-views/component-settings/overview.md)
>[資料字典元件專案](/help/components/data-dictionary/edit-entries-data-dictionary.md)
>

## 自動產生說明

{{release-limited-testing-section}}

Customer Journey Analytics可以使用創作AI為您撰寫說明，而不必手動撰寫每個說明。 您可以產生單一元件的說明，或同時產生許多元件的說明。

產生的說明：

* 長度不超過3個句子。
* 以Adobe使用AI ]**產生的文字**[!UICONTROL &#x200B;結束，讓使用者知道已產生說明。
* 可在產生後進行編輯。

### 先決條件

在您產生說明之前，您的組織必須同意某些產生式AI法律條款。 如果您的組織不同意這些條款，則產生說明的選項會變暗。 選取選項旁的資訊圖示![資訊](/help/assets/icons/InfoOutline.svg)，瞭解如何啟用該功能，或連絡您組織的管理員或Adobe帳戶團隊。

### 如何產生說明

產生的說明會根據元件的定義以及有關如何在資料檢視中使用元件的其他內容，例如：

* 維度的排名最前的專案
* 經常與元件搭配使用的元件

當計算量度或區段參考另一個區段時，產生的說明會說明參考區段的定義。

### 從不同位置產生說明

您可以在Customer Journey Analytics的下列區域產生說明。 有些位置可讓您為多個元件產生說明，有些位置則不然。

選取位置以瞭解如何在該處產生說明。

| 位置 | 支援的元件 | 單一元件 | 多個元件 |
| --- | --- | --- | --- |
| [資料字典](/help/components/data-dictionary/edit-entries-data-dictionary.md) | <ul><li>維度</li><li>量度</li><li>計算量度</li><li>區段</li><li>日期範圍</li></ul> | 是 | 是 |
| [資料檢視](/help/data-views/component-settings/overview.md) | <ul><li>維度</li><li>量度</li><li>衍生欄位</li><li>共用的量度和維度（如需詳細資訊，請參閱[共用的量度和維度](#generate-descriptions-for-shared-metrics-and-dimensions)。）</li></ul> | 是 | 是 |
| [區段產生器](/help/components/segments/seg-builder.md) | 區段 | 是 | 無 |
| [區段管理員](/help/components/segments/seg-manage.md#action-bar) | 區段 | 無 | 是 |
| [計算量度產生器](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) | 計算量度 | 是 | 無 |
| [計算量度管理器](/help/components/calc-metrics/cm-workflow/cm-manager.md#action-bar) | 計算量度 | 無 | 是 |
| [日期範圍產生器](/help/components/date-ranges/create.md#date-range-builder) | 日期範圍 | 是 | 無 |
| [日期範圍管理員](/help/components/date-ranges/manage.md#action-bar) | 日期範圍 | 無 | 是 |

{style="table-layout:auto"}

### 產生共用量度和維度的說明

您只能從資料檢視內產生共用量度和維度的說明，如[從不同位置產生說明](#generate-descriptions-from-various-locations)中的表格所示。 您無法從[共用度量與維度管理員](/help/data-views/shared-metrics-dimensions/smd-overview.md#smd-manager)產生說明。

在資料檢視中產生共用量度或維度的說明時，請考量下列事項：

* 說明會套用至共用元件的所有資料檢視，並取代所有其他資料檢視和「共用量度和維度管理員」中該元件的任何現有說明。

* 說明是以您產生該說明之資料檢視中的內容為基礎（例如資料檢視的排名最前的維度專案）。


