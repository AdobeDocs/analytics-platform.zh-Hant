---
description: 組織可讓您在共用專案之前先限制元件。
keywords: Analysis Workspace curation
title: 組織工作區專案
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 36%

---


# 組織工作區專案

>[!NOTE]
>
>您正在檢視客戶歷程分析中分析工作區的檔案。 其功能集與傳統Adobe Analytics中 [的「分析工作區」略有不同](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html)。 [更多詳情...](/help/getting-started/cja-aa.md)

組織可讓您在共用專案前先限制元件（維度、量度、區段、日期範圍）。 當收件者開啟專案時，他們會看到您為他們策劃的有限元件集。 組織是選用的，但建議先執行步驟，再共用專案。

>[!NOTE]
> 產品設定檔為管理哪些元件可向使用者顯示的主要機制。這些應用程式是透過Adobe Experience Cloud Admin Console管理。 組織為次要的篩選器。

## 套用專案組織

1. Click **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**.
將自動添加項目中使用的元件。
   **注意**: 如果專案有多個報表套裝，您會看到專案中每個報表套裝的組織欄位。
1. （可選）若要新增更多元件，請從左側導軌拖曳您要共用的元件至「組織元 [!UICONTROL 件] 」欄位。
1. 按一下&#x200B;**[!UICONTROL 「完成」]**。

您也可以按一下「組織」和「共 [!UICONTROL 用] 」，從「共 **[!UICONTROL 用」功能表套用組織]**。 此選項會自動將專案組織至專案中使用的元件。 您可以依照上述步驟新增其他元件。

![](assets/curation-field.png)

## 組織的專案檢視

當收件者開啟策劃的專案時，他們只會看到您已定義的組織元件：

![](assets/curate-project.png)

## 移除專案組織

要刪除項目組織並恢復左側導軌中的完整元件：
1. Click **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**.
1. 按一下 **[!UICONTROL 移除組織]**。
1. 按一下&#x200B;**[!UICONTROL 「完成」]**。

## 虛擬報表套裝(VRS)組織

若要在報表套裝層級套用組織，以便一次套用至多個專案，您可以在虛擬報 [表套裝(VRS)中組織元件](https://docs.adobe.com/content/help/zh-Hant/analytics/components/virtual-report-suites/vrs-components.html)。

>[!NOTE]
> 系統會一律先套用 VRS 組織，再套用專案組織。換句話說，即使經組織的專案中含有特定元件，但只要經組織的 VRS 並未包含那些元件，系統便會將其篩除。

## 顯示所有元件選項

在策劃的專案或VRS中，收件者將會看到在左側導軌中顯示「 **[!UICONTROL Show All]** components」（顯示所有元件）選項。 [!UICONTROL 「全部顯示] 」會顯示不同的元件集，視下列情況而定：

* 使用者的權限層級（管理員或非管理員）
* 專案角色（擁有者／編輯者與否）
* 套用的組織類型（VRS或專案）

| 組織類型 | 管理員 | 非管理員專案擁有者或編輯角色 | 非管理員重複或檢視角色 |
|---|---|---|---|
| 已組織的 VRS | 所有未經組織的 VRS 元件 | 此角色擁有或已與其共享之未經組織的 VRS 元件 | 此角色擁有或已與其共享之未經組織的 VRS 元件 |
| 已組織的專案 | 所有未經組織的專案元件 | 所有未經組織的專案元件 | 此角色擁有或已與其共享之未經組織的專案元件 |
| 已組織 VRS 中的已組織專案 | 所有未經組織的元件 (如下所示)**[!UICONTROL 「未經組織的專案元件」]**&#x200B;和&#x200B;**[!UICONTROL 「未經組織的 VRS 元件」]** | 此角色擁有或已與其共用之所有未經組織的專案元件和未經組織的 VRS 元件 | 此角色擁有或已與其共享之未經組織的 VRS 與專案元件 |
