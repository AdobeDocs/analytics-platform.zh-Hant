---
title: 與 Adobe Analytics 比較
description: Customer Journey Analytics 與 Adobe Analytics 比較的概觀。
solution: Customer Journey Analytics
feature: Basics
exl-id: bde36283-86af-4b1a-9cbe-e251676b2951
role: User
autotag-review: '2026-05-19T09:13:47.721Z'
TQID: 'https://experienceleague.adobe.com/MU9ywSyInHtsdzqvxO3yxTSY5bcDvdhnTUkhAgDHmZ4'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
    internal-label: Upgrade
  - id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1
    internal-label: Basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 1f480cda20e0b2d54dd42b909bfa8bf8a2bc0c95
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 52%
---
# 與 Adobe Analytics 比較

文件的這個小節說明如何比較並了解 Adobe Customer Journey Analytics 和 Adobe Analytics 之間的差異。

這兩個解決方案的基本差異在於當建立報告和分析時 (可以) 考量的資料寬度。

在 Customer Journey Analytics 中，*任何*&#x200B;資料來源都可以做為報告和分析的資料。 Adobe Analytics主要針對從網站和行動應用程式收集的線上資料。 Adobe Analytics提供從其他來源匯入資料的功能，但此功能的主要目的是圍繞先前提到的線上資料提供更多內容。

## 資料收集

Customer Journey Analytics 依賴儲存在 Adobe Experience Platform 資料集中的資料。 要在 Experience Platform 中收集和擷取這些資料集中的資料，您有數種選項。 這些選項在[資料擷取概觀](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-data-ingestion/data-ingestion)中有詳細說明。

Adobe Analytics 最終在解決方案本身內收集資料。 同樣地，您有數個選項可收集該資料，這些選項在[Adobe Analytics實作指南](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/home)中有詳細說明。

您可以使用 [Analytics 來源連接器](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics)在 Customer Journey Analytics 使用您的 Adobe Analytics 報告套裝資料。 此連接器會擷取從 Adobe Analytics 收集到的資料並傳至 Experience Platform。 接著您可以在 Customer Journey Analytics 中建立與這個資料集的連線。 如需詳細資訊，請參閱[在 Customer Journey Analytics 中使用 Adobe Analytics 報告套裝資料](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja)。

Adobe Analytics報表套裝中的資料與構成Customer Journey Analytics連線之Adobe Experience Platform資料集中儲存的資料無關。 因此，Adobe建議您分別評估每個平台中的資料，不要期望兩個平台都反映相同的值。

## 資料處理

在製作資料相關的報告之前，您通常需要處理該資料以確保可以正確使用資料進行報告。 資料處理作業可以在收集時和報告時進行。

一般而言，Customer Journey Analytics的設計目的是在報表時間處理Experience Platform資料集中收集和儲存的資料。 Customer Journey Analytics 提供強大的報告時處理功能，以確保資料已準備好用於報告和分析。 [衍生欄位](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-dataviews/derived-fields)和[元件設定](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-dataviews/component-settings/overview)可以修改並回溯套用至歷史資料。 如果您必須在Experience Platform擷取資料之前對應、轉換及驗證資料，則可以使用Experience Platform的[資料準備](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/data-prep/home)功能。

在 Adobe Analytics 中，大部分資料處理作業是在收集資料後立即進行。 行銷管道規則、處理規則、eVar持續性和其他後續處理邏輯此時會套用，並在報表套裝中成為永久性。 對任何這些設定所做的變更，只會影響該時間點之後的新傳入資料。

如需詳細資訊，請參閱[比較 Adobe Analytics 和 Customer Journey Analytics 之間的資料處理](data-processing-comparisons.md) 和[處理規則、VISTA 和分類與「資料準備」的比較](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep)。


## 術語

Customer Journey Analytics 在定義維度和量度方面提供彈性，這得益於基於底層體驗資料模型 (XDM) 的結構描述所提供的彈性。 例如，Adobe Analytics使用訪客、造訪和點選時，Customer Journey Analytics使用人員、工作階段和事件（您可以視需要變更命名）。

如需術語差異的詳細資訊，請參閱[比較透過 Analytics 來源連接器傳遞的 Analytics 資料術語](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology)。


## 虛擬報告環境和沙箱

Adobe Analytics 採用虛擬報告套裝的概念，允許您將收集到的資料分成不同區段，並控制該分段資料的存取。

Customer Journey Analytics 採用類似的概念，稱為「資料檢視」。 資料檢視是一種容器，讓您決定如何解譯來自某個連線的資料。 其提供極大的彈性，可指定和設定維度和量度，做好報告和分析的準備。

Experience Platform提供的沙箱可作為容器，用於儲存特定環境的資料和應用程式。 沙箱的功能與 Adobe Analytics 虛擬報告套件或 Customer Journey Analytics 資料檢視無關。 Adobe Analytics本身與Experience Platform沙箱沒有相依性或關聯。 Customer Journey Analytics 確實支援 Experience Platform 沙箱，但有一些重要的考量。

如需詳細資訊，請參閱[虛擬報告套裝、資料檢視、Adobe Experience Platform 沙箱和 Analytics 來源連接器](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc)。


## 身分識別

Customer Journey Analytics 支援您定義為結構描述一部分的身分識別，而包含您資料的資料集會符合這些結構描述。 因此，身分識別是 Experience Platform 的基本概念，Customer Journey Analytics 在設定[連線](../../connections/overview.md) (透過為每個資料集定義人員 ID) 和套用 [拼接](../../stitching/overview.md) 以進行跨管道分析時，會使用身分識別。 Experience Platform SDK和API使用的重要身分識別是ECID。

Adobe Analytics 使用一組更明確的身分識別欄位，例如 Adobe Analytics ID (AAID)。 使用Analytics來源聯結器時，這些Adobe Analytics身分識別欄位會獲得特殊處理。 如需詳細資訊，請參閱 [AAID、ECID、AACUSTOMID 和 Analytics 來源連接器](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc)。


## 高基數維度

Customer Journey Analytics會儲存整個維度值，一個維度可跨越的不重複值數目沒有限制。 相較之下，Adobe Analytics則使用32位元雜湊來對應維度值，以最佳化報表和儲存空間。 此行為可能導致報告發生[雜湊碰撞](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/validate/hash-collisions)。 一旦達到唯一限制臨界值，Adobe Analytics也會將值儲存至[低流量](https://experienceleague.adobe.com/zh-hant/docs/analytics/technotes/low-traffic)條列專案。 使用這些維度的區段可顯示Adobe Analytics與Customer Journey Analytics報表之間的差異。

## 支援的功能

如需有關Adobe Analytics功能的概述，以及Customer Journey Analytics如何支援這些功能，請參閱[Customer Journey Analytics功能支援](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa)。
