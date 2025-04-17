---
title: Content Analytics 手動設定
description: 如何手動設定 Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 981cd0c01d775acbd71cada7efed4911b4bcb157
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 3%

---

# Content Analytics 手動設定

{{release-limited-testing}}


本文詳細說明啟動或停止Content Analytics設定的資料收集，或編輯您的Content Analytics實作所需的手動動作。

下列手動組態動作可供使用：

## 開始資料收集

若要開始實作Content Analytics設定的資料收集：

1. 遵循[發佈流程](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}。 成功發佈包含Content Analytics設定的Tags屬性資料庫。

1. [安裝](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation)內嵌程式碼，於您的開發、預備或發佈環境之頁面的`<head>`元素中，並遵守Content Analytics。


## 停止資料收集

若要停止實作Content Analytics設定的資料收集：

1. 移除開發、預備或生產環境中頁面之`<head>`元素中的[內嵌程式碼](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments)，受限於Content Analytics。
1. [刪除](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)您Content Analytics組態的相關聯標籤屬性。



## 修改資料彙集

您可以使用[引導式組態精靈](guided.md)，對已實作的組態進行一些微幅變更。 例如，變更資料檢視，或啟用或停用體驗。

您可在與Content Analytics設定相關聯的Tags屬性中使用[Adobe Content Analytics擴充功能](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview)，以變更下列成品：

* [沙箱和資料流](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}。

  >[!CAUTION]
  >
  >請確認您在Adobe Content Analytics擴充功能中設定的沙箱和資料串流，已在先前的階段使用[引導式設定](guided.md)為Content Analytics進行設定。 此設定確保所有必要的成品都可供使用。<br/><br/>同時確認沙箱或資料串流的更新不會干擾另一個設定為使用相同沙箱或資料串流的Content Analytics設定。
  >

* [體驗擷取與定義](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  您可以啟用或停用體驗，以及編輯規則運算式和查詢引數的組合，以決定如何在您的網站上呈現內容。

* [事件篩選](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}

  您可以編輯規則運算式，以修改篩選頁面和資產的方式。


在Adobe Content Analytics擴充功能中進行變更後，請確定您使用[發佈流程](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}來根據所做的變更開始收集資料。



>[!MORELIKETHIS]
>
>[引導式設定](guided.md)
>[資料收集標籤發佈概觀](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>


## 版本設定

如果您想要收集Content Analytics體驗，您應考慮實作版本設定，以確保正確收集新體驗（對網頁的變更）。

若要實作版本設定，請在您要分析之體驗的頁面上新增全域`adobe.getContentExperienceVersion`函式。

`adobe.getContentExperienceVersion`函式應傳回字串作為值（可以是您選擇的任何值），以識別版本。 此版本已附加至[Experience ID URL](/help/content-analytics/report/components.md#experience-metadata)。

如果函式不存在或函式未傳回任何值，則會使用值`NoVersion`作為預設值。

### 範例

```
window.adobe = window.adobe || {};
window.adobe.getContentExperienceVersion = () => {
  return "1.0";
};
```
