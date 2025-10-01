---
title: Content Analytics 手動設定
description: 如何手動設定 Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: a3d974733eef42050b0ba8dcce4ebcccf649faa7
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 70%

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
>&#x200B;>[資料收集標記發佈概觀](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/publish/overview)
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

## 身分識別

Content Analytics會透過下列方式處理身分：

* ECID會自動填入Content Analytics結構描述的`identityMap`部分。
* 如果您需要`identityMap`中的其他身分識別值，則需在Web SDK擴充功能的`onBeforeEventSend`回呼中設定這些值。
* 不支援欄位式拚接，因為結構描述是系統所擁有。 因此，您無法新增其他欄位到結構描述以支援欄位式拼接


若要確保Content Analytics身分資料和Adobe Experience Platform Web SDK資料身分資料在欄位層級正確連結，您必須在事件傳送[回撥前修改網站SDK &#x200B;](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/web-sdk/commands/configure/onbeforeeventsend){target="_blank"}。

1. 導覽至包含Adobe Experience Platform Web SDK擴充功能和Adobe Content Analytics擴充功能的&#x200B;**[!UICONTROL 標籤]**&#x200B;屬性。
1. 選取![外掛程式](/help/assets/icons/Plug.svg) **[!UICONTROL 擴充功能]**。
1. 選取&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]**&#x200B;擴充功能。
1. 選取&#x200B;**[!UICONTROL 設定]**。
1. 在&#x200B;**[!UICONTROL SDK執行個體]**&#x200B;區段中，向下捲動至&#x200B;**[!UICONTROL 資料彙集]** - **[!UICONTROL 開啟，然後事件傳送回呼]**。

   ![在事件傳送回撥之前](/help/content-analytics/assets/onbeforeeventsendcallback.png)

1. 選取&#x200B;**[!UICONTROL &lt;/>在事件傳送回撥程式碼]**&#x200B;前提供。
1. 新增下列程式碼：

   ```javascript
   window.adobeContentAnalytics?.forwardEvent(content);
   
   content.xdm.identityMap = _satellite.getVar('identityMap');
   if ((content.xdm.eventType === "content.contentEngagement") && (_satellite.getVar('identityMap') != null)) {
      return true;
   }
   ```

   ![在事件傳送回撥之前](/help/content-analytics/assets/onbeforeeventsendcallbackcode.png)

1. 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存程式碼。
1. 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存副檔名。
1. [發佈](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/publish/overview)標籤屬性的更新。





