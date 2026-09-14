---
title: 設定交談深入分析設定
description: 瞭解如何設定「交談見解」設定。
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hold: true
source-git-commit: 8e446c15e998e660b42a09681fe78b885711e41f
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 8%
---
# 設定交談見解設定


對話深入分析可讓您大規模分析對話(來自大型語言模型(LLM)或人類)，並在整個客戶歷程中提供這些對話的內容。 透過交談見解，您可以瞭解代表對實際使用者結果的影響。


## 建立或編輯設定

當您建立或編輯對話深入分析設定時，需指定沙箱以及包含提示、回應和意見回饋資料的事件資料集。 您也可以選取要新增這些資料集的Customer Journey Analytics連線。 以及您要新增「對話深入分析」量度和維度的資料檢視。

只有系統管理員可以建立或編輯交談見解設定。

您可以從[交談見解設定介面](./conversation-insights-manage.md)建立或編輯設定。

### 還原遺失的混合資料集

如果您編輯組態，而且已針對組態產生的混合資料集已不存在，請選取&#x200B;**[!UICONTROL 還原]**&#x200B;以重新產生混合資料集。


### 設定步驟

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
   * 若要設定在表格中顯示哪些欄，請選取「![欄設定](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)」。 在&#x200B;**[!UICONTROL 自訂資料表]**&#x200B;對話方塊中，選取要顯示的資料行。 然後選取&#x200B;**[!UICONTROL 套用]**。

1. 在&#x200B;**[!UICONTROL 資料檢視]**&#x200B;區段中，如果尚未設定任何資料檢視，請選取&#x200B;**[!UICONTROL 選取資料檢視]**&#x200B;以選取資料檢視。

   如果已設定資料檢視，請選取![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 編輯資料檢視選擇]**&#x200B;以重新設定資料檢視選擇。

   在&#x200B;**[!UICONTROL 選取多個資料檢視]**&#x200B;對話方塊中：

   ![交談深入分析選取資料檢視](assets/conversation-insights-configuration-select-data-views.png)

   1. 選取一或多個要用於「交談見解」設定的資料檢視。

   1. 選取&#x200B;**[!UICONTROL 使用資料檢視]**&#x200B;以使用資料檢視。 選取「取消」，即可取消。

   * 若要在資料檢視清單中搜尋以從中選取，請使用![搜尋](/help/assets/icons/Search.svg)欄位。
   * 若要設定在表格中顯示哪些欄，請選取「![欄設定](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)」。 在&#x200B;**[!UICONTROL 自訂資料表]**&#x200B;對話方塊中，選取要顯示的資料行。 然後選取&#x200B;**[!UICONTROL 套用]**。

1. 若要完成設定：

   * 針對未建立的新組態選取&#x200B;**[!UICONTROL 捨棄]**。

   * 針對您想要儲存但不想要建立成品（例如資料檢視的更新）的新設定，選取&#x200B;**[!UICONTROL 儲存以供稍後使用]**。 因此，您可以稍後重新造訪設定，並完成設定的實際建立。

   * 選取&#x200B;**[!UICONTROL 建立]**&#x200B;以建立新組態。

   * 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存修改的組態。

   * 選取&#x200B;**[!UICONTROL 還原]**&#x200B;以還原組態，為組態重新產生新的混合資料集。

   * 選取&#x200B;**[!UICONTROL 結束]**&#x200B;以忽略組態的任何變更。


## 資料檢視驗證

（說明您從相關資料集中看到的量度和維度）


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