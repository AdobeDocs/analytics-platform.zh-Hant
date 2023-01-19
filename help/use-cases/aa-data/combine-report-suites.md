---
title: 結合報告套裝與不同的結構描述
description: 了解如何使用「資料準備」來結合報告套裝與不同的結構描述
exl-id: 2656cc21-3980-4654-bffb-b10908cb21f5
source-git-commit: 69356510596d047d80af63338fccca71e8af53cd
workflow-type: ht
source-wordcount: '1335'
ht-degree: 100%

---

# 結合報告套裝與不同的結構描述

[Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant)將來自 Adobe Analytics 的報告套裝資料引入 Adobe Experience Platform (AEP) 以供 AEP 應用程式使用，例如 Real-time Customer Data Platform 和 Customer Journey Analytics (CJA)。 引入 AEP 的每個報告套裝都配置為單獨的來源連線資料流，每個資料流都作為 AEP 資料湖中的資料集。 Analytics 來源連接器會為每個報告套裝各建立一個資料集。

CJA 客戶使用[連線](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hant)，將來自 AEP 資料湖的資料集整合到 CJA 的 Analysis Workspace 中。 但是，在連線中組合報告套裝時，需要使用 AEP 的[「資料準備」](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hant)功能解決報告套裝之間的結構描述差異。 目的是確保 Adobe Analytics 變數 (如 prop 和 eVar) 在 CJA 中具有一致的意義。

## 報告套裝之間的結構描述差異有問題

假設您的公司想要將來自兩個不同報告套裝的資料引入 AEP 以供 CJA 使用，並假設兩個報告套裝的結構描述有所差異：

| 報告套裝 A | 報告套裝 B |
| --- | --- |
| eVar1 = 搜尋字詞 | eVar1 = 事業單位 |
| eVar2 = 客戶類別 | eVar2 = 搜尋字詞 |

為了簡單起見，假設兩個報告套裝僅定義了這些 eVar。

此外，假設您執行下列動作：

- 建立 Analytics 來源連線 (不使用資料準備)，將&#x200B;**報告套裝 A** 擷取至 AEP 資料湖，做為&#x200B;**資料集 A**。
- 建立 Analytics 來源連線 (不使用資料準備)，將&#x200B;**報告套裝 B** 擷取至 AEP 資料湖，做為&#x200B;**資料集 B**。
- 建立名為&#x200B;**「所有報告套裝」**&#x200B;的 [CJA 連線](/help/connections/create-connection.md)，結合了資料集 A 和資料集 B。
- 建立名為&#x200B;**「全域檢視」**，根據「所有報告套裝」連線的 [CJA 資料檢視](/help/data-views/create-dataview.md)。

如果不使用「資料準備」來解決資料集 A 和資料集 B 之間的結構描述差異，則「全域檢視」資料檢視中的 eVar 將包含混合值：

| CJA 中的「全域檢視」資料檢視 |
| --- |
| eVar1 => 混合搜尋字詞和業務單位 |
| eVar2 => 混合客戶類別和搜尋字詞 |

這種情況會產生無意義的 eVar1 和 eVar2 報告：

- eVar 欄位包含具有不同語義意義的混合值。
- 搜尋字詞分佈在 eVar1 和 eVar2 之間。
- 不可能對每個搜尋字詞、業務單位和客戶類別使用不同的歸因模型。

## 使用「AEP 資料準備」解決報告套裝之間的結構描述差異

Experience Platform 資料準備功能與 Analytics 來源連接器整合，可用於解決上述場景中說明的結構描述差異。 這會產生在 CJA 資料檢視中具有一致意義的 eVar。 (下面使用的命名慣例，可以根據您的需求加以自訂。)

1. 在為報告套裝 A 和報告套裝 B 建立源連線資料流之前，先在 AEP 中[建立新的結構描述](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=zh-Hant) (在我們的範例中將其稱為&#x200B;**「統一結構描述」**。) 將以下內容新增到結構描述中：

   | 「統一結構描述」 |
   | --- |
   | **XDM ExperienceEvent** 類別 |
   | **「Adobe Analytics ExperienceEvent 範本」**&#x200B;欄位群組 |

1. 將另一個欄位群組新增到結構描述或[建立自訂欄位群組](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=en#:~:text=To%20create%20a%20new%20field,section%20in%20the%20left%20rail)並將其新增到結構描述。 我們將建立一個新的欄位群組，並將其稱為&#x200B;**「統一欄位」**。 然後我們將以下欄位新增到新的欄位群組中：

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

1. 現在為 CJA 建立&#x200B;**「所有報告套裝」**&#x200B;連線，結合資料集 A 和資料集 B。

1. 在 CJA 中建立&#x200B;**「全域檢視」**&#x200B;資料檢視。 忽略原始 eVar 欄位，僅包括「統一欄位」欄位群組中的欄位。

   CJA 中的&#x200B;**「全域檢視」**&#x200B;資料檢視：

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
>「統一欄位」自訂欄位群組和關聯的欄位對應可以隨時新增到現有的「Analytics 來源連接器」資料流和資料集。 但是，這只會影響未來的資料。

## 不只是報告套裝

「資料準備」結合資料集與不同結構描述的能力，超越了 Analytics 報告套裝。 假設您有兩個包含以下資料的資料集：

| 資料集 A = 透過 Analytics 來源連接器的 Analytics 報告套裝 |
| --- |
| `eVar1` => 客戶類別 |

| 資料集 B = 呼叫中心資料 |
| --- |
| Some_field => 客戶類別 |

使用「資料準備」，您可以將 Analytics 資料中 eVar 1 的「客戶類別」結合呼叫中心資料中 Some_field 的「客戶類別」。 以下是可行方法之一。 同樣地，您可以根據需求更改命名慣例。

1. 在 AEP 中建立結構描述。 將以下內容新增到結構描述中：

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

1. 建立結合了資料集 A 和資料集 B 的 CJA 連線。

1. 使用您剛剛建立的 CJA 連線，在 CJA 中建立資料檢視。 忽略原始 eVar 欄位，僅包括「客戶資訊」欄位群組中的欄位。

   CJA 中的資料檢視：

   | 來源欄位 | 包括在資料檢視中？ |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | 否 |
   | \_experience.analytics.customDimensions.eVars.eVar2 | 否 |
   | _\&lt;路徑>_.Customer_category | 是 |

## 「資料準備」與「元件 ID」的比較

如上所述，「資料準備」可讓您將不同的欄位對應到多個 Adobe Analytics 報告套裝中。 當您想要將來自多個資料集的資料組合到單一 CJA 連線時，這在 CJA 中很有用。 但是，如果您打算將報告套裝保留在單獨的 CJA 連線中，但希望在這些連線和資料檢視中使用一組報告，則變更 CJA 中的基礎「元件 ID」提供了即使結構描述不同，也能讓報告相容的方法。如需詳細資訊，請參閱[元件設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html?lang=zh-Hant)。

變更「元件 ID」是僅限 CJA 的功能，不會影響從 Analytics 來源連接器傳送到「即時客戶個人檔案」和 RTCDP 的資料。
