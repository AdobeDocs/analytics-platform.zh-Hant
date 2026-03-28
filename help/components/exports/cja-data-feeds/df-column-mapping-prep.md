---
description: 瞭解如何準備將資料摘要欄從Adobe Analytics對應至Customer Journey Analytics。
keywords: 點按資料流;資料摘要;資料摘要;資料摘要
title: 準備將資料摘要欄從Adobe Analytics對應至Customer Journey Analytics
feature: Components
hide: true
hidefromtoc: true
exl-id: d0a9e697-1e48-4cfb-8613-2f932bf5015b
source-git-commit: b9efb621523f8bbfbb3afe7db4db2e60fcddd34c
workflow-type: tm+mt
source-wordcount: '1060'
ht-degree: 2%

---

# 準備將資料摘要欄從Adobe Analytics對應至Customer Journey Analytics

在決定可納入資料摘要的欄時，Customer Journey Analytics提供的架構比Adobe Analytics更靈活。 大部分組織應該會從Customer Journey Analytics匯出與從Adobe Analytics匯出不同的資料摘要欄。 造成這些差異的原因如下：

* **[結構描述架構](#schema-architecture)**： Adobe Analytics資料摘要欄衍生自Analytics變數，而Customer Journey Analytics資料摘要欄衍生自資料檢視結構描述。

* **[資料處理](#data-processing)**： Adobe Analytics和Customer Journey Analytics之間存在基本資料處理差異，尤其是許多Adobe Analytics資料行同時存在前置和後置處理資料行。

* **[未使用的資料行](#unused-columns)**： Adobe Analytics包含超過1,100個資料摘要資料行。 大多陣列織不會使用所有要匯出的欄的資料。

* **[跨頻道欄](#cross-channel-columns)**： Customer Journey Analytics支援跨頻道資料（例如客服中心資料），Adobe Analytics未提供這些資料。

開始將Adobe Analytics資料摘要欄對應至Customer Journey Analytics資料摘要欄之前，請檢閱以下章節，以更加瞭解這些影響對應的關鍵因素。

檢閱此資訊後，請依照您計畫保留在Customer Journey Analytics中的每個Adobe Analytics資料摘要資料行的對應指示操作，如[資料欄參考](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md)中所述。

## 結構描述架構

在決定哪些欄可納入資料摘要時，Customer Journey Analytics提供的架構比Adobe Analytics更靈活：

### Adobe Analytics架構

預先定義的靜態變數清單可納入為資料摘要欄。

很容易納入所有欄，許多客戶也會這麼做，即使這些欄包含的資料在整個組織內未使用。

### Customer Journey Analytics架構

資料檢視結構描述中包含的任何元件都可以納入為資料摘要欄。 如需每個潛在Adobe Analytics資料摘要資料行中此程式的詳細資訊，請參閱[資料行參考](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md)。

透過下表所述的任何一種方式，將元件包含在資料檢視結構描述中：

| 納入資料檢視結構描述的方法 | 其他資訊 |
|---------|----------|
| XDM結構描述欄位在資料檢視中組織為元件 | XDM結構描述中存在的欄位在資料檢視中組織為元件後，會成為Customer Journey Analytics資料檢視結構描述的一部分。 <p>您的Customer Journey Analytics XDM結構描述中預設可用的欄位數可能會因Customer Journey Analytics實作收集資料的方式而異，如下所示：</p><ul><li>**新的Web SDK實作**：如果您的Customer Journey Analytics實作使用自訂結構描述，Adobe Analytics資料摘要中的許多欄可能在Customer Journey Analytics中不存在。 同樣地，Customer Journey Analytics可能包含Adobe Analytics資料摘要中不存在的欄位。<p>如有可能，請洽詢為您組織的Customer Journey Analytics實作設計XDM架構的團隊或個人。 建立XDM結構描述時，許多人都在針對Customer Journey Analytics中需要的Adobe Analytics欄位做出決定。 若要了解更多資訊，請參閱「[建構您的結構描述以用於 Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)」。</p></li><li>**Analytics Source Connector實作**：許多資料摘要欄位預設有一對一的欄位對應，因為Analytics Source Connector使用XDM結構描述中的Analytics Experience Event欄位群組。 如需瞭解哪些Adobe Analytics欄位對應到這個欄位群組中的欄位，請參閱Experience Platform檔案中的[Analytics欄位對應](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics)。</li></ul> |
| 元件是使用衍生欄位在資料檢視中建立 | 您可以直接在資料檢視中建立元件，進而建立XDM結構描述中無法使用的資料摘要欄。 |

## 資料處理

Adobe Analytics和Customer Journey Analytics之間的資料處理差異會影響哪些資料摘要欄可供匯出，如下所示：

* **Adobe Analytics**：許多資料摘要欄位會匯出為兩個個別的欄：一個包含已預先處理的資料，另一個包含已後續處理的資料。 （後續處理的資料包括伺服器端邏輯、處理規則、VISTA規則、維度持續性規則等。）

  由於Adobe Analytics會以兩個個別的欄（一個用於預先處理的資料，另一個用於後續處理的資料）匯出某些欄位的資料，因此Adobe Analytics包含的資料摘要欄會比Customer Journey Analytics多。 對應欄位時，請記住這一點。

* **Customer Journey Analytics**：在資料檢視中建立資料摘要後，即可使用這些欄位。 通常，Customer Journey Analytics資料檢視中的欄位僅包含後續處理的資料。 不過，您通常可以在Adobe Analytics資料檢視中建立第二個版本的欄位，並將它設定為在點選時過期，藉此近似表示欄位的Customer Journey Analytics預處理版本。

## 未使用的欄

有超過1,100個資料摘要欄可匯出至Adobe Analytics。 在這些欄中，並非所有都會用於您的Customer Journey Analytics資料摘要。 這種差異並不表示您的Customer Journey Analytics資料摘要欄位不足。

識別您的組織使用的Adobe Analytics資料摘要欄。 這會通知您的Customer Journey Analytics資料摘要中需要哪些欄。 若要決定要使用的欄：

* **識別僅適用於Adobe Analytics的欄位**： Adobe Analytics資料摘要中的某些欄位特定於Adobe Analytics的資料處理引擎，因此不適用於Customer Journey Analytics。 此類資料行的範例為`exclude_hit`和`hit_source`。

* **識別套用至您組織的欄位**：雖然並非所有Adobe Analytics客戶都會匯出所有可用的欄，但許多客戶會匯出多於實際使用的欄。

  開始從Customer Journey Analytics匯出資料摘要之前，您應該先判斷您的組織目前使用的Adobe Analytics資料摘要欄，然後確定這些元件存在於您的Customer Journey Analytics資料檢視結構描述中。 若要收集這項資訊，請聯絡貴組織內使用Adobe Analytics資料摘要內容的團隊或個人。

## 跨頻道欄

Customer Journey Analytics支援跨管道資料（例如客服中心資料），這些資料在Adobe Analytics中無法使用。 這些跨管道欄位是Customer Journey Analytics資料摘要中可包含的新欄範例，Adobe Analytics不支援這些欄。

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
