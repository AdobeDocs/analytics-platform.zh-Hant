---
title: 將Quantum量度資料新增至Customer Journey Analytics
description: 使用量子量度來收集使用者歷程和行為的資料，然後從收集的資料強化CJA，以提取更豐富的見解。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hide: true
exl-id: ea8795fe-f5aa-458f-9e01-53ff1ffe6372
TQID: https://experienceleague.adobe.com/LLrYpPlbagFAIeuD9TMgA3E8lrcUrMxMSWLC-8SiiIY
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: e1bd5a34-b16e-477b-84cc-247fa0793f4b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 942cc774812d4a6b3b7f45df837ff9277e8f9b46
workflow-type: tm+mt
source-wordcount: 435
ht-degree: 4%

---

# 將Quantum量度資料新增至Customer Journey Analytics

>[!IMPORTANT]
>
>Quantum Metric來源聯結器目前尚無法使用。

CJA會解除QM資料、循序資料分析、豐富歸因及其他進階報表的報表時間控制鎖定。  QM可以使用QM來源聯結器或Quantum Metrics Tags擴充功能傳送至AEP。

## 步驟1：建立量度來源聯結器

1. 登入[experience.adobe.com](https://experience.adobe.com)。
1. 導覽至[!UICONTROL Experience Platform] > [!UICONTROL 連線] > [!UICONTROL 來源]。
1. 新增Quantum Metric來源聯結器，並依照提示完成操作。

如需詳細資訊，請參閱[Adobe Experience Platform來源聯結器](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/home)。

## 步驟2：在Customer Journey Analytics中建立連線

建立Quantum量度資料的來源聯結器會自動在Adobe Experience Platform中建立資料集。 將此資料集新增至Customer Journey Analytics中的新或現有[連線](/help/connections/overview.md)。

1. 登入[experience.adobe.com](https://experience.adobe.com)。
1. 導覽至Customer Journey Analytics，然後在頂端功能表中選取&#x200B;**[!UICONTROL 連線]** （可選擇從&#x200B;**[!UICONTROL 資料管理]**&#x200B;進行）。
1. 為連線命名，並將Quantum量度資料集新增至連線。
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

>[!NOTE]
>雖然您可以將Quantum量度資料新增至與Customer Journey Analytics資料其餘部分相同的連線，但若沒有兩個資料集之間的通用人員ID，該資料無法彙整在一起。 如果需要此行為，Adobe建議使用[標籤延伸模組](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/destinations/catalog/analytics/quantum-metric)，而非來源聯結器。

## 步驟3：在Customer Journey Analytics中建立資料檢視

建立[資料檢視](/help/data-views/data-views.md)以設定維度和量度設定。

1. 登入[experience.adobe.com](https://experience.adobe.com)。
1. 導覽至Customer Journey Analytics，然後在頂端功能表中選取&#x200B;**[!UICONTROL 資料檢視]** （可選擇從&#x200B;**[!UICONTROL 資料管理]**&#x200B;進行）。
1. 選取所需的資料檢視，或建立資料檢視。
1. 在右側的結構欄位清單中找出所需的「量度」維度和量度，並將其拖曳至中心的維度和量度區域。
1. 使用右窗格來設定每個所需的維度和量度。

## 步驟4：開始在Customer Journey Analytics中報告和分析

現在，資料可在Customer Journey Analytics中使用，您可以開始報告資料。

1. 登入[experience.adobe.com](https://experience.adobe.com)。
1. 導覽至Customer Journey Analytics，然後在頂端功能表中選取&#x200B;**[!UICONTROL Workspace]**。
1. 選取現有專案，或建立專案。
1. 將任何需要的量度維度或量度拖曳至Workspace畫布以分析資料。
