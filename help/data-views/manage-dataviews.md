---
title: 管理資料檢視
description: 瞭解如何管理資料檢視。
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: c5cf15ab-3eb1-4e6b-93a3-3d89694ca0ea
source-git-commit: e65dd6f71c75c06aac078c22ea7d77eed75cd381
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 10%

---

# 管理資料檢視


一旦您[建立或編輯一或多個資料檢視](/help/data-views/create-dataview.md)，您就可以在&#x200B;**[!UICONTROL 資料檢視]**&#x200B;中管理它們。

從Customer Journey Analytics的主功能表列選取&#x200B;**[!UICONTROL 資料管理]** > **[!UICONTROL 資料檢視]**。

**[!UICONTROL 資料檢視]**&#x200B;介面會顯示所有可用資料檢視的表格。

![資料檢視介面](/help/data-views/assets/data-views.png)

表格中有下列欄和圖示：

| 欄或圖示 | 說明 |
| --- | --- |
| **[!UICONTROL 名稱]** | 資料檢視的名稱。 |
| ![資訊](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | 若要檢視資料檢視的相關資訊，請選取資料檢視名稱旁的![資訊大綱](/help/assets/icons/InfoOutline.svg)。<br/>快顯視窗會顯示資料檢視的詳細資訊。 |
| ![更多內容](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | 選取「![更多](/help/assets/icons/More.svg)」開啟內容選單。您可以選取：<br/>![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 編輯]**&#x200B;以[編輯](#edit-data-views)資料檢視。<br/>![複製](/help/assets/icons/Copy.svg) **[!UICONTROL 複製]**&#x200B;到[複製資料檢視](#copy-data-views)。<br/>![刪除](/help/assets/icons/Delete.svg) **[!UICONTROL 刪除]**&#x200B;以[刪除](#delete-data-views)資料檢視。<br/>![檔案CSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL 匯出為CSV]**&#x200B;以[將資料檢視的詳細資料匯出為CSV檔案](#export-data-views-to-csv)。<br/>![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL 建立專案]**&#x200B;以[為資料檢視建立新的Workspace專案](#create-project-from-data-views)。<br/>![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 啟用Data Insights Agent]**&#x200B;以啟用Data Insights Agent的資料檢視。<br/>![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL 停用Data Insights Agent]**&#x200B;以停用Data Insights Agent的資料檢視。 |
| **[!UICONTROL 連線]** | 與資料檢視相關聯的連線名稱。 |
| **[!UICONTROL 沙箱]** | 與資料檢視相關聯的沙箱名稱。 |
| **[!UICONTROL 所有者]** | 資料檢視的所有者。 |
| **[!UICONTROL Data Insights Agent]** ![資訊大綱](/help/assets/icons/InfoOutline.svg) | 表示資料檢視的[Data Insights Agent](/help/data-analysis-ai.md)是&#x200B;**[!UICONTROL 已啟用]**&#x200B;還是&#x200B;**[!UICONTROL 已停用]**。 <br/>選取![資訊大綱](/help/assets/icons/InfoOutline.svg)以在您的資料檢視中顯示含有&#x200B;**[!UICONTROL Data Insights Agent狀態]**&#x200B;的快顯視窗。 <br/>![Data Insights Agent使用量](/help/data-views/assets/data-views-dia-status.png) |
| **[!UICONTROL 整合]** | 列出與其他解決方案的整合。 例如： Adobe對象分析、Content Analytics、Brand Concierge、Journey Optimizer、GenStudio和使用情況分析。 |
| **[!UICONTROL 在 CJA 中使用]** | 指出資料檢視是否用於Customer Journey Analytics。 對於在Adobe Journey Optimizer整合過程中自動產生的資料檢視，此值僅為&#x200B;**[!UICONTROL Off]**。 |
| **[!UICONTROL 建立日期]** | 資料檢視的建立時間戳記。 |
| **[!UICONTROL 上次修改日期]** | 最近修改資料檢視的時間戳記。 |

若要設定要在表格中顯示哪些欄，請選取![ColumnSetting](/help/assets/icons/ColumnSetting.svg)。 在&#x200B;**[!UICONTROL 自訂資料表]**&#x200B;對話方塊中，選取要顯示的資料行。 然後選取&#x200B;**[!UICONTROL 套用]**。


## 搜尋資料釋圖

您可以使用![搜尋](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg)方塊快速搜尋資料檢視。

## 篩選資料檢視

若要將篩選套用至資料檢視清單，請選取![篩選](/help/assets/icons/Filter.svg)圖示，然後從下列篩選選項中選取：

| 篩選條件選項 | 說明 |
|---------|----------|
| **[!UICONTROL 連線]** | 只會顯示與您選取的連線相關聯的資料檢視。 |
| **[!UICONTROL 所有者]** | 只會顯示您所選取人員擁有的資料檢視。 |
| **[!UICONTROL 沙箱]** | 系統只會顯示您選取的沙箱中可用的資料檢視。 |
| **[!UICONTROL 整合]** | 只會顯示具有選定整合的資料檢視。 |
| **[!UICONTROL 在 CJA 中使用]** | 選取&#x200B;**[!UICONTROL 開啟]**&#x200B;以僅顯示已啟用與Customer Journey Analytics搭配使用的資料檢視。 選取&#x200B;**[!UICONTROL 關閉]**，只顯示尚未啟用與Customer Journey Analytics搭配使用的資料檢視。 |


選取![篩選器](/help/assets/icons/Filter.svg) **[!UICONTROL 隱藏篩選器]**&#x200B;以隱藏篩選器窗格。

## 建立資料視圖

若要[建立新的資料檢視](/help/data-views/create-dataview.md)，請選取&#x200B;**[!UICONTROL 建立新的資料檢視]**。


## 編輯資料檢視

若您要[編輯資料檢視](/help/data-views/create-dataview.md)：

1. 選取資料檢視名稱旁的![更多](/help/assets/icons/More.svg)。
1. 從內容選單中選取 ![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 「編輯」]**。

或者，您可以：

1. 選取資料檢視列。
1. 選取藍色動作列中的「![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 編輯」]**。


## 複製資料檢視

如果要複製資料檢視：

1. 選取資料檢視名稱旁的![更多](/help/assets/icons/More.svg)。
1. 從內容功能表選取![複製](/help/assets/icons/Copy.svg) **[!UICONTROL 複製]**。

或者，您可以：

1. 選取一或多個資料檢視列。
1. 從藍色動作列中選取![複製](/help/assets/icons/Copy.svg) **[!UICONTROL 複製]**。

資料檢視已複製並新增至清單，且名稱已附加&#x200B;**[!UICONTROL （複製）]**。


## 刪除資料檢視

如果您想要刪除資料檢視：

1. 選取資料檢視名稱旁的![更多](/help/assets/icons/More.svg)。
1. 從內容功能表中選取![刪除](/help/assets/icons/Delete.svg) **[!UICONTROL 刪除]**。

或者，您可以：

1. 選取一或多個資料檢視列。
1. 選取藍色動作列中的「![刪除](/help/assets/icons/Delete.svg) **[!UICONTROL 刪除」]**。

當您刪除一或多個資料檢視時，**[!UICONTROL 刪除資料檢視]**&#x200B;面板會指出哪些專案受到影響。

![刪除資料檢視](/help/data-views/assets/delete-data-view.png)


* 在➊ **[!UICONTROL 確認]**&#x200B;中，會顯示刪除資料檢視的含意。
* 選取&#x200B;**[!UICONTROL 刪除]**&#x200B;以永久刪除資料檢視。 選取「**[!UICONTROL 取消]**」進行取消。


## 將資料檢視匯出為CSV

您可以將資料檢視匯出為CSV檔案。

1. 選取資料檢視名稱旁的![更多](/help/assets/icons/More.svg)。
1. 從內容功能表選取![檔案CSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL 匯出至CSV]**。

或者，您可以：

1. 選取一或多個資料檢視列。
1. 從藍色動作列選取![檔案CSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL 匯出至CSV]**。

選取的資料檢視詳細資料會匯出至瀏覽器[下載]資料夾中名為`Data views List (x).csv`的CSV檔案。


## 從資料檢視建立專案

您可以直接從資料檢視介面建立Workspace專案。

1. 選取資料檢視名稱旁的![更多](/help/assets/icons/More.svg)。
1. 從內容功能表選取![專案新增](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL 建立專案]**。

或者，您可以：

1. 選取資料檢視列。
1. 從藍色動作列選取![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL 建立專案]**。


## 啟用或停用Data Insights Agent的資料檢視

您可以啟用或停用[Data Insights Agent](/help/data-analysis-ai.md)的資料檢視。

1. 選取資料檢視名稱旁的![更多](/help/assets/icons/More.svg)。
1. 從內容功能表中選取![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 啟用Data Insights Agent]**&#x200B;或![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL 停用Data Insights Agent]**。

或者，您可以：

1. 選取一或多個已針對Data Insights Agent停用或啟用的資料檢視列。
1. 從藍色動作列中選取![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 啟用Data Insights Agent]**&#x200B;或![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL 停用Data Insights Agent]**。
