---
title: 設定同意報告和篩選
description: 瞭解如何在Customer Journey Analytics中建立設定，以針對連線啟用同意報告和選用的擷取時間篩選。
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 4661a066f90991e6fb149c6909ef4a9f75cf02ac
workflow-type: tm+mt
source-wordcount: 1326
ht-degree: 20%

---

# 設定同意報告和篩選 {#configure-consent-reporting}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-merge-policy"
>title="合併原則"
>abstract="合併原則會將來自多個資料集的輪廓資料合併到統一的客戶輪廓中，用於建立客群。 選取與包含您要報告的同意原則成員資格資料（`consentPoliciesIDMap`欄位）的設定檔資料集對應的合併原則。 或洽詢您的資料團隊，了解各合併原則與哪些客群相關聯。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-sandbox"
>title="沙箱"
>abstract="選取包含正確 Experience Platform 輪廓資料集的沙箱。 這些資料集必須包含您要在 Analysis Workspace 中報告的同意資料。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-person-id"
>title="人員 ID"
>abstract="從模型式結構描述中選取代表個人 ID 的欄位。 選取範圍僅限於結構描述中標示為「身分識別」且確實具有身分識別命名空間的欄位清單。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-identity-namespace"
>title="使用主要身分識別命名空間"
>abstract="啟用此選項，讓 Customer Journey Analytics 在標示 primary=true 屬性的「身分對應」中尋找身分識別，並將其做為該列的人員 ID。 此身分識別在 Experience Platform 中是用於資料分割的主索引鍵。 <br/>如果您讓此選項維持停用，請從下方的「身分識別命名空間」欄位中選取命名空間。 Customer Journey Analytics 會針對此命名空間索引鍵搜尋每一列的身分識別圖，並使用該命名空間底下的身分識別作為該列的個人 ID。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-enable-reporting"
>title="啟用報告"
>abstract="啟用此選項以使用Analysis Workspace來報告連線中可用的同意資料。 同意原則維度和量度會新增至您選取的資料檢視。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-enable-filtering"
>title="啟用篩選"
>abstract="啟用此選項可排除非同意的訪客資料不會擷取到Customer Journey Analytics中。 啟用後，只有當訪客符合以下啟用的所有同意原則時，才會擷取訪客的資料。 <br>此選項適用於需要在擷取時排除非同意訪客資料的組織。"

<!-- markdownlint-enable MD034 -->

系統管理員可以針對一或多個連線啟用同意報告及（選擇性）同意篩選。 如需概述資訊，請參閱[同意報告和篩選概述](/help/connections/consent-reporting-filtering/consent-overview.md)。

>[!IMPORTANT]
>
>同意篩選會排除內嵌時未經同意的訪客資料。 透過篩選排除的資料不會儲存在Customer Journey Analytics中，而且無法針對過去的日期復原。 啟用篩選之前，請仔細檢閱行銷動作選項。

## 建立設定

當您建立同意報告和篩選的設定時，您會選取包含同意原則成員資格資料的沙箱和合併原則、選擇要設定的連線或連線，以及選擇是否要篩選每個行銷動作的資料。 Customer Journey Analytics接著會自動建立同意原則查詢資料集和同意原則元件。

若要建立同意報表和篩選設定：

1. 在Customer Journey Analytics中，選取&#x200B;**[!UICONTROL 資料管理]** > **[!UICONTROL 同意報告和篩選]**。

1. 選取「**[!UICONTROL 建立設定]**」。

   ![同意設定頁面](assets/consent-configure.png)

1. 在&#x200B;**[!UICONTROL 詳細資料]**&#x200B;區段中，指定下列資訊：

   | 欄位 | 說明 |
   |---------|----------|
   | **[!UICONTROL 名稱]** | 指定組態的名稱。 |
   | **[!UICONTROL 沙箱]** | 選取Experience Platform沙箱，其中包含設定檔資料集和您的同意原則成員資格資料。 <p>每個沙箱最多存在一個同意原則查詢資料集。 相同沙箱中的多個設定共用相同的查詢資料集。</p> |

1. 在&#x200B;**[!UICONTROL 設定檔資料集]**&#x200B;區段的&#x200B;**[!UICONTROL 合併原則]**&#x200B;欄位中，選取與包含您想要報告的同意原則成員資格資料（`consentPoliciesIDMap`欄位）的設定檔資料集相對應的合併原則。 當您啟用同意報告時，此設定檔資料集會新增到您選取的連線（如果它尚未成為其中一部分）。<p>合併原則可決定Adobe Experience Platform如何將來自多個資料集的設定檔資料合併到統一的客戶設定檔中，以用於同意原則成員資格資料。 每天，系統都會在Experience Platform中產生這些資料的快照。 此快照提供特定時間點的靜態資料檢視，不包含任何事件資料。</p><p>如果您看到多個合併原則且不確定要選擇哪一個，請選取&#x200B;**[!UICONTROL 預設以時間為基礎]**&#x200B;的合併原則。 您也可以洽詢資料團隊，更清楚瞭解哪些同意資料與每個合併原則相關聯。</p>

1. 在&#x200B;**[!UICONTROL 連線]**&#x200B;區段中，選取&#x200B;**[!UICONTROL 選取連線]**，選取要設定的連線旁的核取方塊，然後選取&#x200B;**[!UICONTROL 使用連線]**。

   同意報表和篩選會在連線層級套用。 已設定連線下的所有資料檢視都會繼承相同的行為。

1. 在&#x200B;**[!UICONTROL 人員ID]**&#x200B;欄位中，從代表人員ID的模型架構中選取欄位。 選取範圍僅限於結構描述中標示為「身分識別」且確實具有身分識別命名空間的欄位清單。

1. 選擇是否啟用同意資料的報告。

   如需何時啟用報告的詳細資訊，請參閱[同意報告與篩選](/help/connections/consent-reporting-filtering/consent-overview.md#consent-reporting-vs-filtering)。

   若要啟用及設定報表：

   1. 在&#x200B;**[!UICONTROL 報告]**&#x200B;區段中，選取&#x200B;**[!UICONTROL 啟用報告]**。

   1. 在 Analysis Workspace 內分析 Platform 同意資料時，選取與您想要使用之連線關聯的任何資料檢視。 在&#x200B;**[!UICONTROL 資料檢視]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL 選取資料檢視]**。

   1. 在「資料檢視」對話方塊中，選取您要用於同意報告的一或多個資料檢視旁的核取方塊。 這些資料檢視會自動設定用於報告的Experience Platform同意資料。

   1. 選取&#x200B;**[!UICONTROL 使用資料檢視]**。

1. 選擇是否啟用篩選，在擷取時排除非同意的訪客。

   啟用篩選時，Customer Journey Analytics只有在訪客符合所有已啟用的同意原則時，才會擷取訪客的資料。

   如需何時啟用篩選的相關資訊，請參閱[同意報告與篩選](/help/connections/consent-reporting-filtering/consent-overview.md#consent-reporting-vs-filtering)。

   若要啟用並設定篩選：

   1. 在&#x200B;**[!UICONTROL 篩選]**&#x200B;區段中，選取&#x200B;**[!UICONTROL 啟用篩選]**&#x200B;以篩選同意資料。

   1. 啟用篩選下列一或兩個行銷動作：

      >[!NOTE]
      >
      >當啟用行銷動作的篩選功能時，Customer Journey Analytics只有在訪客符合套用至該行銷動作的&#x200B;**所有**&#x200B;同意原則時，才會擷取訪客的資料。 如需詳細資訊，請參閱[同意報告和篩選概觀](/help/connections/consent-reporting-filtering/consent-overview.md)中的[同意篩選](/help/connections/consent-reporting-filtering/consent-overview.md#consent-filtering)。

      行銷動作會繫結至您在Experience Platform中設定的資料使用標籤和原則。 如需詳細資訊，請參閱[標籤、原則和行銷動作](/help/data-views/data-governance.md)。

      | 行銷動作 | 說明 |
      | --------- | ---------- |
      | **[!UICONTROL 分析資料]** | 在Analysis Workspace中篩選用於標準Customer Journey Analytics報表的資料。 |
      | **[!UICONTROL 資料科學資料]** | 篩選用於進階分析、機器學習和資料科學使用案例的資料。 |

1. 選取&#x200B;**[!UICONTROL 建立]**&#x200B;以建立組態。

   如果您已啟用報告，Customer Journey Analytics會自動執行以下操作：

   * 將所選的設定檔資料集新增到連線。
   * 為沙箱建立同意原則查詢資料集（如果尚未存在），並從Experience Platform同步原則名稱和說明。
   * 將同意原則元件（維度、量度和衍生欄位）新增至已設定連線內的資料檢視。

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
