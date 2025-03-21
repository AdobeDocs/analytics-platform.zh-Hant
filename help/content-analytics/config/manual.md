---
title: Content Analytics手動設定
description: 如何手動設定內容分析
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 01459765d84a46d170c1619ffeae184957bbf839
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 1%

---

# Content Analytics手動設定

{{draft-aca}}

{{release-limited-testing}}

本文詳細說明啟動或停用Content Analytics設定或編輯您的Content Analytics實作所需的手動動作。

下列手動組態動作可供使用：

## 啟動

若要啟動新組態或您對現有組態所做的變更，請執行下列動作：

1. 您必須遵循[發佈流程](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}。 成功發佈包含Content Analytics設定的Tags屬性資料庫。

1. 您必須在開發、預備或發佈環境的頁面之`<head>`元素中[安裝](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation)內嵌程式碼，並受限於Content Analytics。


## 停用

若要停用內容分析資料的集合：

1. 移除開發、預備或生產環境中頁面之`<head>`元素中的[內嵌程式碼](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments)，受限於Content Analytics。
1. [刪除](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)您Content Analytics組態的相關聯標籤屬性。



## 修改

您可以使用[引導式組態精靈](guided.md)，對已實作的組態進行一些微幅變更。 例如，變更資料檢視。

您可在與Content Analytics設定相關聯的Tags屬性中使用[Adobe Content Analytics擴充功能](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview)，以變更下列成品：

* [沙箱和資料流](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}。

  >[!CAUTION]
  >
  >請確認您在Adobe Content Analytics擴充功能中設定的沙箱和資料串流，已在先前的階段使用[引導式設定](guided.md)為Content Analytics進行設定。 此設定確保所有必要的成品都可供使用。<br/><br/>同時確認沙箱或資料串流的更新不會干擾另一個設定為使用相同沙箱或資料串流的Content Analytics設定。
  >

* [體驗擷取與定義](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  您可以編輯規則運算式來修改方式。

* [事件篩選](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}

  您可以編輯規則運算式，以修改篩選頁面和資產的方式。


在Adobe Content Analytics擴充功能中進行變更後，請確定您使用[發佈流程](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}來啟用變更。



>[!MORELIKETHIS]
>
>[引導式設定](guided.md)
>[資料收集標籤發佈概觀](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>


## 版本設定

如果您需要設定Content Analytics體驗的版本，您必須在您認為要分析的體驗頁面上新增全域`adobe.getContentExperienceVersion`函式。

`adobe.getContentExperienceVersion`函式應傳回字串作為值（可以是您選擇的任何值），以識別版本。 此版本已附加至[Experience ID URL](/help/content-analytics/report/components.md#experience-metadata)。

如果函式不存在或函式未傳回任何值，則會使用值`NoVersion`作為預設值。

### 範例

```
function adobe.getContentExperienceVersion() {
  return "1.0";
}
```
