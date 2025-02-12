---
title: 升級至 Customer Journey Analytics 時的監視資料集攝取
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
ht-degree: 32%

---

# 升級至 Customer Journey Analytics 時的監視資料集攝取 {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="驗證資料集中的資料"
>abstract="現在您已設定 Web SDK 實作，便可以使用資料集活動管理員查看已攝取和失敗的批次。如果您看到的主要是已攝取的批次，則此步驟已完成。如果您看到的主要是失敗的批次或沒有批次，請檢查您的 Web SDK 實作，確保其正確地將資料傳送至 Adobe。<br><br>如果一切均正確無誤完成，只需不到一天的時間即可完成這個步驟。如果發生多個資料彙集問題，則進行疑難排解可能明顯花費更長時間。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>必須先完成所有先前的升級步驟，才能依照本頁面的步驟操作。 您可以依照[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)操作，也可以依照[Adobe Analytics到Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)為您的組織動態產生的升級步驟操作。
>
>完成此頁面上的步驟後，請繼續依照建議的升級步驟或動態產生的升級步驟操作。

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

設定網頁SDK實作後，您需要檢查個別批次的狀態，以確認資料正在擷取至資料集中。

1. 在Experience Platform UI中，選取左側導覽中的&#x200B;**[!UICONTROL 監視]**。

   監控儀表板隨即顯示。 此儀表板可讓您檢視來自批次或串流擷取的入站資料狀態。

   <!-- insert screenshot -->

1. 選取&#x200B;**[!UICONTROL 批次端對端]**&#x200B;以檢視批次清單。

   如果未顯示任何批次，請檢查您的Web SDK實作，以確保其正確地傳送資料給Adobe。

   <!-- insert screenshot -->

1. 選取指定資料集的批次識別碼，然後驗證&#x200B;**[!UICONTROL 狀態]**&#x200B;欄位中是否顯示&#x200B;**[!UICONTROL 成功]**。

   如果&#x200B;**[!UICONTROL Failed]**&#x200B;顯示在&#x200B;**[!UICONTROL 狀態]**&#x200B;欄位中，請檢查您的Web SDK實作，以確保其正確傳送資料至Adobe。

   重複此步驟以驗證每個批次的狀態。

1. 繼續執行[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[動態產生的升級步驟](https://gigazelle.github.io/cja-ttv/)。

