---
title: Content Analytics手動設定
description: 如何手動設定內容分析
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 35298dd6d18ebb07d104a608aeff06cb864ee1dc
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 1%

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

若要啟動新組態或您對現有組態所做的變更，請執行下列動作：

1. 您必須遵循[發佈流程](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}。 只有當您成功發佈包含您的Content Analytics設定之Tag屬性的資料庫時，系統才會收集您已設定的網域、體驗和資產的Content Analytics資料。

1. 您必須在開發、預備或發佈環境的頁面之`<head>`元素中[安裝](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation)內嵌程式碼，並受內容分析限制。


## 停用

若要停用收集內容分析資料：

1. 移除開發、預備或生產環境之頁面的`<head>`元素中的[內嵌程式碼](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments)，並受限於內容分析。
1. [刪除](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)內容分析組態的相關標籤屬性。



## 修改

一般而言，您應該使用[引導式設定精靈](guided.md)來變更您的實作。

或者，您可以使用與內容分析組態相關之Tag屬性中的[Adobe Content Analytics擴充功能](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview)，變更下列成品：

* [沙箱和資料流](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}。

  >[!CAUTION]
  >
  >您必須確認您在Adobe Content Analytics擴充功能中設定的沙箱和資料串流，已在先前的階段使用[引導式設定](guided.md)為內容分析進行設定。 此設定確保所有必要的成品都可供使用。<br/><br/>您也必須確認沙箱或資料串流的更新不會干擾另一個設定為使用相同沙箱或資料串流的Content Analytics設定。
  >

* [事件篩選](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}

  您可以編輯規則運算式，以修改篩選頁面和資產的方式。


在Adobe Content Analytics擴充功能中進行變更後，請確定您使用[發佈流程](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}來啟用變更。



>[!MORELIKETHIS]
>
>[引導式設定](guided.md)
>[資料收集標籤發佈概觀](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>


## 版本設定

如果您需要設定內容分析體驗的版本，必須在您視為要分析的體驗的頁面上新增全域`adobe.getContentExperienceVersion`函式。

`adobe.getContentExperienceVersion`函式應傳回字串作為值，該值可以是您選擇用來識別版本的任何值。 版本會附加至Experience ID URL。

如果函式不存在或函式未傳回任何值，則會使用值`NoVersion`作為預設值。

### 範例

```
function adobe.getContentExperienceVersion() {
  return "1.0";
}
```
