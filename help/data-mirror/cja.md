---
title: 設定Customer Journey Analytics
description: 瞭解如何為Customer Journey Analytics的Experience Platform Data Mirror設定Customer Journey Analytics連線、資料檢視和專案
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: f7687bba-efbe-4a2c-8ad1-cf216554a1e9
source-git-commit: b2a13524760f9d466696534bc8b9691f3b4dfb8a
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 2%

---

# 設定Customer Journey Analytics

{{release-limited-testing}}

{{relational-model-based}}

若要針對Customer Journey Analytics使用Experience Platform Data Mirror功能，您必須建立或更新連線、資料檢視和工作區專案，才能使用關聯式資料。

## 連線

在您的連線中，新增代表資料倉儲原生解決方案之資料的關聯式資料集。 這些資料集確實有關聯式資料集型別。

當您新增的關聯式資料集包含來自Data Warehouse原生解決方案的映象資料時，該資料通常是事件資料。 請確定您為資料集選取正確的設定。 例如，選取正確的資料集型別、身分欄位和時間戳記欄位。


## 資料檢視

將關聯式結構描述中的欄位定義為資料檢視中的元件（量度和維度）。 資料映象欄位可在&#x200B;**[!UICONTROL 事件資料集]**&#x200B;資料夾的&#x200B;**[!UICONTROL 臨機與關聯欄位]**&#x200B;子資料夾中使用。 使用功能（例如[衍生欄位](/help/data-views/derived-fields/derived-fields.md)或[元件設定](/help/data-views/component-settings/overview.md)）來修改以關聯式欄位為基礎的元件。


## Workspace 專案

設定使用關聯式資料中量度和維度的Workspace專案。 最終以Data Warehouse原生解決方案中的資料為基礎的元件。 會根據您設定的資料映象功能而更新。

>[!MORELIKETHIS]
>
>[Data Mirror快速入門手冊：映象並使用關係資料](relational.md)
>
