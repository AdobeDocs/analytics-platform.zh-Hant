---
description: 組織可讓您在共用專案前先限制元件。
keywords: Analysis Workspace curation
title: 組織專案
translation-type: tm+mt
source-git-commit: a991dce6abaf90cbca06de75606a2517cb5b6484
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 99%

---


# 組織專案

>[!NOTE]
>
>您正在檢視 Customer Journey Analytics 中 Analysis Workspace 的相關文件，其功能集與傳統 Adobe Analytics 中的 [Analysis Workspace 略有不同](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html)。[深入了解...](/help/getting-started/cja-aa.md)

組織可讓您在共用專案前先限制元件 (維度、量度、區段、日期範圍)。收件者在開啟專案時，將會看到您為其組織的限定元件集。組織是可選作業，但建議您在共用專案前先執行此步驟。

>[!NOTE]
> 產品設定檔為管理哪些元件可向使用者顯示的主要機制。這項機制可透過 Adobe Experience Cloud Admin Console 來管理。組織為次要的篩選器。

## 套用專案組織

1. 按一下&#x200B;**[!UICONTROL 共用]** > **[!UICONTROL 組織專案資料]**。專案中使用的元件將會自動新增。
   **注意**：如果一個專案有多個報表套裝，則專案中的每個報表套裝都會顯示一個組織欄位。
1. (可選) 若要新增更多元件，請從左側邊欄將您要共用的元件拖曳至[!UICONTROL 組織元件]欄位。
1. 按一下&#x200B;**[!UICONTROL 完成]**。

您也可以按一下&#x200B;**[!UICONTROL 組織與共用]**，從[!UICONTROL 「共用」]功能表套用組織。此選項會自動將專案組織到專案中使用的元件。您可以依照上述步驟新增其他元件。

![](assets/curation-field.png)

## 已組織的專案檢視

收件者在開啟已組織的專案時，將只會看到您已定義的組織元件集：

![](assets/curate-project.png)

## 移除專案組織

若要移除專案組織並還原左側邊欄中的完整元件集：

1. 按一下&#x200B;**[!UICONTROL 共用]** > **[!UICONTROL 組織專案資料]**。
1. 按一下&#x200B;**[!UICONTROL 移除組織]**。
1. 按一下&#x200B;**[!UICONTROL 完成]**。

## 虛擬報表套裝 (VRS) 組織

若要在報表套裝層級套用組織，以便將其同時套用至多個專案，您可以[在虛擬報表套裝 (VRS) 中組織元件](https://docs.adobe.com/content/help/zh-Hant/analytics/components/virtual-report-suites/vrs-components.html)。

>[!NOTE]
> 系統會一律先套用 VRS 組織，再套用專案組織。換句話說，即使經組織的專案中含有特定元件，但只要經組織的 VRS 並未包含那些元件，系統便會將其篩除。

## 顯示所有元件選項

在已組織的專案或 VRS 中，收件者將會在左側邊欄中看到&#x200B;**[!UICONTROL 顯示所有元件]**&#x200B;的選項。[!UICONTROL 全部顯示]會根據下列條件顯示不同的元件集：

* 使用者的權限層級 (管理員或非管理員)
* 專案角色 (是否為擁有者/編輯者)
* 套用的組織類型 (VRS 或專案)

| 組織類型 | 管理員 | 非管理員專案擁有者或編輯角色 | 非管理員複製或檢視角色 |
|---|---|---|---|
| 已組織的 VRS | 所有未經組織的 VRS 元件 | 此角色擁有或已與其共享之未經組織的 VRS 元件 | 此角色擁有或已與其共享之未經組織的 VRS 元件 |
| 已組織的專案 | 所有未經組織的專案元件 | 所有未經組織的專案元件 | 此角色擁有或已與其共享之未經組織的專案元件 |
| 已組織 VRS 中的已組織專案 | 所有未經組織的元件 (如下所示)**[!UICONTROL 「未經組織的專案元件」]**&#x200B;和&#x200B;**[!UICONTROL 「未經組織的 VRS 元件」]** | 此角色擁有或已與其共用之所有未經組織的專案元件和未經組織的 VRS 元件 | 此角色擁有或已與其共享之未經組織的 VRS 與專案元件 |
