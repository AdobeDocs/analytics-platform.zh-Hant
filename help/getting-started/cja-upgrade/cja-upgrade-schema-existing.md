---
title: 建立結構描述以進行Customer Journey Analytics
description: 瞭解從Adobe Analytics升級為Customer Journey Analytics時的建議路徑
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 0%

---

# 透過Customer Journey Analytics使用您的Adobe Analytics結構描述

>[!NOTE]
>
>此檔案應該用作[Adobe Analytics的Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)的一部分。

<!-- this page exists as the "Learn more" link in the info icon for the option "I am comfortable using my Adobe Analytics schema as a basis" -->

若要搭配Customer Journey Analytics使用現有的Adobe Analytics結構描述，只有在您的Adobe Analytics實作已透過Adobe Experience Platform Web SDK設定時才可使用。<!-- correct? Or can you do this with an AppMeasurement implementation?-->

請考量搭配Customer Journey Analytics使用您的Adobe Analytics結構描述的下列優缺點：

| 優勢 | 缺點 |
|----------|---------|
| <p>使用Adobe Analytics結構描述的優點包括：</p><ul><li>容易升級<p>如果您已透過Adobe Experience Platform Web SDK將資料傳送至Adobe Analytics，您可以新增其他服務至您的資料串流，以將資料傳送至Adobe Experience Platform (然後可在您的Customer Journey Analytics設定中使用)。</p></li></ul> | <p>使用Adobe Analytics結構的缺點包括：</p><ul><li>雖然使用Adobe Analytics結構描述在其可搭配其他Platform應用程式使用方面不會限制您，但它的確會讓結構描述比其他應用程式更複雜。 這是因為Adobe Analytics結構描述包含許多專屬於Adobe Analytics的物件，您的組織不太可能使用。<p>當需要變更結構描述時，您必須篩選數千個未使用的欄位，以尋找需要更新的欄位。</p></li></ul> |

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