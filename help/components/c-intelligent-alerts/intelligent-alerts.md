---
description: 了解如何使用警報，以便對通知進行精細控制並與異常偵測整合。
title: 警報概觀
feature: Workspace Basics
role: User, Admin
exl-id: 029be0c8-ec78-4bb7-a6cd-bb303b5ac82a
source-git-commit: 65e46a5d2a6759dd83b24bba2d1d4ee283b907c9
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 58%

---

# 警報概觀

Customer Journey Analytics 中的警報可讓您根據變更的百分比或特定資料點來接收通知

根據您的 Customer Journey Analytics 套件，您還可以使用根據異常臨界值觸發的警報。這些警示（也稱為&#x200B;*智慧型警示*）提供與[異常偵測](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md)整合的精細控制項，在您最需要時觸發。

* 預覽警報觸發的頻率。
* 透過電子郵件或簡訊傳送警報，當中附有可自動產生 Analysis Workspace 專案的連結。
* 建立可在單一警報中擷取多個量度的&#x200B;*棧疊*&#x200B;警報。
* 建立警示依據：
   * 量度中的異常已存在、高於或低於預期臨界值。

     [異常偵測](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md)會使用歷史資料建置預期值加上上限與下限。 如果實際量度值高於定義為臨界值的上限或下限，則該事件在臨界值信賴等級中被視為異常，且不會觸發警報。 較高的臨界值（例如：99%或99.9%）表示頻寬較寬，導致由更極端的異常所造成的警報較少。 較低的臨界值（例如：90%）表示頻帶較窄，這會產生由不太極端的異常所導致的更多警示。
   * 依特定百分比區分的量度變更。
   * 高於、低於或等於特定值的量度。 (僅適用於擁有Select、Prime或Ultimate套件的Adobe Analytics客戶)

此[教學影片](https://experienceleague.adobe.com/zh-hant/docs/analytics-learn/tutorials/data-science/intelligent-alerts)提供警示的基本概觀。



## 了解警示有何差異

在 Customer Journey Analytics 中使用警報的流程，與在 Adobe Analytics 中使用警報的流程幾乎相同。儘管如此，還是有些重要差異。

若要了解更多資訊，請參閱「[警報功能比較：Customer Journey Analytics 和 Adob&#x200B;&#x200B;e Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)」。

## 警報的異常回顧

>[!NOTE]
>
>僅擁有 Customer Journey Analytics Select、Prime 或 Ultimate 套件的組織才能使用具有異常偵測的警報 (也稱為&#x200B;_智慧型警報_)。

如果警報使用異常偵測，訓練期會依您為警報選擇的顆粒度而有所不同。

* 每月顆粒度：15 個月 + 去年的相同範圍
* 每週顆粒度：15 週 + 去年的相同範圍
* 每日顆粒度：35 天 + 去年的相同範圍
* 每小時顆粒度：336小時

如需更多資訊，請參閱[用於異常偵測統計技術](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)。

## 建立警報

如需有關如何在 Customer Journey Analytics 中建立警報的資訊，請參閱「[建立警報](/help/components/c-intelligent-alerts/alert-builder.md)」。

>[!IMPORTANT]
>
>使用時間戳記資料建立警報，可能導致錯誤觸發警報。Adobe 建議您為警報使用非時間戳記資料。

## 管理警報

您可以在警報管理器中管理現有警報。您可以對警報執行各種管理任務，例如標記、重新命名、刪除等。

如需有關如何管理 Customer Journey Analytics 中現有警報的更多資訊，請參閱「[管理警報](/help/components/c-intelligent-alerts/alert-manager.md)」。
