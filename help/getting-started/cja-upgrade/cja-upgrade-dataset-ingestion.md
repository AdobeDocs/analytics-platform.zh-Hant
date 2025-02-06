---
title: 升級至Customer Journey Analytics時監視資料集擷取
description: 瞭解在升級至Customer Journey Analytics時如何監視資料集擷取
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: 3b1012a302200192fd31fd6a9ed94f96323eb595
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 0%

---

# 升級至Customer Journey Analytics時監視資料集擷取 {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="驗證資料集中的資料"
>abstract="現在您已設定好網頁SDK實作，您可以使用資料集活動管理器來檢視擷取和失敗的批次。 如果您主要看到擷取的批次，表示此步驟已完成。 如果您主要看到失敗的批次或沒有批次，請檢查您的Web SDK實施，以確保其正確地將資料傳送到Adobe。<br><br>如果一切都已正確且完美地完成，這個步驟可以在一天內完成。 如果有多個資料收集問題，疑難排解可能需要更長的時間。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>必須先完成所有先前的升級步驟，才能依照本頁面的步驟操作。 您可以依照[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)操作，也可以依照[Adobe Analytics為您的組織動態產生的升級步驟操作，以Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。
>
>完成此頁面上的步驟後，請繼續依照建議的升級步驟或動態產生的升級步驟操作。

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

設定網頁SDK實作後，您需要檢查個別批次的狀態，以確認資料正在擷取至資料集中。

1. 在Experience PlatformUI中，選取左側導覽中的&#x200B;**[!UICONTROL 監視]**。

   監控儀表板隨即顯示。 此儀表板可讓您檢視來自批次或串流擷取的入站資料狀態。

   <!-- insert screenshot -->

1. 選取&#x200B;**[!UICONTROL 批次端對端]**&#x200B;以檢視批次清單。

   如果未顯示任何批次，請檢查您的Web SDK實作，以確保其可正確地傳送資料給Adobe。

   <!-- insert screenshot -->

1. 選取指定資料集的批次識別碼，然後驗證&#x200B;**[!UICONTROL 狀態]**&#x200B;欄位中是否顯示&#x200B;**[!UICONTROL 成功]**。

   如果&#x200B;**[!UICONTROL Failed]**&#x200B;顯示在&#x200B;**[!UICONTROL 狀態]**&#x200B;欄位中，請檢查您的Web SDK實作，以確保其正確傳送資料給Adobe。

   重複此步驟以驗證每個批次的狀態。

1. 繼續執行[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[動態產生的升級步驟](https://gigazelle.github.io/cja-ttv/)。

