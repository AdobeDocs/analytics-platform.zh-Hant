---
title: 升級至 Customer Journey Analytics 時的監視資料集攝取
description: 瞭解在升級至Customer Journey Analytics時如何監視資料集擷取
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 33%

---

# 升級至 Customer Journey Analytics 時的監視資料集攝取 {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="驗證資料集中的資料"
>abstract="現在您已設定您的實作，便可以使用資料集活動管理員來查看已攝取和失敗的批次。如果您看到的主要攝取的批次，則此步驟已完成。如果您看到的主要失敗的批次或沒有批次，請檢查您的實作，以確保其正確地將資料傳送至 Adobe。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

在您設定網頁SDK或API實作後，您需要檢查個別批次的狀態，以確認資料正在擷取到資料集中。

1. 在Experience Platform UI中，選取左側導覽中的&#x200B;**[!UICONTROL 監視]**。

   監控儀表板隨即顯示。 此儀表板可讓您檢視來自批次或串流擷取的入站資料狀態。

   <!-- insert screenshot -->

1. 選取&#x200B;**[!UICONTROL 批次端對端]**&#x200B;以檢視批次清單。

   如果未顯示任何批次，請檢查您的實作，以確保其正確地將資料傳送至Adobe。

   <!-- insert screenshot -->

1. 選取指定資料集的批次識別碼，然後驗證&#x200B;**[!UICONTROL 狀態]**&#x200B;欄位中是否顯示&#x200B;**[!UICONTROL 成功]**。

   如果&#x200B;**[!UICONTROL 失敗]**&#x200B;顯示在&#x200B;**[!UICONTROL 狀態]**&#x200B;欄位中，請檢查您的實作，以確定其正確傳送資料至Adobe。

   重複此步驟以驗證每個批次的狀態。

{{upgrade-final-step}}

