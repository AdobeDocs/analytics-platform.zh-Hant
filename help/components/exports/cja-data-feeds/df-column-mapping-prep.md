---
description: 瞭解如何準備將資料摘要欄從Adobe Analytics對應至Customer Journey Analytics。
keywords: 點按資料流;資料摘要;資料摘要;資料摘要
title: 準備將資料摘要欄從Adobe Analytics對應至Customer Journey Analytics
feature: Components
hide: true
hidefromtoc: true
source-git-commit: 5dada1744a479cd4736c9fb7f3c807471e8da226
workflow-type: tm+mt
source-wordcount: '948'
ht-degree: 2%

---

# 準備將資料摘要欄從Adobe Analytics對應至Customer Journey Analytics

從Adobe Analytics資料摘要轉換成Customer Journey Analytics資料摘要時，自然會將每個Adobe Analytics資料摘要欄對應到Customer Journey Analytics中的資料摘要欄。

不過，將資料摘要欄從Adobe Analytics對應至Customer Journey Analytics很少是一對一的對應。 這是由於下列因素所造成：

* **[結構描述架構](#schema-architecture)**： Adobe Analytics資料摘要欄衍生自Analytics變數，而Customer Journey Analytics資料摘要欄衍生自Experience Platform中的XDM結構描述欄位和Customer Journey Analytics中的資料檢視元件。

* **[實作型別](#implementation-type)**： Adobe Analytics和Customer Journey Analytics分別支援多個實作設定。 對應個別欄位所需的步驟取決於這些實作。

* **[資料處理](#data-processing)**： Adobe Analytics和Customer Journey Analytics之間存在基本資料處理差異。

* **[未使用的資料行](#unused-columns)**： Adobe Analytics包含超過1,100個資料摘要資料行。 識別您的組織使用其中哪些欄，以便您可以計畫僅對應所需的欄。

開始將Adobe Analytics資料摘要欄對應至Customer Journey Analytics資料摘要欄之前，請檢閱以下章節，以更加瞭解這些影響對應的關鍵因素。

檢閱此資訊後，請依照您計畫保留在Customer Journey Analytics中的每個Adobe Analytics資料摘要資料行的對應指示操作，如[資料欄參考](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md)中所述。

## 結構描述架構

Experience Data Model (XDM)結構描述以及Customer Journey Analytics中使用的資料檢視比Adobe Analytics變數型模型更靈活。 因此，您組織的XDM結構描述可能不會包含轉換為一對一資料摘要欄對應的欄位。

請考量下列有關架構架構的要點：

* 缺少一對一欄對應並不表示您的Customer Journey Analytics XDM結構描述不足。 這表示您必須先決定目前使用哪些Adobe Analytics資料摘要欄，然後僅將這些欄對應至Customer Journey Analytics資料摘要。

* Customer Journey Analytics XDM結構描述支援跨管道資料（例如客服中心資料），但在Adobe Analytics中無法使用。 這些跨管道欄位是Adobe Analytics不支援的Customer Journey Analytics資料摘要中可包含的新欄範例。

* 欄位必須先納入Experience Platform的XDM結構描述，然後經過組織以用於Customer Journey Analytics的資料檢視，才能納入Customer Journey Analytics資料摘要中。

  如需每個潛在Adobe Analytics資料摘要資料行中此程式的詳細資訊，請參閱[資料行參考](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md)。

>[!TIP]
>
>如有可能，請洽詢為您組織的Customer Journey Analytics實作設計XDM架構的團隊或個人。 建立XDM結構描述時，許多人都在針對Customer Journey Analytics中需要的Adobe Analytics欄位做出決定。 若要了解更多資訊，請參閱「[建構您的結構描述以用於 Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)」。

## 實作型別

<!--  tons of different AA implementations + tons of different CJA schemas -->

視為Customer Journey Analytics實作收集資料的方式而定，您的Customer Journey Analytics XDM結構描述中可對應至的欄位數量可能有所不同，如下所示：

* **新的Web SDK實作**：如果您的Customer Journey Analytics實作使用自訂結構描述，Adobe Analytics資料摘要中的許多欄可能在Customer Journey Analytics中不存在。 同樣地，Customer Journey Analytics可能包含Adobe Analytics資料摘要中不存在的欄位。

* **Analytics Source Connector實作**：許多資料摘要欄位預設有一對一的欄位對應，因為Analytics Source Connector使用XDM結構描述中的Analytics Experience Event欄位群組。 如需瞭解哪些Adobe Analytics欄位對應到這個欄位群組中的欄位，請參閱Experience Platform檔案中的[Analytics欄位對應](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics)。

<!-- **Data layer**: ??? -->

## 資料處理

Adobe Analytics和Customer Journey Analytics的資料處理方式不同，如下所示：

**Adobe Analytics**：許多資料摘要欄位會匯出為兩個個別的欄：一個包含已預先處理的資料，另一個包含已後續處理的資料。 （後續處理的資料包括伺服器端邏輯、處理規則、VISTA規則、維度持續性規則等。）

由於Adobe Analytics會以兩個個別的欄（一個用於預先處理的資料，另一個用於後續處理的資料）匯出某些欄位的資料，因此Adobe Analytics包含的資料摘要欄會比Customer Journey Analytics多。 對應欄位時，請記住這一點。

**Customer Journey Analytics**：在資料檢視中建立資料摘要後，即可使用這些欄位。 通常，Customer Journey Analytics資料檢視中的欄位僅包含後續處理的資料。 不過，您通常可以在Adobe Analytics資料檢視中建立第二個版本的欄位，並將它設定為在點選時過期，藉此近似表示欄位的Customer Journey Analytics預處理版本。

## 未使用的欄

有超過1,100個資料摘要欄可匯出至Adobe Analytics。 在這些欄中，並非所有都會用於您的Customer Journey Analytics資料摘要。

若要決定要使用的欄：

* **識別僅適用於Adobe Analytics的欄位**： Adobe Analytics資料摘要中的某些欄位特定於Adobe Analytics的資料處理引擎，因此不適用於Customer Journey Analytics。 此類資料行的範例為`exclude_hit`和`hit_source`。

* **識別套用至您組織的欄位**：雖然並非所有Adobe Analytics客戶都會匯出所有可用的欄，但許多客戶匯出的數量會多於實際使用的數量。

  開始對應資料摘要欄之前，請先識別貴組織實際使用了哪些欄位。 若要收集這項資訊，請聯絡使用Adobe Analytics資料摘要內容的團隊或個人。



<!--

1. View the data views throughout your organization to make sure that corresponding dimensions are available. If a corresponding dimension does not exist in the data view, create it.

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view.

   

1. For each Adobe Analytics data feed field that is being used, ensure that a similar field exists in the XDM schema.

1. Verify that and that corresponding dimensions are available in the data view. If not, you need to create them. 

1. View the data views throughout your organization to see which dimensions are available. 

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view. 

## Map data feed columns from Adobe Analytics to Customer Journey Analytics

### Step 1 - Map the default columns included in Customer Journey Analytics

There are roughly 20 default fields included in all WebSDK implementations. 

Before you can map these default columns, make sure that your Customer Journey Analytics environment meets the following prerequisites:

* It uses a WebSDK implementation.

* The appropriate field groups that contain the default WebSDK fields are added to your XDM schema.If the field is not added to your schema, it is included in the payload, but ultimately dropped.

* Each default field must be curated as a component in a Customer Journey Analytics data view.

* The component settings in the data view must be equivalent to how Analytics treats it (Visit persistence or hit-level persistence).

To map the default dimensions:

1. ...

1. ...

+++ View the Adobe Analytics data feed columns that are included by default

| Adobe Analytics column name | Column description | Data type |
| --- | --- | --- |
| **`accept_language`** | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| **`adload`** | Media ad loads | varchar(255) |
| **`aemassetid`** | A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events. | text |

+++

### Step 2: Discover which additional data feed columns your consumers use

There are over 1,100 data feed columns available to be exported in Adobe Analytics. While not all Adobe Analytics customers export all of the available columns, many customers export more than they actually use. 

Before you begin mapping data feed columns, you should first:

1. Contact the teams or individuals who consume data feed content and determine which data feed columns they use.

1. View the data views throughout your organization to see which dimensions are available. 

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view. 


### Step 3 - Map each additional column

1. ...

1. ...

+++ View the Adobe Analytics data feed columns that could be mapped if they are included in your schema and data views

| Adobe Analytics column name | Column description | Data type |
| --- | --- | --- |
| **`accept_language`** | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| **`adload`** | Media ad loads | varchar(255) |
| **`aemassetid`** | A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events. | text |

+++

Notes below here. Ignore:

Do we group these columns by if you're using the WebSDK, or if you're using specific field groups.

Here's what is in Analytics, and here's what it maps to in CJA. Customers want us to "give them the mappings."

Some of these fields there is probably something like it that you could get in WebSDK. There will be some fields that aren't. Or some that are in AEP that aren't in here (like call center data).

We have an XDM field mappings to Analytics variables. "Adobe analytics XDM Var - first hit on Google." If you set your XDM payload to the given field on the left, it will automatically be associated to the Analytics variable on the right. But we're looking for a reverse mapping of this. 









If you're using ADC, you'll have the AA column name in there. We also have an ADC mapping doc page. (Analytics field mappings doc page maps the fields)



Make a table (or a section) that talks about fields that are new to CJA, like cross-channel fields (call center, etc.) 

The number of AA columns that they can map is not going to be that big (maybe 100). The number of columns that don't map will be huge.

## Data feed column reference

### Adobe Analytics data feed columns that are included by default in Customer Journey Analytics WebSDK implementations

### Adobe Analytics data feed columns that can be included in Customer Journey Analytics data feed

### Adobe Analytics data feed columns that don't apply to Customer Journey Analytics


### Columns, descriptions, and data types

Use this section to learn what data is contained in each column. Most implementations don't use every column, so this section can be referenced when determining which columns to include in a data feed export.

-->
