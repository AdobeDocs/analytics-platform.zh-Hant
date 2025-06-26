---
description: 監管可讓您在共用專案前先限制元件。
keywords: Analysis Workspace 監管
title: 監管專案
feature: Curate and Share
exl-id: f9636191-8414-458c-9881-8c03f3d45efb
role: User
source-git-commit: f940e5cba11df0ff158093a503213ff1641b1c5d
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 55%

---

# 組織專案

管監功能可襄您在共用專案前先限制元件 (維度、量度、區段、日期範圍)。收件者在開啟專案時，會看到您為其組織的限定元件集。 組織是可選作業，但建議您在共用專案前先執行此步驟。

>[!NOTE]
> 產品設定檔為管理哪些元件可向使用者顯示的主要機制。這項機制可透過 [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/en/docs/core-services/interface/administration/admin-tool-experience-cloud) 來管理。 組織為次要的區段。

## 套用專案組織

1. 選取&#x200B;**[!UICONTROL 共用]** > **[!UICONTROL 組織專案資料]**。
專案中使用的元件會自動新增。
如果專案有多個資料檢視，您會在專案中看到每個資料檢視的監管放置目標。
1. （可選）若要新增更多元件，請從左側面板將您要共用的元件拖曳至資料檢視的&#x200B;**[!UICONTROL 組織元件]**&#x200B;拖放區域。
1. 選取&#x200B;**[!UICONTROL 完成]**。

<!--
Curation can also be applied from the [!UICONTROL Share] menu by selecting **[!UICONTROL Curate and Share]**. This option automatically curates the project to the components in use in the project. You can add additional components following the steps above.
-->

![Curate Components 視窗會顯示專案正在使用的元件。](assets/curation-field.png)

收件者在開啟已組織的專案時，只會看到您已定義的組織元件集：


## 移除專案組織

若要移除專案組織並還原左側面板中的完整元件集：

1. 選取&#x200B;**[!UICONTROL 共用]** > **[!UICONTROL 組織專案資料]**。
1. 選取&#x200B;**[!UICONTROL 移除組織]**。
1. 選取&#x200B;**[!UICONTROL 完成]**。

## 元件組織選項

在已組織的專案中，收件者將會在左側面板中看到&#x200B;**[!UICONTROL 顯示全部]**&#x200B;個元件的選項。 「[!UICONTROL 全部顯示]」會根據下列條件顯示不同的元件集：

* 使用者的權限層級 (管理員或非管理員)
* 專案角色 (是否為所有者/編輯者)
* 套用的組織類型 (在專案層級)

| 組織類型 | 管理員可以看到 | 非管理員專案所有者 (或編輯角色) 可以看到 | 非管理員重複角色可以看到 |
| --- | --- | --- | --- |
| 從資料檢視&#x200B;**中隱藏的**&#x200B;元件&#x200B;*2&rbrace;* | 所有資料檢視元件都可用於報告（隱藏元件需要您選取&#x200B;**[!UICONTROL 全部顯示]**） | 不可用於報告 | 不可用於報告 |
| **從資料檢視中新增或移除的元件** | 僅限新增到資料檢視的元件 (隱藏或未隱藏)。 管理員無法報告資料檢視中未定義的欄位或元件。 | 僅限新增到資料檢視的元件，或由用戶擁有或與用戶共用的元件。 隱藏元件不適用 (例如虛擬報告套件監管)。 | 只有新增到資料檢視的元件不會隱藏，並包含在專案組織中。 |
| **專案中已組織的元件** | 所有可用於報告的資料檢視元件（隱藏元件需要您選取&#x200B;**[!UICONTROL 全部顯示]**） | 所有非隱藏的資料檢視元件 (需要按一下「顯示全部」) | 僅限已組織的元件，加上由用戶擁有或與用戶共用的元件 |
| **使用具有隱藏元件之資料檢視的組織專案** | 所有可用於報告的資料元件（隱藏和非組織元件需要您選取&#x200B;**[!UICONTROL 全部顯示]**） | 所有非組織專案元件、所有非隱藏資料檢視元件，以及用戶擁有或與用戶共用的任何元件 | 僅限已組織的元件，加上由用戶擁有或與用戶共用的元件 |
