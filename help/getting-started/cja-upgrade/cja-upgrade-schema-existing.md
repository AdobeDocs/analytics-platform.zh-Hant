---
title: 選擇您的 Customer Journey Analytics 結構描述
description: 瞭解選擇Customer Journey Analytics結構時可用的選項，以及各個選項的優缺點
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: a2b90ab2-2fcb-4bf4-a862-2f0675dc2fe2
source-git-commit: 971600fcc7d8a5aac4ad39812ab4a7af69d45ccc
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 24%

---

# 選擇您的 Customer Journey Analytics 結構描述 {#choose-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-tailored"
>title="使用自訂結構描述"
>abstract="(建議) 自訂結構描述可讓您的組織僅追蹤需要的內容，並避免產生與混亂和不必要欄位相關的經常性費用。此選項包括 Web SDK 新增的欄位群組和您的組織自訂的欄位群組。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-default"
>title="使用預設結構描述"
>abstract="(不建議) Adobe Analytics 結構描述包含超過一千個欄位，這可能會讓結構描述變得混亂和複雜。您的組織將被迫繼續遵守 prop 和 eVar 的概念，而這是 Customer Journey Analytics 中未使用的舊版概念。與其他 Adobe Experience Platform 服務的整合更加困難。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>此檔案應該用作[Adobe Analytics到Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)的一部分。

<!-- this page exists as the "Learn more" link in the info icons for the options "I am comfortable using my Adobe Analytics schema as a basis" and "I want to use a schema tailored to my organization" -->

升級至Customer Journey Analytics時，Adobe建議您建立自訂Experience Data Model (XDM)結構，以便在您開始使用其他Platform服務時更符合組織的需求。 或者，您也可以選擇使用現有的Adobe Analytics結構描述。

考量每個專案的優缺點。

## 建立為您的組織量身打造的自訂結構描述（建議）

Adobe建議在升級至Customer Journey Analytics時建立自訂結構描述。

| 優勢 | 缺點 |
|----------|---------|
| <ul><p>更新為您自己的自訂結構描述的優點包括：</p><ul><li>根據貴組織的需求以及您使用的特定平台應用程式量身打造的簡化方案。</li><p>當需要變更結構描述時，您不必在數千個未使用的欄位中篩選，以尋找需要更新的欄位。</p></ul> | <p>更新為您自己的自訂結構的缺點包括：</p><ul><li>在開始將資料傳送至Platform之前，需要先更新您的結構描述，這是一個耗時的過程。</li></ul> |

## 使用您現有的Adobe Analytics結構描述

若要將您現有的Adobe Analytics結構描述與Customer Journey Analytics搭配使用，選項只有在您的Adobe Analytics實作設定為Adobe Experience Platform Web SDK時才可用。<!-- correct? Or can you do this with an AppMeasurement implementation?-->

| 優勢 | 缺點 |
|----------|---------|
| <p>使用Adobe Analytics結構描述的優點包括：</p><ul><li>容易升級<p>如果您已經透過Adobe Experience Platform Web SDK將資料傳送至Adobe Analytics，您可以新增其他服務至您的資料串流，將資料傳送至Adobe Experience Platform (之後可用於您的Customer Journey Analytics設定)。</p></li></ul> | <p>使用Adobe Analytics結構的缺點包括：</p><ul><li>雖然使用Adobe Analytics結構描述在其可搭配其他Platform應用程式使用方面不會限制您，但它的確會讓結構描述比其他應用程式更複雜。 這是因為Adobe Analytics結構描述包含許多專屬於Adobe Analytics的物件，您的組織不太可能使用。<p>當需要變更結構描述時，您必須篩選數千個未使用的欄位，以尋找需要更新的欄位。</p></li></ul> |




<!-- Not sure about any of this: 

If you plan to use your Adobe Analytics schema, the following steps are required:

For Adobe Analytics implementations using AppMeasurement:

1. Datastream mapping

For Adobe Analytics implementations using the Web SDK:

1. 



the upgrade steps provided by the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/).

If you want to create an XDM schema to use with Customer Journey Analytics, continue with [Create an XDM schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).


Tags: (All 3 require data prep mapping. Would need to go into the datastream and map every single field to its appropriate place in XDM. Because whenever you use the data object, it always requires mapping. If you send something in the data object and it doesn't get mapped, the it is permanently lost and can't be recovered.)

1. Shim - Intercepts and instead of sending data to a report suite, it sends it to a Data View. (Data object)

1. Russ special - convert current implementation to a Web SDK implementation - put everything in the data object. 

1. Plop entire data layer into the data object and send that to the datastream. (not documented. Might be the Web SDK docs.)

-->
