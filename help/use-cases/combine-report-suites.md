---
title: 將報表套件與不同架構組合
description: 瞭解如何使用資料準備將報告套件與不同架構組合
source-git-commit: 02483345326180a72a71e3fc7c60ba64a5f8a9d6
workflow-type: tm+mt
source-wordcount: '1308'
ht-degree: 3%

---


# 將報表套件與不同架構組合

的 [分析源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant) 將Adobe Analytics的報告套件資料帶入Adobe Experience Platform(AEP)，供Real-time Customer Data Platform和Customer Journey Analytics(CJA)等AEP應用程式使用。 引入AEP的每個報告套件都配置為單個源連接資料流，每個資料流連接都配置為AEP資料湖中的資料集。 分析源連接器為每個報告套件建立一個資料集。

CJA客戶使用 [連接](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hant) 將AEP資料湖的資料集合到CJA的Analysis Workspace。 但是，在連接中組合報表套件時，需要使用AEP解決報表套件之間的架構差異 [資料準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hant) 功能。 目的是確保道具和eVars等Adobe Analytics變數在《中非合作法》中具有一致的含義。

## 報告套件之間的架構差異有問題

假設您的公司要將來自兩個不同報表套件的資料帶入AEP供CJA使用，並假設兩個報表套件的架構有差異：

| 報告套件A | 報告套件B |
| --- | --- |
| eVar1 =搜索詞 | eVar1 =業務單位 |
| eVar2 =客戶類別 | eVar2 =搜索詞 |

為了簡單起見，假設這是兩個報告套件唯一定義的eVar。

此外，假定您執行以下操作：

- 建立接收的分析源連接（不使用資料準備） **報告套件A** 進入AEP資料湖 **資料集A**。
- 建立接收的分析源連接（不使用資料準備） **報告套件B** 進入AEP資料湖 **資料集B**。
- 建立 [CJA連接](/help/connections/create-connection.md) 調用 **所有報表套件** 資料集A和資料集B的組合。
- 建立 [CJA資料視圖](/help/data-views/create-dataview.md) 調用 **全局視圖** 基於「所有報告套件」連接。

如果不使用資料準備來解決資料集A和資料集B之間的架構差異，則「全局視圖」資料視圖中的eVars將包含以下值的混合：

| CJA中的全局視圖資料視圖 |
| --- |
| eVar1 =>搜索詞和業務單元的組合 |
| eVar2 =>客戶類別和搜索條款的組合 |

這種情況導致對eVar1和eVar2提出毫無意義的報告：

- eVar欄位包含具有不同語義含義的值的混合。
- 搜索項在eVar1和eVar2之間分發。
- 不可能對搜索條款、業務單位和客戶類別中的每個使用不同的屬性模型。

## 使用AEP資料準備解決報表套件之間的架構差異

Experience Platform資料準備功能與分析源連接器整合，可用於解決上述方案中描述的架構差異。 這在CJA資料視圖中產生具有一致含義的eVars。 （可以根據您的需要自定義下面使用的命名約定。）

1. 在為報表套件A和報表套件B建立源連接資料流之前， [建立自定義欄位組](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=en#:~:text=To%20create%20a%20new%20field,section%20in%20the%20left%20rail.) 在AEP(我們叫它 **統一欄位** 在示例中)，其中包含以下欄位：

   | &quot;統一欄位&quot;自定義欄位組  |
   | --- |
   | 搜尋字詞 |
   | 業務單位 |
   | 客戶類別 |

1. [建立新架構](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=en) 在AEP(我們叫它 **統一架構** 以我們為例。) 將以下欄位組添加到架構：

   | 「統一架構」的欄位組 |
   | --- |
   | XDM體驗事件 |
   | Adobe Analytics體驗活動模板 |
   | 統一欄位 |

   建立源連接資料流時 **報告套件A**&#x200B;選中 **統一架構** 用於資料流。

1. 按如下方式添加自定義映射：

   | 報表套件A源欄位 | 「統一欄位」欄位組中的目標欄位 |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Search_term |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

   >[!NOTE]
   >
   >目標欄位的XDM路徑將取決於您如何設定自定義欄位組。

1. 建立源連接資料流時 **報告套件B**&#x200B;中，選擇 **統一架構** 用於資料流。

   工作流顯示兩個欄位存在描述符名稱衝突。 這是因為，在報告套件B中，eVar1和eVar2的描述符與在報告套件A中的描述符不同。但我們已經知道了這一點，因此我們可以安全地忽略衝突並使用自定義映射，如下所示：

   | 報表套件B源欄位 | 「統一欄位」欄位組中的目標欄位 |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.業務_單位 |
   | _experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Search_term |

1. 現在建立 **所有報表套件** 資料集A和資料集B組合。

1. 建立 **全局視圖** 資料視圖。

   忽略原始eVar欄位，並僅包括「統一欄位」欄位組中的欄位。

   CJA中的全局視圖資料視圖：

   | 源欄位 | 是否包括在資料視圖中？ |
   | --- | --- | 
   | \_experience.analytics.customDimensions.eVars.eVar1 | 無 |
   | \_experience.analytics.customDimensions.eVars.eVar2 | 無 |
   | _\&lt;path>_.Search_term | 有 |
   | _\&lt;path>_.Customer_category  | 有 |
   | _\&lt;path>_.業務_單位 | 有 |

   您現在已將eVar1和eVar2從源報告套件映射到三個新欄位。 請注意，使用資料準備映射的另一個優勢是，目標欄位現在基於語義有意義的名稱（搜索術語、業務單元、客戶類別），而不是意義不大的eVar名稱(eVar1、eVar2)。

   >[!NOTE]
   >
   >可隨時將統一欄位自定義欄位組和關聯欄位映射添加到現有分析源連接器資料流和資料集。 但是，這僅影響未來資料。

## 不只是報告套件

Data Prep將資料集與不同架構組合的功能超出了分析報告套件。 假設您有兩個包含以下資料的資料集：

| 資料集A =通過分析源連接器分析報告套件 |
| --- |
| `eVar1` =>客戶類別 |

| 資料集B =呼叫中心資料 |
| --- |
| Some_field =>客戶類別 |

使用資料準備，您可以將分析資料中eVar1中的客戶類別與呼叫中心資料中Some_field中的客戶類別組合。 你可以這樣做。 同樣，可以根據您的需要更改命名約定。

1. 建立自定義欄位組：

   | 「客戶資訊」自定義欄位組  |
   | --- |
   | 客戶類別 |

1. 在AEP中建立架構。 將以下欄位組添加到架構：

   | 「擴展架構」的欄位組 |
   | --- | 
   | XDM體驗事件 |
   | Adobe Analytics體驗活動模板 |
   | 客戶資訊 |

1. 為建立資料流時 **資料集A**&#x200B;選中 **擴展架構** 作為架構。

1. 按如下方式添加自定義映射：

   | 資料集A源欄位 | 「客戶資訊」欄位組中的目標欄位 |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

1. 為建立資料流時 **資料集B**&#x200B;中，選擇 **擴展架構** 作為架構。

1. 按如下方式添加自定義映射：

   | 資料集B源欄位 | 「客戶資訊」欄位組中的目標欄位 |
   | --- | --- |
   | _\&lt;path>_.Some_field | _\&lt;path>_.Customer_category |

   建立組合了資料集A和資料集B的CJA連接。使用剛建立的CJA連接在CJA中建立資料視圖。 忽略原始eVar欄位，並僅包括「客戶資訊」欄位組中的欄位。

   CJA中的資料視圖：

   | 源欄位 | 是否包括在資料視圖中？ |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | 無 |
   | \_experience.analytics.customDimensions.eVars.eVar2 | 無 |
   | _\&lt;path>_.Customer_category | 有 |

## 資料準備與元件ID

如上所述，Data Prep允許您跨多個Adobe Analytics報告套件將不同的欄位映射在一起。 在CJA中，如果要將來自多個資料集的資料合併到單個CJA連接中，這將很有幫助。 但是，如果您打算將報告套件保留在單獨的CJA連接中，但希望跨這些連接和資料視圖使用一組報告，則更改CJA中的基礎元件ID提供了使報告相容的方法，即使架構不同。 請參閱 [元件設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html?lang=en) 的子菜單。

更改元件ID是僅CJA功能，不會影響從分析源連接器發送到即時客戶配置檔案和RTCDP的資料。

