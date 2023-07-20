---
title: Customer Journey Analytics 指南
description: Customer Journey Analytics 登陸頁面。
exl-id: c2d9b758-42a4-4b58-9bab-095518efb86d
solution: Customer Journey Analytics
feature: Basics
source-git-commit: a49ef8b35b9d5464df2c5409339b33eacb90cd9c
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 86%

---

# Customer Journey Analytics 指南

本技術文件指南提供 Customer Journey Analytics 的自助協助。Customer Journey Analytics 可將您選擇之任何管道的客戶資料 (線上及離線皆可) 整合到 Adobe Experience Platform 中，接著依您目前使用 Analysis Workspace 分析現有數位資料的方式加以分析。

Customer Journey Analytics 可讓您控制如何在 Analysis Workspace 中連接任何常見客戶 ID 的線上和離線資料，進而允許您在Customer Journey Analytics的整個客戶資料集中搜尋。

Analytics Select、Prime 和 Ultimate 客戶均符合購買此附加產品的資格。如需詳細資訊，請聯絡您的 Adobe 客戶團隊。

<table frame="none"> 
 <tbody> 
  <tr> 
   <td colname="col1" colsep="0" rowsep="0" valign="top"> <p class="head"> <b>全新或精選項目</b> </p> <p> 
     <ul>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/stitching/overview.html"> 跨管道分析(在Customer Journey Analytics中彙整ID) </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=zh-Hant">在 Customer Journey Analytics 中利用 Adobe Analytics 報告套裝資料</a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=zh-Hant"> 結合報告套裝與不同的結構描述 </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep.html?lang=zh-Hant"> 處理規則、VISTA 和分類與「資料準備」的比較 </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons.html?lang=zh-Hant"> 比較Adobe Analytics與Customer Journey Analytics報告功能的資料處理 </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html?lang=zh-Hant"> 虛擬報告套裝、資料檢視、Adobe Experience Platform沙箱和Analytics來源聯結器 </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja.html?lang=zh-Hant">Adobe Analytics 至 Customer Journey Analytics 的發展進程 </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja-user.html?lang=zh-Hant"> Adobe Analytics使用者的Customer Journey Analytics使用指南 </a> </li>
     <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=zh-Hant#connection-detail"> 使用加強的連線管理功能 </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=zh-Hant#cja-dataviews"> 使用加強的資料檢視功能 </a> </li>
   <td colname="col2" valign="top"><p class="head"> <b>快速入門</b> </p> 
      <ul> 
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=zh-Hant"> Customer Journey Analytics 快速入門 </a> </li> 
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=zh-Hant"> 常見問題</a> </li> 
   </ul> <p class="head"><b>發行說明</b> </p> 
     <li>請參閱最新的 <a href="https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant" format="https" scope="external">Customer Journey Analytics 發行說明</a>，了解新功能和修正內容。 </li>
    <td colname="col3" valign="top"> <p class="head"><b>CUSTOMER JOURNEY ANALYTICSAPI</b> </p> 
    <ul> 
     <li>查看全部 <a href="https://developer.adobe.com/cja-apis/docs/" format="https" scope="external">Customer Journey Analytics API</a>。 </li>
      <li>查看最新 <a href="https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API" format="https" scope="external">Customer Journey Analytics Reporting API</a>。 </li>
    </ul> <p class="head"> <b>Adobe Experience Platform 資源</b> </p> 
    <ul> 
     <li><a href="https://www.adobe.com/tw/experience-platform.html" format="http" scope="external"> Adobe Experience Platform</a> </li> 
     <li> <a href="https://experienceleague.adobe.com/docs/platform-learn/tutorials/overview.html?lang=zh-Hant" format="https" scope="external"> Adobe Experience Platform 教學課程</a> </li> 
     <li><a href="https://www.adobe.io/apis/experienceplatform/home/api-reference.html" format="https" scope="external"> API 參考</a> </li> 
     <li><a href="https://www.adobe.com/tw/experience-platform/documentation-and-developer-resources.html" format="https" scope="external"> 文件與開發人員資源</a> </li>
     <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=zh-Hant" format="https" scope="external"> 如何從傳統 Adobe Analytics 擷取和使用資料的快速入門指南。
     <li><a href="https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant" format="https" scope="external">用於報告套裝資料的 Adobe Analytics 來源連接器</a> </li>
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
