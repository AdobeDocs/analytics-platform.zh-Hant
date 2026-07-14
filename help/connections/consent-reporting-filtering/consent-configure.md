---
title: 設定同意報告和篩選
description: 瞭解如何使用布建精靈來為Customer Journey Analytics中的連線啟用同意報表和選用的擷取時間篩選。
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: eb00932f-4d46-46bc-b1d8-10de7588db8did: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2: id: ffe2fd81-0630-49b3-a33b-4b8899e89c51id: d3fb138f-79e4-4a81-aedb-76dd93560085
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: eafeab50e86b3e98f372c70a0fd43494015ca002
workflow-type: tm+mt
source-wordcount: 759
ht-degree: 2%

---

# 設定同意報告和篩選

系統管理員可以針對一或多個連線啟用同意報告及（選擇性）同意篩選。 如需概述資訊，請參閱[同意報告和篩選概述](/help/connections/consent-reporting-filtering/consent-overview.md)。

>[!IMPORTANT]
>
>同意篩選會排除內嵌時未經同意的訪客資料。 透過篩選排除的資料不會儲存在Customer Journey Analytics中，而且無法針對過去的日期復原。 啟用篩選之前，請仔細檢閱行銷動作選項。

## 先決條件

在設定同意報告和篩選之前，請確定：

* 您在Customer Journey Analytics中擁有系統管理員許可權。
* 您要使用的沙箱包含設定檔資料集，其中的`consentPoliciesIDMap`欄位中有同意原則成員資格資料。
* 您要設定的連線已經存在。 如需詳細資訊，請參閱[建立或編輯連線](/help/connections/create-connection.md)。

## 建立設定

當您建立同意報表和篩選的設定時，請選取包含同意原則成員資格資料的沙箱和設定檔資料集，選擇要設定的連線或連線，並選擇是否篩選每個行銷動作的資料。 Customer Journey Analytics接著會自動建立同意原則查詢資料集和同意原則元件。

若要建立同意報表和篩選設定：

1. 在Customer Journey Analytics中，選取&#x200B;**[!UICONTROL 資料管理]** > **[!UICONTROL 同意報告和篩選]**。

1. 選取「**[!UICONTROL 建立設定]**」。

1. 在&#x200B;**[!UICONTROL 詳細資料]**&#x200B;區段中，指定下列資訊：

   | 欄位 | 說明 |
   |---------|----------|
   | **[!UICONTROL 名稱]** | 指定組態的名稱。 |
   | **[!UICONTROL 沙箱]** | 選取Experience Platform沙箱，其中包含設定檔資料集和您的同意原則成員資格資料。 <p>每個沙箱最多存在一個同意原則查詢資料集。 相同沙箱中的多個設定共用相同的查詢資料集。</p> |

1. 在&#x200B;**[!UICONTROL 設定檔資料集]**&#x200B;區段中，選取包含您要報告的同意原則成員資格資料（`consentPoliciesIDMap`欄位）的設定檔資料集。 此設定檔資料集已新增至您選取的連線。

1. 在&#x200B;**[!UICONTROL 連線]**&#x200B;區段中，選取&#x200B;**[!UICONTROL 選取連線]**，選取要設定的一或多個連線旁的核取方塊，然後選取&#x200B;**[!UICONTROL 使用連線]**。

   同意報表和篩選會在連線層級套用。 已設定連線下的所有資料檢視都會繼承相同的行為。

1. （選擇性）在&#x200B;**[!UICONTROL 篩選]**&#x200B;區段中，您可以為下列行銷動作啟用篩選：

   >[!NOTE]
   >
   >取消選取兩個切換即可在不篩選的情況下啟用同意報告。
   >
   >當啟用行銷動作的篩選功能時，Customer Journey Analytics只有在訪客符合套用至該行銷動作的&#x200B;**所有**&#x200B;同意原則時，才會擷取訪客的資料。 如需詳細資訊，請參閱[同意報告和篩選概觀](/help/connections/consent-reporting-filtering/consent-overview.md)中的[同意篩選](/help/connections/consent-reporting-filtering/consent-overview.md#consent-filtering)。

   | 行銷動作 | 說明 |
   |---------|----------|
   | **[!UICONTROL Analytics]** | 在Analysis Workspace中篩選用於標準Customer Journey Analytics報表的資料。 |
   | **[!UICONTROL 資料科學]** | 篩選用於進階分析、機器學習和資料科學使用案例的資料。 |

1. 選取&#x200B;**[!UICONTROL 建立]**&#x200B;以建立組態。

   Customer Journey Analytics自動：

   * 將所選的設定檔資料集新增到連線。
   * 為沙箱建立同意原則查詢資料集（如果尚未存在），並從Experience Platform同步原則名稱和說明。
   * 將同意原則元件（維度、量度和衍生欄位）新增至已設定連線內的資料檢視。
   * 將&#x200B;**同意**&#x200B;內部標籤套用至新元件，以便在資料檢視中篩選它們。 如需內部標籤的詳細資訊，請參閱[標籤和原則](/help/data-views/data-governance.md)。

1. 組態完成後，[在資料檢視](#view-consent-policy-components-in-the-data-view)中檢視同意原則元件，以驗證它們是否可用。

## 在資料檢視中檢視同意原則元件

在您[建立組態](#create-a-configuration)之後，您可以驗證同意原則元件是否已新增至所設定連線下的資料檢視。

若要在資料檢視中檢視同意原則元件，您必須是資料檢視所指派之產品設定檔的產品設定檔管理員。 如需詳細資訊，請參閱[存取控制](/help/technotes/access-control.md)。

若要在資料檢視中檢視同意原則元件：

1. 在 Customer Journey Analytics 中，選取「**[!UICONTROL 資料管理]**」>「**[!UICONTROL 資料釋圖]**」。

1. 開啟與已設定連線相關聯的資料檢視。

1. 在&#x200B;**[!UICONTROL 維度]**&#x200B;區段中，下列維度現在應該可供使用：

   * **[!UICONTROL 同意原則ID]**

   * **[!UICONTROL 原則名稱]**

   * **[!UICONTROL 原則描述]**

1. 在&#x200B;**[!UICONTROL 量度]**&#x200B;區段中，下列量度現在應該可供使用：

   * **[!UICONTROL 有同意的訪客]**

   * **[!UICONTROL 同意的事件]**

   * **[!UICONTROL 唯一的同意原則]**

   <!-- TODO: Add a screenshot of the consent policy components in the data view (assets/consent-components-dataview.png). -->

1. 在Analysis Workspace中使用同意原則元件。

   有權存取Analysis Workspace中資料檢視的使用者現在可以檢視新元件，並在其分析中使用它們。 如需有關如何在Analysis Workspace中使用同意原則元件的資訊，請參閱[分析同意原則資料](/help/connections/consent-reporting-filtering/consent-analyze.md)。
