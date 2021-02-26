---
description: 在 Analysis Workspace 中劃分維度和維度項目。
keywords: Analysis Workspace
title: 劃分維度
topic: Reports and Analytics
uuid: 0b888e26-f201-4405-99f9-755b3ee6cd18
translation-type: tm+mt
source-git-commit: 1c82c7c2e61c170b6eb05bfda0c7a79e5a13c4e1
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 96%

---


# 劃分維度

>[!NOTE]
>
>您正在檢視 Customer Journey Analytics 中 Analysis Workspace 的相關文件，其功能集與傳統 Adobe Analytics 中的 [Analysis Workspace 略有不同](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html)。[深入了解...](/help/getting-started/cja-aa.md)

在 Analysis Workspace 中劃分維度和維度項目。

您可針對特定需求，以無限方式劃分資料；使用相關量度、維度、區段、時間表及其他分析劃分值來建立查詢。

1. [建立專案](/help/analysis-workspace/home.md)並搭配資料表格。
1. 在資料表格中，以滑鼠右鍵按一下某個條列項目，並選取&#x200B;**[!UICONTROL 劃分]** > *`<item>`*。

   ![步驟結果](assets/fa_data_table_actions.png)

   您可以跨所選時段，依維度項目或受眾區段來劃分量度。您也可以更深入鑽研至更詳細的層級。

   >[!NOTE]
   >
   >表格中顯示的劃分數目上限為 200。匯出劃分時，此限制會提高。

**影片：Analysis WorkspaceDimension**

>[!VIDEO](https://video.tv.adobe.com/v/23971)

**影片：Dimension劃分**

>[!VIDEO](https://video.tv.adobe.com/v/23969)

## 將歸因模型套用到資料劃分

表格中的任何劃分也可套用任何歸因模型。此歸因模型可與父欄相同或不同。舉例來說，您可以在「行銷管道」維度中分析線性訂單，但將「U 形訂單」套用至管道中的特定追蹤代碼。若要編輯套用到劃分的歸因模型，請將滑鼠移到劃分模型上方，然後按一下&#x200B;**[!UICONTROL 編輯]**：

![劃分設定](assets/breakdown_settings.png)
