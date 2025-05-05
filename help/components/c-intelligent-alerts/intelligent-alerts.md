---
description: 警報可對通知進行精細控制，並整合異常偵測。
title: 警報概觀
feature: Workspace Basics
role: User, Admin
exl-id: 029be0c8-ec78-4bb7-a6cd-bb303b5ac82a
source-git-commit: 56ac1c5a6d13a972aed90cab79cbc5f794cedc9e
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 98%

---

# 警報概觀

Customer Journey Analytics 中的警報可讓您根據變更的百分比或特定資料點來接收通知

根據您的 Customer Journey Analytics 套件，您還可以使用根據異常臨界值觸發的警報。這些警報 (也稱為「智慧型警報」) 提供整合[異常偵測](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md)的精細控制，可在您最需要時觸發。

警報可讓您：

* 預覽警報觸發的頻率
* 透過電子郵件或簡訊傳送警報，當中附有可自動產生 Analysis Workspace 專案的連結
* 建立在單一警報中擷取多個量度的「堆疊」警報
* 根據異常情況建置警報 (90%、95%、99%、99.75% 和 99.9% 臨界值；百分比變更；高於/低於)(僅適用於擁有 Select、Prime 或 Ultimate 套件的 Customer Journey Analytics 客戶)

以下影片教學課程提供警報基本概觀：[警報](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=zh-Hant) (在影片 5:34 處)

## 瞭解警報的差異

在 Customer Journey Analytics 中使用警報的流程，與在 Adobe Analytics 中使用警報的流程幾乎相同。儘管如此，還是有些重要差異。

若要了解更多資訊，請參閱「[警報功能比較：Customer Journey Analytics 和 Adob&#x200B;&#x200B;e Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)」。

## 警報的異常回顧

>[!NOTE]
>
>僅擁有 Customer Journey Analytics Select、Prime 或 Ultimate 套件的組織才能使用具有異常偵測的警報 (也稱為&#x200B;_智慧型警報_)。

如果警報使用異常偵測，訓練期會依您為警報選擇的詳細程度而有所不同。

* 每月詳細程度：15 個月 + 去年的相同範圍
* 每週詳細程度：15 週 + 去年的相同範圍
* 每日詳細程度：35 天 + 去年的相同範圍
* 每小時詳細程度：336小時

如需更多資訊，請參閱[用於異常偵測統計技術](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)。

## 建立警報

如需有關如何在 Customer Journey Analytics 中建立警報的資訊，請參閱「[建立警報](/help/components/c-intelligent-alerts/alert-builder.md)」。

>[!IMPORTANT]
>
>使用時間戳記資料建立警報，可能導致錯誤觸發警報。Adobe 建議您為警報使用非時間戳記資料。

## 管理警報

您可以在警報管理器中管理現有警報。您可以對警報執行各種管理任務，例如標記、重新命名、刪除等。

如需有關如何管理 Customer Journey Analytics 中現有警報的更多資訊，請參閱「[管理警報](/help/components/c-intelligent-alerts/alert-manager.md)」。
