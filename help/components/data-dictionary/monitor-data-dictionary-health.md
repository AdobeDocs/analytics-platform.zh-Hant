---
description: 管理員負責監控資料字典的健康狀況。 這包括元件是否正在收集資料、獲得核准、包含特定說明，以及沒有重複。
title: 監視資料字母排序健康狀況
feature: Components
role: Admin
exl-id: 8bc89ac7-078d-469d-8627-3905823d4100
TQID: https://experienceleague.adobe.com/RKh01bcmVkoZ2wkHDvBM-oX9rRagVaOqK4fn2A-IpaI
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: df28738e-9c71-4aa8-929e-edde22340cc6
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: b7493ad9283b5830c36b8e3ac942bf9295b693f8
workflow-type: tm+mt
source-wordcount: 461
ht-degree: 88%

---

# 監視資料字母排序健康狀況 {#monitor-data-dictionary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_datadictionary"
>title="資料字典"
>abstract="選取此選項後，主要元件會與可存取重複元件的每個人 (所有者和與之共用元件的任何人) 共用。 然後，這些使用者就可以從元件清單中選取主要元件，以供未來的專案使用。 但是，他們無法編輯該元件，即使他們是已合併之重複元件的所有者亦然。 <br/>此選項只有在主要元件是細分群體、計算量度或日期範圍時才可用。 量度和維度始終可供所有使用者使用。
>
>When this option is deselected, the primary component still replaces duplicates in existing projects and segments, but users who didn't previously have access to it can't access it from the component list for future projects. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="datadictionary_share_primary"
>title="共用主要元件"
>abstract="選取此選項後，主要元件會與可存取重複元件的每個人 (所有者和與之共用元件的任何人) 共用。 然後，這些使用者就可以從元件清單中選取主要元件，以供未來的專案使用。 但是，他們無法編輯該元件，即使他們是已合併之重複元件的所有者亦然。 <br/>此選項只有在主要元件是細分群體、計算量度或日期範圍時才可用。 量度和維度始終可供所有使用者使用。
>
>When this option is deselected, the primary component still replaces duplicates in existing projects and segments, but users who didn't previously have access to it can't access it from the component list for future projects. "

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-enable MD034 -->

>[!CONTEXTUALHELP]
>id="datadictionary_delete_duplicates"
>title="刪除所取代的重複項目"
>abstract="選取此選項後，合併的重複項目將不再可用。 如果您想要讓重複項目繼續可用，請取消選取此選項。"

<!-- markdownlint-enable MD034 -->

Customer Journey Analytics管理員負責維護健康的資料字典。

## 健康資料字典的特徵

健康的資料字典是所有的元件：

* 正在使用且正在收集資料

* 包含有用的說明，讓使用者了解如何善加利用各種元件

* 沒有不必要的重複

* 經管理員核准

## 檢查資料字典的健康狀況

在您的資料字典中識別健康問題：

1. 開啟 Analysis Workspace 專案。

1. 選取 Analysis Workspace 左邊的資料字典圖示。 (存取資料字典的替代方法說明請見[資料字典概觀](/help/components/data-dictionary/data-dictionary-overview.md)中的「存取資料字典」。)

   顯示資料字典視窗。

   ![資料字典管理員的檢視，顯示字典健康狀態](assets/data-dictionary-admin.png)

1. 確定在下拉式選單中選取了正確的資料檢視。

1. 在 [!UICONTROL **字典健康**] 標籤上選擇以下任一選項旁邊的 [!UICONTROL **檢視**]：

   * [!UICONTROL **個元件缺少說明**]

   * [!UICONTROL **個元件有重複項**]

   * [!UICONTROL **個元件未連接任何資料**]

   視您選取的專案而定，會將適當的區段套用至資料字典，並僅顯示相關元件。

1. 編輯任何元件以提升資料字典的健康狀況。 有關如何在資料字典中編輯元件的資訊，請參閱[在資料字典中編輯元件條目](/help/components/data-dictionary/edit-entries-data-dictionary.md)。
