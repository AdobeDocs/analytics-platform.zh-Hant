---
description: 警報可讓您精細地控制通知，並整合異常偵測。
title: 警報概觀
feature: Workspace Basics
role: User, Admin
source-git-commit: def8b074ea468e409e340415d5e96f75d6b69312
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 27%

---

# 警報概觀

Customer Journey Analytics中的警報可讓您根據變更的百分比或特定資料點收到通知。

視您的Customer Journey Analytics封裝而定，您也可以使用要根據異常臨界值觸發的警報。 這些警報（也稱為「智慧型警報」）提供與[異常偵測](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md)整合的精細控制項，在您最需要時觸發。

警示可讓您：

* 預覽警報觸發的頻率
* 透過電子郵件或簡訊傳送警報，當中附有可自動產生 Analysis Workspace 專案的連結
* 建立在單一警報中擷取多個量度的「堆疊」警報
* 根據異常（90%、95%、99%、99.75%和99.9%臨界值；%變更；以上/以下）建立警報(僅適用於Select、Prime或Ultimate套件的Customer Journey Analytics客戶)

下列影片教學課程提供警示的基本概觀： [警示](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html) (5:34)

## 瞭解警示與Adobe Analytics的Customer Journey Analytics有何不同

在Customer Journey Analytics中使用警報的程式幾乎與在Adobe Analytics中使用警報的程式相同。 不過，兩者之間還是有重大差異。

如需詳細資訊，請參閱[警示功能比較：Customer Journey Analytics和Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)。

## 警報的異常回顧

>[!NOTE]
>
>使用具有異常偵測的警報（也稱為&#x200B;_智慧型警報_）僅適用於具有Select、Prime或UltimateCustomer Journey Analytics封裝的組織。

如果警報使用異常偵測，訓練期會依您為警報選擇的粒度而有所不同。

* 每月粒度：15 個月 + 去年的相同範圍
* 每週粒度：15 週 + 去年的相同範圍
* 每日粒度：35 天 + 去年的相同範圍
* 每小時粒度：336小時

如需詳細資訊，請參閱[異常偵測所使用的統計技術](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)。

## 建立警報

如需有關如何在Customer Journey Analytics中建立警示的資訊，請參閱[建立警示](/help/components/c-intelligent-alerts/alert-builder.md)。

>[!IMPORTANT]
>
>使用時間戳記資料建立警報，可能導致錯誤觸發警報。Adobe建議對警報使用非時間戳記資料。

## 管理警報

您可以在「警報管理員」中管理現有警報。 您可以對警示執行各種管理工作，例如標籤、重新命名、刪除等等。

如需有關如何管理Customer Journey Analytics中現有警示的詳細資訊，請參閱[管理警示](/help/components/c-intelligent-alerts/alert-manager.md)。

