---
title: 瞭解您的Adobe Analytics實作及其對您升級至Customer Journey Analytics的影響
description: 瞭解從Adobe Analytics升級為Customer Journey Analytics時的建議路徑
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: 3827bafd85a03e8574667095b372aa61afb6756b
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 9%

---

# 瞭解您的Adobe Analytics實作及其對您升級至Customer Journey Analytics的影響

>[!NOTE]
> 
>必須先完成所有先前的升級步驟，才能依照本頁面的步驟操作。 您可以依照[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)操作，也可以依照[Adobe Analytics為您的組織動態產生的升級步驟操作，以Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。
>
>完成此頁面上的步驟後，請繼續依照建議的升級步驟或動態產生的升級步驟操作。

有多種方式可升級至Customer Journey Analytics，但並非所有升級路徑都適用於每種型別的Adobe Analytics實施。 不過，不論Adobe Analytics在您的組織中如何實作，都提供建議的升級路徑。

請利用下列資訊協助您瞭解目前的Adobe Analytics實作，以及組織可用的升級路徑。

如果您需要更具體的建議、指引或支援，請聯絡您的Adobe代表。

| 現有的Adobe Analytics實作 | 說明 | 可用的升級路徑 |
|---------|----------|----------|
| AppMeasurement | AppMeasurementJavaScript向來是實施Adobe Analytics的常用方法。<p>如需此實作型別的詳細資訊，請參閱[使用JavaScript的AppMeasurement實作Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview)</p> | <ul><li>（建議）透過Analytics Source聯結器新實作Experience Platform Web SDK</li><li>Experience Platform Web SDK的新實作</li><li>將Adobe Analytics移轉至Web SDK</li><li>Analytics Source聯結器</li></ul> |
| Adobe Analytics擴充功能（標籤） | <p>Adobe Experience Platform 中的標記是標記管理解決方案，可讓您部署 Analytics 程式碼以及其他標記需求。 Adobe 可與其他解決方案和產品整合，且您可部署自訂程式碼。您不需依賴組織內部的任何開發團隊更新網站上的程式碼，便可完成上述所有工作。</p><p>如需此實作型別的詳細資訊，請參閱[使用Analytics擴充功能實作Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview)</p> | <ul><li>（建議）透過Analytics Source聯結器新實作Experience Platform Web SDK</li><li>Experience Platform Web SDK的新實作</li><li>將Adobe Analytics移轉至Web SDK</li><li>Analytics Source聯結器</li></ul> |
| Experience PlatformWeb SDK (alloy.js) | Experience Platform Web SDK是Adobe目前建議的實施Adobe Analytics方法。 Adobe Experience PlatformEdge Network可讓您將預計要送給多個產品的資料傳送到一個集中位置。 <p>如需此實作型別的詳細資訊，請參閱[使用Adobe Experience PlatformEdge Network實作Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)</p> | <ul><li>（建議）透過Analytics Source聯結器新實作Experience Platform Web SDK</li><li>設定Adobe Analytics Web SDK實作，將資料傳送至Platform</li></ul> |
| Experience Platform Web SDK擴充功能（標籤） | Experience Platform Web SDK是Adobe目前為實作Adobe Analytics以處理網頁資料而建議使用的方法。 Adobe Experience PlatformEdge Network可讓您將預計要送給多個產品的資料傳送到一個集中位置。 <p>如需此實作型別的詳細資訊，請參閱[https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)</p> | <ul><li>（建議）透過Analytics Source聯結器新實作Experience Platform Web SDK</li><li>設定Adobe Analytics Web SDK實作，將資料傳送至Platform</li></ul> |
| Experience Platform Mobile SDK | Experience Platform Mobile SDK是Adobe目前為行動資料實作Adobe Analytics的建議方法。 Adobe Experience PlatformEdge Network可讓您將預計要送給多個產品的資料傳送到一個集中位置。<p>Adobe Experience Platform Mobile SDK有助於在行動應用程式中強化Adobe的Experience Cloud解決方案和服務。 </p><p>如需此實作型別的詳細資訊，請參閱[使用Adobe Experience Platform Mobile SDK實作Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>（建議）透過Analytics Source聯結器新實作Experience Platform Web SDK</li><li>設定Adobe Analytics Web SDK實作，將資料傳送至Platform</li></ul> |

{style="table-layout:auto"}
