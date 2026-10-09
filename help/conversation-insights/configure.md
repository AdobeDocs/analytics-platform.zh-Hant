---
title: 建立或編輯對話深入分析設定
description: 瞭解如何設定「交談見解」設定。
solution: Customer Journey Analytics
feature: AI Tools
role: Admin, User
autotag-review: '2026-10-02T07:00:50.074Z'
TQID: 'https://experienceleague.adobe.com/yw5FGvOYbxxpcm3CfDyKed1-T7sGFTIRkvRz3Q4xj4I'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ae3aff40-b2f6-4df1-8c01-0b0720d1510f
    internal-label: AI Tools
  - id: d7a261eb-f9ac-4dd6-bd60-1637efcd3d36
    internal-label: Conversation Insights (CJA)
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: cd12bd7f6943be6c58694af1374d32a1639d1578
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 16%
---
# 建立或編輯組態

對話深入解析可讓您從提供給客戶的代理程式體驗中分析對話。 這些代理程式體驗可以基於大型語言模型(LLM)或基於人類對話。 例如，和客戶或客服中心互動的聊天機器人紀錄。
透過交談深入分析，您可以瞭解代理程式對實際使用者結果的影響。

透過「交談見解」設定介面，您可以快速建立或編輯設定和相關的成品（連線、資料檢視等）。

當您建立或編輯對話深入分析設定時，需指定沙箱以及包含提示、回應和意見回饋資料的事件資料集。 您也可以選取要新增這些資料集的Customer Journey Analytics連線。 以及您要新增「對話深入分析」量度和維度的資料檢視。

只有系統管理員可以建立或編輯交談見解設定。

您可以從[交談見解設定介面](./manage.md)建立或編輯設定。

## 還原遺失的混合資料集

如果您編輯組態，而且已針對組態產生的混合資料集已不存在，請選取&#x200B;**[!UICONTROL 還原]**&#x200B;以重新產生混合資料集。


## 設定步驟

針對每個設定：

1. 在&#x200B;**[!UICONTROL 詳細資料]**&#x200B;區段中，指定下列資訊：

   ![交談深入分析詳細資料](assets/conversation-insights-configuration-details.png)

   | 欄位 | 說明 |
   |---------|----------|
   | **[!UICONTROL 名稱]** | 指定組態的名稱。 |
   | **[!UICONTROL 沙箱]** | 選取Experience Platform沙箱，其中包含您要新增至連線的提示、回應和意見反應事件資料集。 |

1. 在&#x200B;**[!UICONTROL 資料集]**&#x200B;區段中，指定下列資訊：

   ![交談深入分析資料集](assets/conversation-insights-configuration-datasets.png)

   | 欄位 | 說明 |
   |---------|----------|
   | **[!UICONTROL 提示事件資料集]** | 選取包含提示事件資料的資料集。 |
   | **[!UICONTROL 回應事件資料集]** | 選取包含回應事件資料的資料集。 |
   | **[!UICONTROL 意見反應事件資料集]** | 選取包含意見事件資料的資料集。 |

1. 在&#x200B;**[!UICONTROL 連線]**&#x200B;區段中，如果尚未設定連線，請使用&#x200B;**[!UICONTROL 選取連線]**&#x200B;來選取連線。

   ![交談深入分析連線](assets/conversation-insights-configuration-connection.png)

   如果已設定連線，請選取![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 編輯]**&#x200B;以選取其他連線。

   ![交談深入分析編輯連線](assets/conversation-insights-configuration-edit-connection.png)

   在&#x200B;**[!UICONTROL 選取連線]**&#x200B;對話方塊中：

   ![交談深入分析選取連線](assets/conversation-insights-configuration-select-connection.png)

   1. 選取您要新增提示、回應和意見反應事件資料集的連線旁的核取方塊。
   1. 選取&#x200B;**[!UICONTROL 使用連線]**。

   * 若要搜尋要選取的連線清單，請使用![搜尋](/help/assets/icons/Search.svg)欄位。
   * 若要設定要在表格中顯示哪些欄，請選取![ColumnSetting](/help/assets/icons/ColumnSetting.svg)。 在&#x200B;**[!UICONTROL 自訂資料表]**&#x200B;對話方塊中，選取要顯示的資料行。 然後選取&#x200B;**[!UICONTROL 套用]**。

1. 在&#x200B;**[!UICONTROL 資料檢視]**&#x200B;區段中，如果尚未設定任何資料檢視，請選取&#x200B;**[!UICONTROL 選取資料檢視]**&#x200B;以選取資料檢視。

   如果已設定資料檢視，請選取![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 編輯資料檢視選擇]**&#x200B;以重新設定資料檢視選擇。

   在&#x200B;**[!UICONTROL 選取多個資料檢視]**&#x200B;對話方塊中：

   ![交談深入分析選取資料檢視](assets/conversation-insights-configuration-select-data-views.png)

   1. 選取一或多個要用於「交談見解」設定的資料檢視。

   1. 選取&#x200B;**[!UICONTROL 使用資料檢視]**&#x200B;以使用資料檢視。 選取「取消」，即可取消。

   * 若要在資料檢視清單中搜尋以從中選取，請使用![搜尋](/help/assets/icons/Search.svg)欄位。
   * 若要設定要在表格中顯示哪些欄，請選取![ColumnSetting](/help/assets/icons/ColumnSetting.svg)。 在&#x200B;**[!UICONTROL 自訂資料表]**&#x200B;對話方塊中，選取要顯示的資料行。 然後選取&#x200B;**[!UICONTROL 套用]**。

1. 若要完成設定：

   * 針對未建立的新組態選取&#x200B;**[!UICONTROL 捨棄]**。

   * 針對您想要儲存但不想要建立成品（例如資料檢視的更新）的新設定，選取&#x200B;**[!UICONTROL 儲存以供稍後使用]**。 您可以稍後重新造訪設定，並完成設定的實際建立。

   * 選取&#x200B;**[!UICONTROL 建立]**&#x200B;以建立新組態。

   * 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存修改的組態。

   * 選取&#x200B;**[!UICONTROL 還原]**&#x200B;以還原組態，為組態重新產生新的混合資料集。

   * 選取&#x200B;**[!UICONTROL 結束]**&#x200B;以忽略組態的任何變更。


## 資料檢視驗證

您在[設定步驟](#configuration-steps)中設定的資料檢視，在[資料檢視](/help/data-views/manage-dataviews.md)中具有&#x200B;**[!UICONTROL 交談深入分析]**&#x200B;作為&#x200B;**[!UICONTROL 整合]**&#x200B;的值。

對於每個已設定的資料檢視：

* **容器**： [容器索引標籤](/help/data-views/create-dataview.md#containers)包含新的&#x200B;**[!UICONTROL 容器名稱]**： **[!UICONTROL 交談]**，具有&#x200B;**[!UICONTROL 顯示名稱]**： **[!UICONTROL 容器]**&#x200B;作為額外的&#x200B;**[!UICONTROL 系統]** **[!UICONTROL 容器型別]**。
* **元件**：您會看到其他結構描述欄位資料夾。 例如：agentExperience和conversation。 此外，系統會自動新增下列元件：

  | 量度 | 結構描述資料類型 | 結構描述路徑 |
  |---|---|---|
  | 客戶回饋 | 字串 | eventType |
  | 正面情緒 | 字串 | 衍生欄位 |
  | 推薦 | 字串 | eventType |
  | 航程 | 字串 | eventType |

  | 維度 | 結構描述資料類型 | 結構描述路徑 |
  |---|---|---|
  | 代理 ID | 字串 | `agenticExperience.agents.agentID` |
  | 代理人名稱 | 字串 | `agenticExperience.agents.name` |
  | Concierge 名稱 | 字串 | `agenticExperience.name` |
  | Concierge 版本 | 字串 | `agenticExperience.version` |
  | 對話 ID | 字串 | `conversation.conversationID` |
  | 對話名稱 | 字串 | `conversation.conversationName` |
  | 交談訊號名稱 | 字串 | `conversation.signals.name` |
  | 交談摘要布林值 | 布林值 | `conversation.signals.values.booleanValue` |
  | 交談摘要信賴度 | 雙精度浮點數 | `conversation.signals.values.confidence` |
  | 交談摘要中繼資料索引鍵 | 字串 | `conversation.signals.values.metadata.key` |
  | 交談摘要數值 | 雙精度浮點數 | `conversation.signals.values.numberValue` |
  | 交談摘要限定詞 | 字串 | `conversation.signals.values.qualifiers` |
  | 對話語氣訊號 | 字串 | `conversation.signals.attributes.tones.values` |
  | 環境 | 字串 | `agenticExperience.environment` |
  | 回饋分類 | 字串 | 衍生欄位 |
  | 回饋評等分類 | 字串 | `conversation.feedback.rating.classification` |
  | 回饋區段用途 | 字串 | `conversation.feedback.raw.purpose` |
  | 回饋來源 | 字串 | `conversation.feedback.source` |
  | 短語 | 字串 | `conversation.signals.attributes.subjects.values.phrase` |
  | 回答原始文字 | 字串 | `conversation.response.raw.text` |
  | 回答來源 | 字串 | `conversation.response.source` |
  | 情感分類 | 字串 | 衍生欄位 |
  | 技能名稱 | 字串 | `agenticExperience.agents.skills.name` |
  | 技能版本 | 字串 | `agenticExperience.agents.skills.version` |
  | 值 | 字串 | `agenticExperience.agents.skills.parameters.value` |


<!--

1. In the Data views dialog, select the checkbox next to one or more data views that you want to use when analyzing Experience Platform audience data within Analysis Workspace. These data views are automatically configured with Experience Platform audience data for reporting.

1. Select **[!UICONTROL Use data views]**.

1. Select **[!UICONTROL Create]** to create the configuration.

   >[!IMPORTANT]
   >
   >Because the profile dataset is updated once per day, audiences are available in Customer Journey Analytics data views on the day after you create the audience analysis configuration.


1. After 24 hours, [view audience dimensions in the data view](#view-audience-dimensions-in-the-data-view) to verify that the audience dimensions are available in the data views that you selected. 


## View audience dimensions in the data view

After you [create an audience analysis configuration](#create-an-audience-analysis-configuration), you can verify that audience dimensions were added to the data views that you selected during the configuration.

To view audience dimensions in the data view, you must be a product profile administrator for the product profile that the data view is assigned to. For more information, see [Access control](/help/technotes/access-control.md).

To view the audience analysis dimensions in the data view:

1. In Customer Journey Analytics, select **[!UICONTROL Data Management]** > **[!UICONTROL Data views]**.

1. In the **[!UICONTROL Dimensions]** section, the following dimensions should now be available:

   * **[!UICONTROL Audience Name]**

   * **[!UICONTROL Audience Origin]**

   * **[!UICONTROL Exited Audience Origin]**

   * **[!UICONTROL Exited Audience Name]**

   Note that each of these dimensions was added to the profile dataset that is associated with the merge policy that you selected during the audience analysis configuration, and each was added to the new lookup dataset that was created.

   ![Audience dimensions available in the data view](assets/audience-analysis-dataview-dataset.png)

1. Use the audience analysis dimensions in Analysis Workspace. 

   Users who have access to use the data view in Analysis Workspace can now see the new dimensions and use them in their analyses. For information about how to use the audience analysis dimensions in Analysis Workspace, see [Analyze Experience Platform audiences in Customer Journey Analytics](/help/connections/audience-analysis/analyze-audiences.md).

-->