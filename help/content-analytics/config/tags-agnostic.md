---
title: Content Analytics標籤無關設定
description: 瞭解如何在不使用Experience Platform資料收集標籤的情況下設定Content Analytics。
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
source-git-commit: d15d85f5904bbada26bfd74fdc45217efeddd723
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 5%

---


# Content Analytics Tags不可知的設定

Adobe Content Analytics JavaScript資料庫可透過Experience Platform Edge Network將內容資料傳送至Adobe Experience Platform，讓您追蹤網站上的內容相關事件。 當您想要實作Content Analytics而不使用Adobe Experience Platform標籤(Launch)時，請使用此資料庫。

>[!NOTE]
>
>本文適用於Web Channel的Content Analytics 。


>[!PREREQUISITES]
>
>* 呼叫`initializeContentLibrary`之前，必須在頁面上初始化Adobe Experience Platform Web SDK (Alloy)。
>* 完成Content Analytics引導式設定精靈，引導您完成設定Content Analytics設定先決條件所需的所有步驟。
>* 引導式設定完成後，您的特定設定JavaScript設定即可在設定檢視中使用。


## 安裝

您可以透過兩種方式安裝程式庫：

### npm套件

使用`npm`安裝程式庫。

1. 在命令列上，使用：

   ```bash
   npm install @adobe/content-analytics
   ```

1. 匯入程式庫：

   ```JavaScript
   import initializeContentLibrary from "@adobe/content-analytics";
   ```

### 指令碼標籤(CDN)

直接從CDN載入程式庫。

1. 初始化[Web SDK JavaScript資料庫](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/install/library)並載入Content Analytics套件：

   ```html
   <!-- 1. Load and configure Alloy first -->
   <script src="https://cdn1.adoberesources.net/alloy/2.x.x/alloy.min.js"></script>
   <script>
   alloy("configure", {
       datastreamId: "YOUR_DATASTREAM_ID",
       orgId: "YOUR_ORG_ID@AdobeOrg",
   });
   </script>
   
   <!-- 2. Load Content Analytics -->
   <script src="https://cdn1.adoberesources.net/content-analytics/1.x.x/content-analytics.min.js"></script>
   <script>
   window.contentAnalytics({
       datastreamId: "YOUR_DATASTREAM_ID",
   });
   </script>
   ```

   位置
   * `alloy/2.x.x`參考您要使用[Web SDK JavaScript資料庫](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/install/library)的版本。
   * `content-analytics/1.x.x`參考您要使用Content Analytics SDK資料庫的版本。

2. 獨立組建會公開`window.contentAnalytics`做為初始化函式。


## 資料流設定

`datastreamId`選項為必要項，且必須參考資料流，該資料流的Experience Platform服務已設定啟用Content Analytics體驗事件資料集。 確定與資料流關聯的沙箱尚未與其他Content Analytics設定關聯。

您可以為每個環境提供個別的資料串流ID：

```javascript
initializeContentLibrary({
  datastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",          // production
  stagingDatastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",   // optional
  developmentDatastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx", // optional
});
```

## 體驗擷取與定義

啟用體驗追蹤並控制如何在您的網站上識別體驗。 體驗的定義方式是結合&#x200B;**網域規則運算式**&#x200B;與選擇性的&#x200B;**查詢引數**，在相符頁面中區分不同的體驗。

| 選項 | 類型 | 預設 | 說明 |
|--------|------|---------|-------------|
| `includeExperiences` | 布林值 | `false` | 啟用頁面/體驗檢視追蹤 |
| `experienceConfigurations` | 陣列 | - | 依網域規則運算式和查詢引數定義體驗 |

`experienceConfigurations`中的每個專案都接受：

| 屬性 | 類型 | 說明 |
|----------|------|-------------|
| `regEx` | 字串 | 網域規則運算式符合頁面URL （例如`^(?!.*\b(store\|help\|admin)\b)`） |
| `queryParameters` | 陣列 | 其值可區分相符頁面上的體驗的查詢引數名稱（例如`["outdoors", "patio", "kitchen"]`） |

### 範例

如需如何使用網域規則運算式和查詢引數啟用體驗追蹤的範例，請參閱下文。

```javascript
initializeContentLibrary({
  datastreamId: "YOUR_DATASTREAM_ID",
  includeExperiences: true,
  experienceConfigurations: [
    {
      regEx: "^https://www\\.example\\.com/products",
      queryParameters: ["category", "collection"],
    },
    {
      regEx: "^https://www\\.example\\.com/blog",
      queryParameters: [],
    },
  ],
});
```

## 事件篩選

使用規則運算式控制哪些頁面URL和資產URL包含在資料收集中。 使用下列模式範例作為起點，並在部署之前使用規則運算式測試器驗證模式。

| 選項 | 類型 | 預設 | 說明 |
|--------|------|---------|-------------|
| `pageUrlQualifier` | 字串（規則運算式） | - | 僅追蹤URL符合此模式的頁面 |
| `assetUrlQualifier` | 字串（規則運算式） | - | 僅追蹤URL符合此模式的資產 |
| `excludeURLsFromTracking` | 陣列 | `[]` | 要從追蹤排除的URL字串清單 |

### 範例

如需如何從Content Analytics排除檔案頁面，以及僅考慮Content Analytics產品影像的範例，請參閱下文。

```javascript
initializeContentLibrary({
  datastreamId: "YOUR_DATASTREAM_ID",
  pageUrlQualifier: "^(?!.*\\/documentation).*",
  assetUrlQualifier: ".*\\/products\\/.*\\.(?:jpg|png|webp)",
  excludeURLsFromTracking: [
    "https://www.example.com/internal",
    "https://www.example.com/staging",
  ],
});
```
