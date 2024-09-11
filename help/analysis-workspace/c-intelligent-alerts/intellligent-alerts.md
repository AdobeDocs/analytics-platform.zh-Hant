---
description: 新的智慧型警報系統可提供更細微的警報控制能力，並可與警報系統的異常偵測整合。
title: 智慧型警報概述
feature: Workspace Basics
role: User, Admin
source-git-commit: 74ad39f6ccc6436f7c8540b7d8b69b20b93d2b5c
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 56%

---

# 智慧型警報概述

{{release-limited-testing}}

Customer Journey Analytics中的智慧型警報（或只是「警報」）可讓您在資料中發生異常事件時收到通知。

您可以根據異常臨界值、變化百分比或特定資料點設定警報觸發。警示提供與[異常偵測](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md)整合的精細控制項，在您最需要時觸發。

智慧型警報可讓您：

* 根據異常 (90％、95％、99%、99.75% 或 99.9% 臨界值；% 變化；以上/以下) 建立警報
* 預覽警報觸發的頻率
* 透過電子郵件或簡訊傳送警報，當中附有可自動產生 Analysis Workspace 專案的連結
* 建立在單一警報中擷取多個量度的「堆疊」警報

下列影片教學課程提供警示的基本概觀： [智慧型警示](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html) (5:34)

## 瞭解警示與Adobe Analytics的Customer Journey Analytics有何不同

在 Customer Journey Analytics 中使用智慧型警報的流程，與在 Adobe Analytics 中使用智慧型警報幾乎相同。不過，兩者之間還是有重大差異。

如需詳細資訊，請參閱[智慧型警報功能比較：Customer Journey Analytics和Adobe Analytics](/help/analysis-workspace/c-intelligent-alerts/alerts-feature-comparison.md)。

## 警報的異常回顧

如果警報使用異常偵測，訓練期會依您為警報選擇的粒度而有所不同。

* 每月粒度：15 個月 + 去年的相同範圍
* 每週粒度：15 週 + 去年的相同範圍
* 每日粒度：35 天 + 去年的相同範圍
* 每小時粒度：336小時

如需詳細資訊，請參閱[異常偵測所使用的統計技術](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)。

## 建立警報

如需有關如何在Customer Journey Analytics中建立警示的資訊，請參閱[建立警示](/help/analysis-workspace/c-intelligent-alerts/alert-builder.md)。

>[!IMPORTANT]
>
>使用時間戳記資料建立警報，可能導致錯誤觸發警報。Adobe 建議您為智慧型警報使用非時間戳記資料。

## 管理警報

您可以在「警報管理員」中管理現有警報。 您可以對警示執行各種管理工作，例如標籤、重新命名、刪除等等。

如需有關如何管理Customer Journey Analytics中現有警示的詳細資訊，請參閱[管理警示](/help/analysis-workspace/c-intelligent-alerts/alert-manager.md)。

