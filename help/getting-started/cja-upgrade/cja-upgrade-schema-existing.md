---
title: 選擇您的 Customer Journey Analytics 結構描述
description: 了解關於選擇 Customer Journey Analytics 結構描述時可用選項以及每個選項的優缺點
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: a2b90ab2-2fcb-4bf4-a862-2f0675dc2fe2
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '475'
ht-degree: 100%

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

{{upgrade-note}}

<!-- this page exists as the "Learn more" link in the info icons for the options "I am comfortable using my Adobe Analytics schema as a basis" and "I want to use a schema tailored to my organization" -->

升級到 Customer Journey Analytics 時，Adobe 建議建立自訂體驗資料模型 (XDM) 結構描述，以便在您開始使用其他 Platform 服務時更能滿足組織的需求。或者，您可以選擇使用現有的 Adob&#x200B;&#x200B;e Analytics 結構描述。

考慮每種方法的優點和缺點。

## 建立適合您組織的自訂結構描述 (建議)

在升級到 Customer Journey Analytics 時，Adobe 建議建立自訂結構描述。

| 優點 | 缺點 |
|----------|---------|
| <ul><p>更新到您自己自訂結構描述的優點包括：</p><ul><li>根據您的組織需求和您使用的特定 Platform 應用程式量身定制的簡化結構描述。</li><p>當需要變更結構描述時，您不必篩選數千個未使用的欄位來找到需要更新的欄位。</p></ul> | <p>更新到您自己自訂結構描述的缺點包括：</p><ul><li>更新結構描述相當耗費時間，這是開始將資料傳送到 Platform 之前必需進行的程序。</li></ul> |

## 使用現有的 Adob&#x200B;&#x200B;e Analytics 結構描述

只有當您的 Adob&#x200B;&#x200B;e Analytics 實施以 Adob&#x200B;&#x200B;e Experience Platform Web SDK 來設定時，才可以使用將現有 Adob&#x200B;&#x200B;e Analytics 結構描述與 Customer Journey Analytics 搭配使用的選項。 <!-- correct? Or can you do this with an AppMeasurement implementation?-->

| 優點 | 缺點 |
|----------|---------|
| <p>使用 Adob&#x200B;&#x200B;e Analytics 結構描述的優點包括：</p><ul><li>容易升級<p>如果您已經使用 Adob&#x200B;&#x200B;e Experience Platform Web SDK 將資料傳送至 Adob&#x200B;&#x200B;e Analytics，則您可以向資料流新增附加服務以將資料傳送至 Adob&#x200B;&#x200B;e Experience Platform (然後可在您的 Customer Journey Analytics 設定中使用)。</p></li></ul> | <p>使用 Adob&#x200B;&#x200B;e Analytics 結構描述的缺點包括：</p><ul><li>雖然使用 Adob&#x200B;&#x200B;e Analytics 結構描述不會限制您如何與其他 Platform 應用程式結合使用，但會導致比使用其他結構描述更複雜的結構描述。這是因為 Adobe Analytics 結構描述包含許多 Adob&#x200B;&#x200B;e Analytics 專屬的物件，而您的組織不太可能使用這些物件。<p>當需要變更結構描述時，您必須篩選數千個未使用的欄位來找到需要更新的欄位。</p></li></ul> |




<!-- Not sure about any of this: 

If you plan to use your Adobe Analytics schema, the following steps are required:

For Adobe Analytics implementations using AppMeasurement:

1. Datastream mapping

For Adobe Analytics implementations using the Web SDK:

1. 



the upgrade steps provided by the Customer Journey Analytics Upgrade Guide.

If you want to create an XDM schema to use with Customer Journey Analytics, continue with [Create an XDM schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).


Tags: (All 3 require data prep mapping. Would need to go into the datastream and map every single field to its appropriate place in XDM. Because whenever you use the data object, it always requires mapping. If you send something in the data object and it doesn't get mapped, the it is permanently lost and can't be recovered.)

1. Shim - Intercepts and instead of sending data to a report suite, it sends it to a Data View. (Data object)

1. Russ special - convert current implementation to a Web SDK implementation - put everything in the data object. 

1. Plop entire data layer into the data object and send that to the datastream. (not documented. Might be the Web SDK docs.)

-->
