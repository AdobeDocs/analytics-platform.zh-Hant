---
title: 升級至 Customer Journey Analytics 時的監視資料集攝取
description: 了解如何在升級至 Customer Journey Analytics 時監視資料集攝取
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
autotag-review: '2026-05-19T08:10:42.746Z'
TQID: 'https://experienceleague.adobe.com/tAPQiUUPilyH50PlqwefoZjw14QDN9ER1D6EKsMAR9w'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 224
ht-degree: 100%

---

# 升級至 Customer Journey Analytics 時的監視資料集攝取 {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="驗證資料集中的資料"
>abstract="現在您已設定您的實作，便可以使用資料集活動管理員來查看已攝取和失敗的批次。 如果您看到的主要攝取的批次，則此步驟已完成。 如果您看到的主要失敗的批次或沒有批次，請檢查您的實作，以確保其正確地將資料傳送至 Adobe。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

設定好您的 Web SDK 或 API 實施後，您需要查看個別批次的狀態以驗證資料是否已被攝取到資料集中。

1. 在 Experience Platform UI 中，選取左側導覽中的「**[!UICONTROL 監控]**」。

   監控儀表板會顯示。 此儀表板可讓您檢視批次或串流攝取的輸入資料狀態。

   <!-- insert screenshot -->

1. 選取「**[!UICONTROL 批次端對端]**」，查看批次清單。

   如果未顯示批次資料，請查看您的實施，以確保實施有正確地將資料傳送至 Adobe。

   <!-- insert screenshot -->

1. 選取特定資料集的批次 ID，然後驗證「**[!UICONTROL 狀態]**」欄位中是否顯示「**[!UICONTROL 成功]**」。

   如果「**[!UICONTROL 狀態]**」欄位顯示「**[!UICONTROL 失敗]**」，請查看您的實施，以確保實施有正確地將資料傳送至 Adobe。

   重複此步驟來驗證每個批次的狀態。

{{upgrade-final-step}}

