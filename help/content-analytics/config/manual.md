---
title: Content Analytics 手動設定
description: 如何手動設定 Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 6d23203468032510446711ff5a874fd149531a9a
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 100%

---

# Content Analytics 手動設定

本文章詳細說明開始或停止 Content Analytics 設定的資料收集，或編輯 Content Analytics 實施所需的手動動作。

下列手動設定動作可供使用：

## 開始資料收集

若要針對已實施的 Content Analytics 設定開始進行資料收集：

1. 依照[發佈流程](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/publish/overview){target="_blank"}進行操作。成功發佈內含您 Content Analytics 設定的標記屬性庫。

1. 根據 Content Analytics，在開發、中繼或發佈環境中的 `<head>` 頁面元素內[安裝](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/publish/environments/environments#installation)嵌入代碼。


## 停止資料收集

若要針對已實施的 Content Analytics 設定停止進行資料收集：

1. 根據 Content Analytics，在開發、中繼或生產環境中的 `<head>` 頁面元素內移除[嵌入代碼](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/publish/environments/environments)。
1. [刪除](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/publish/overview) Content Analytics 設定的相關標記屬性。



## 修改資料收集

您可以使用[引導式設定精靈](guided.md)對已實施的設定進行一些細微的變更。例如，變更資料檢視，或啟用或者停用體驗。

您可以使用與 Content Analytics 設定關聯之標記屬性中的 [Adobe Content Analytics 擴充功能](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/extensions/client/content-analytics/overview)來變更下列成品：

* [沙箱和資料流](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}。

  >[!CAUTION]
  >
  >驗證您在 Adobe Content Analytics 擴充功能中設定的沙箱和資料流，是否在早期階段已使用[引導式設定](guided.md)針對 Content Analytics 進行過設定。此設定能確保所有必要的成品均可使用。<br/><br/>亦驗證沙箱或資料流的更新不會干擾設定為使用相同沙箱或資料流的 Content Analytics 設定。
  >

* [體驗擷取與定義](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  您可以啟用或停用體驗，以及編輯規則運算式和查詢參數的組合，確認內容在您網站上的轉譯方式。

* [事件劃分](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting){target="_blank"}

  您可以編輯規則運算式來修改頁面和資產的劃分方式。


在 Adobe Content Analytics 擴充功能中進行變更後，請確保使用[發佈流程](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/publish/overview){target="_blank"}開始根據所做的變更收集資料。



>[!MORELIKETHIS]
>
>[引導式設定](guided.md)
>[資料收集標記發佈概觀](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/publish/overview)
>


## 版本設定

如果您想收集 Content Analytics 體驗，您應該考慮實施版本設定以確保正確收集新的體驗 (您網頁的變更)。

若要實現版本設定，請在您認為想要分析之體驗的頁面上新增一個全域 `adobe.getContentExperienceVersion` 函數。

`adobe.getContentExperienceVersion` 函數應會傳回字串做為值，藉以識別版本，該值可以是您選擇的任何內容。此版本會附加至[體驗 ID URL](/help/content-analytics/report/components.md#experience-metadata)。

若函數不存在或函數沒有傳回值，則會使用值 `NoVersion` 做為預設值。

### 範例

```
window.adobe = window.adobe || {};
window.adobe.getContentExperienceVersion = () => {
  return "1.0";
};
```
