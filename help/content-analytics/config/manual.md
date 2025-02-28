---
title: Content Analytics手動設定
description: 如何手動設定內容分析
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---

# Content Analytics手動設定

>[!WARNING]
>
>本文是即將推出之最終版本的初步非官方草稿版本，屬於內容分析檔案的一部分。 所有內容可能會有所變更，而目前的本文版本概不提供任何法律義務。
>

{{release-limited-testing}}

本文詳細說明啟動或停用Content Analytics設定或編輯您的Content Analytics實作所需的手動動作。

下列手動組態動作可供使用：

## 啟動

若要啟用新設定或您對現有設定所做的變更，您必須[發佈](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}關聯的標籤屬性。 只有當您發佈內容分析標籤屬性時，才會收集您已設定之網域、體驗和資產的內容分析資料。


## 停用

若要停用收集內容分析資料，請[取消發佈](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}內容分析組態的相關聯標籤屬性。



## 修改

一般而言，您應該使用[引導式設定精靈](guided.md)來變更您的實作。

或者，您可以使用與內容分析設定相關聯之「標籤」屬性中的「Adobe內容分析」擴充功能，變更下列成品：

* [沙箱和資料流](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}。

  >[!CAUTION]
  >
  >您必須確認您在Adobe Content Analytics擴充功能中設定的沙箱和資料串流，已在先前的階段使用[引導式設定](guided.md)為內容分析進行設定。 此設定確保所有必要的成品都可供使用。<br/><br/>您也必須確認沙箱或資料串流的更新不會干擾另一個設定為使用相同沙箱或資料串流的Content Analytics設定。
  >

* [事件篩選](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}。

  您可以編輯規則運算式，以修改篩選頁面和資產的方式。


在Adobe Content Analytics擴充功能中進行變更後，請確定您[啟用](#activate)您的變更。



>[!MORELIKETHIS]
>
>[引導式設定](guided.md)
>[資料收集標籤發佈概觀](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>