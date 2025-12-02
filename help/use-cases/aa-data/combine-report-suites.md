---
title: 結合報告套裝與不同的結構描述
description: 了解如何使用「資料準備」來結合報告套裝與不同的結構描述
exl-id: 2656cc21-3980-4654-bffb-b10908cb21f5
feature: Use Cases
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1321'
ht-degree: 55%

---

# 結合報告套裝與不同的結構描述

[Analytics來源聯結器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)將來自Adobe Analytics的報告套裝資料帶入Adobe Experience Platform，以供Adobe Experience Platform應用程式使用，例如Real-time Customer Data Platform和Customer Journey Analytics (Customer Journey Analytics)。 引入Adobe Experience Platform的每個報告套裝都會設定為個別來源連線資料流，而每個資料流都會當作Adobe Experience Platform資料湖中的資料集。 Analytics來源聯結器會為每個報告套裝各建立一個資料集。

Customer Journey Analytics客戶使用[連線](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-hant)將資料集從Adobe Experience Platform資料湖整合到Customer Journey Analytics Analysis Workspace中。 不過，在連線中組合報告套裝時，需要使用Adobe Experience Platform [資料準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hant)功能解決報告套裝之間的結構描述差異。 目的是確保Adobe Analytics變數（例如prop和eVar）在Customer Journey Analytics中具有一致的意義。

## 報告套裝之間的結構描述差異有問題

假設您的公司想要將來自兩個不同報告套裝的資料引入Adobe Experience Platform以供Customer Journey Analytics使用，並假設兩個報告套裝的結構描述有所差異：

| 報告套裝 A | 報告套裝 B |
| --- | --- |
| eVar1 = 搜尋字詞 | eVar1 = 事業單位 |
| eVar2 = 客戶類別 | eVar2 = 搜尋字詞 |

為了簡單起見，假設兩個報表套裝僅定義了這些eVar。

此外，假設您執行下列動作：

- 建立Analytics來源連線（不使用資料準備），將&#x200B;**報告套裝A**&#x200B;擷取至Adobe Experience Platform資料湖，做為&#x200B;**資料集A**。
- 建立Analytics來源連線（不使用資料準備），將&#x200B;**報告套裝B**&#x200B;擷取至Adobe Experience Platform資料湖，做為&#x200B;**資料集B**。
- 建立名為[所有報告套裝](/help/connections/create-connection.md)的&#x200B;**Customer Journey Analytics連線**，結合了資料集A和資料集B。
- 建立名為[全域檢視](/help/data-views/create-dataview.md)的&#x200B;**Customer Journey Analytics資料檢視**，其基礎為全部報表套裝連線。

如果不使用「資料準備」來解決資料集 A 和資料集 B 之間的結構描述差異，則「全域檢視」資料檢視中的 eVar 將包含混合值：

| Customer Journey Analytics中的全域檢視資料檢視 |
| --- |
| eVar1 => 混合搜尋字詞和業務單位 |
| eVar2 => 混合客戶類別和搜尋字詞 |

這種情況會產生無意義的 eVar1 和 eVar2 報告：

- eVar 欄位包含具有不同語義意義的混合值。
- 搜尋字詞分佈在 eVar1 和 eVar2 之間。
- 不可能對每個搜尋字詞、業務單位和客戶類別使用不同的歸因模型。

## 使用「Adobe Experience Platform資料準備」解決報告套裝之間的結構描述差異

Experience Platform資料準備功能已與Analytics來源聯結器整合，可用於解決上述案例中說明的結構描述差異。 這會產生在Customer Journey Analytics資料檢視中具有一致意義的eVar。 (下面使用的命名慣例，可以根據您的需求加以自訂。)

1. 在為報告套裝A和報告套裝B建立來源連線資料流之前，請在Adobe Experience Platform中[建立新的結構描述](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=zh-Hant) （在我們的範例中將其稱為&#x200B;**統一結構描述**。） 將下列專案新增至結構描述：

   | 「統一結構描述」 |
   | --- |
   | **XDM ExperienceEvent** 類別 |
   | **「Adobe Analytics ExperienceEvent 範本」**&#x200B;欄位群組 |

1. 將另一個欄位群組新增到結構描述或[建立自訂欄位群組](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html#:~:text=To%20create%20a%20new%20field,section%20in%20the%20left%20rail)並將其新增到結構描述。 我們將建立一個新的欄位群組，並將其稱為&#x200B;**「統一欄位」**。 然後我們將以下欄位新增到新的欄位群組中：

   | 「統一欄位」自訂欄位群組  |
   | --- |
   | 搜尋字詞 |
   | 事業單位 |
   | 客戶類別 |

1. 為&#x200B;**報告套裝 A** 建立來源連線資料流，選取&#x200B;**「統一結構描述」**&#x200B;用於資料流中。 將自訂對應新增到資料流，如下所示：

   | 報告套裝 A 來源欄位 | 「統一欄位」欄位群組中的目的地欄位 |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;路徑>_.Search_term |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;路徑>_.Customer_category |

   >[!NOTE]
   >
   >目的地欄位的 XDM 路徑將取決於您如何建構自訂欄位群組。

1. 為&#x200B;**報告套裝 B** 建立來源連線資料流，再次選取&#x200B;**「統一結構描述」**&#x200B;以用於資料流中。 工作流程會顯示兩個欄位存在描述項名稱衝突。 這是因為報告套裝 B 中的 eVar1 和 eVar2 描述項與報告套裝 A 中的不同。但我們已經知道這一點，所以我們可以放心地忽略衝突，並使用自訂對應，如下所示：

   | 報告套裝 B 來源欄位 | 「統一欄位」欄位群組中的目的地欄位 |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;路徑>_.Business_unit |
   | _experience.analytics.customDimensions.eVars.eVar2 | _\&lt;路徑>_.Search_term |

1. 現在為Customer Journey Analytics建立&#x200B;**所有報告套裝**&#x200B;連線，結合資料集A和資料集B。

1. 在Customer Journey Analytics中建立&#x200B;**全域檢視**&#x200B;資料檢視。 忽略原始 eVar 欄位，僅包括「統一欄位」欄位群組中的欄位。

   Customer Journey Analytics中的&#x200B;**全域檢視**&#x200B;資料檢視：

   | 來源欄位 | 包括在資料檢視中？ |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar1 | 否 |
   | \_experience.analytics.customDimensions.eVars.eVar2 | 無 |
   | _\&lt;路徑>_.Search_term | 是 |
   | _\&lt;路徑>_.Customer_category  | 是 |
   | _\&lt;路徑>_.Business_unit | 是 |

您現在已將來源報告套裝中的 eVar1 和 eVar2 對應到三個新欄位。 請注意，使用「資料準備」對應的另一個優點是，目的地欄位現在是根據語義上有意義的名稱 (搜尋字詞、業務單位、客戶類別)，而不是較無意義的 eVar 名稱 (eVar1、eVar2)。

>[!NOTE]
>
>「統一欄位」自訂欄位群組和關聯的欄位對應可以隨時新增到現有的Analytics來源聯結器資料流和資料集。 但是，這只會影響未來的資料。

## 不只是報告套裝

「資料準備」結合資料集與不同結構描述的能力，超越了 Analytics 報告套裝。 假設您有兩個包含以下資料的資料集：

| 資料集A =透過Analytics來源聯結器的Analytics報告套裝 |
| --- |
| `eVar1` => 客戶類別 |

| 資料集 B = 呼叫中心資料 |
| --- |
| Some_field => 客戶類別 |

使用「資料準備」，您可以將 Analytics 資料中 eVar 1 的「客戶類別」結合呼叫中心資料中 Some_field 的「客戶類別」。 以下是可行方法之一。 同樣地，您可以根據需求更改命名慣例。

1. 在Adobe Experience Platform中建立結構描述。 將以下內容新增到結構描述中：

   | 「擴充型結構描述」 |
   | --- |
   | **「XDM 體驗事件」**&#x200B;類別 |
   | **「Adobe Analytics 體驗事件範本」**&#x200B;欄位群組 |

1. 建立一個新的欄位群組，並將其新增到結構描述。 新增欄位到欄位群組：

   | 「客戶資訊」自訂欄位群組  |
   | --- |
   | Customer_category |

1. 為&#x200B;**資料集 A** 建立資料流，選取&#x200B;**「擴充型結構描述」**&#x200B;做為您的結構描述。 將自訂對應新增到資料流，如下所示：

   | 資料集 A 來源欄位 | 「客戶資訊」欄位群組中的目的地欄位 |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;路徑>_.Customer_category |

1. 為&#x200B;**資料集 B** 建立資料流，再次選取&#x200B;**「擴充型結構描述」**&#x200B;做為您的結構描述。 將自訂對應新增到資料流，如下所示：

   | 資料集 B 來源欄位 | 「客戶資訊」欄位群組中的目的地欄位 |
   | --- | --- |
   | _\&lt;路徑>_.Some_field | _\&lt;路徑>_.Customer_category |

1. 建立結合資料集A和資料集B的Customer Journey Analytics連線。

1. 使用您剛建立的Customer Journey Analytics連線，在Customer Journey Analytics中建立資料檢視。 忽略原始 eVar 欄位，僅包括「客戶資訊」欄位群組中的欄位。

   Customer Journey Analytics中的資料檢視：

   | 來源欄位 | 包括在資料檢視中？ |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | 否 |
   | \_experience.analytics.customDimensions.eVars.eVar2 | 否 |
   | _\&lt;路徑>_.Customer_category | 是 |

## 「資料準備」與「元件 ID」的比較

如上所述，「資料準備」可讓您將不同的欄位對應到多個 Adobe Analytics 報告套裝中。 如果您想要將多個資料集的資料合併至單一Customer Journey Analytics連線，這在Customer Journey Analytics中會很有幫助。 但是，如果您打算將報表套裝保留在單獨的Customer Journey Analytics連線中，但希望在這些連線和資料檢視中使用一組報表，則變更Customer Journey Analytics中的基礎「元件ID」提供了即使結構描述不同，也能讓報表相容的方法。 如需詳細資訊，請參閱[元件設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html)。

變更「元件ID」是僅限Customer Journey Analytics的功能，不會影響從Analytics來源聯結器傳送到「即時客戶個人檔案」和RTCDP的資料。
