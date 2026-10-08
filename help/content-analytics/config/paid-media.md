---
title: Content Analytics付費媒體自動設定
description: 瞭解資料集、連線、資料檢視等的自動設定。
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
source-git-commit: 2727dce145b996192ac873dd43d5106b011ff736
workflow-type: tm+mt
source-wordcount: '1493'
ht-degree: 4%
---
# 付費媒體自動設定

當您在Content Analytics中啟用付費媒體頻道並儲存設定時，Adobe會使用付費媒體資料集的報表設定來更新所選的連線和資料檢視。 您不需要自行重新建立預設維度、量度、查詢邏輯或摘要資料群組。

會建立三個物件層：

| 物件 | 包含 | 用途 |
| --- | --- | --- |
| 摘要資料集 | 在廣告、體驗放置或資產層級提供Advertising網路效能資料，如有支援，則另外提供人口統計/地理劃分。 | 可讓您測量傳遞次數、點按次數、支出，以及廣告網路回報的結果 |
| 中繼資料和屬性查詢資料集 | 帳戶、行銷活動、廣告群組、廣告、體驗和資產詳細資訊；Content Analytics創意屬性。 | 可讓您使用可辨識的名稱、創意細節、縮圖和內容屬性來報告，而不使用識別碼。 |
| 資料檢視元件和設定 | 維度、量度、計算量度、衍生欄位和摘要資料群組。 | 可讓您建置Workspace分析，而不需手動重建這些資料集之間的關係。 |

啟用付費媒體不會自動將付費媒體資料連結至網站的訂單、預訂或收入。 您的體驗事件資料與付費媒體資料之間的關聯，需要客戶特定的追蹤金鑰對應和報表設定。

## 摘要資料集

下圖顯示當您在Content Analytics中為一個或多個廣告網路啟用付費媒體頻道時，如何產生彙總資料集。 可用廣告網路中的相關API可用來下載體驗、資產和廣告資料，並轉換成6個可能的摘要資料集。

![付費媒體產生摘要資料集](/help/content-analytics/assets/paid-media-generation-of-datasets.svg)

會建立哪些摘要資料集取決於特定廣告網路。 並非每個您已為其設定來源聯結器的廣告網路都會產生所有六個可能的摘要資料集。 請參閱下表，以取得摘要資料集的概觀及下列資訊：

* 摘要資料集名稱、事件型別和元件尾碼
* 實體
* 劃分
* 下列網路的哪些資料集已填入![核取記號](/help/assets/icons2/Checkmark.svg)：
  * ![MetaSolid](/help/assets/icons2/MetaSolid.svg) Meta
  * ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) Google
  * ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) Pinterest
  * ![Snapchat](/help/assets/icons2/Snapchat.svg) Snapchat
  * ![TikTok](/help/assets/icons2/TikTok.svg) TikTok

    >[!AVAILABILITY]
    >
    >Pinterest、Snapchat和TikTok處於發行的有限測試階段，可能尚未在您的環境中提供。 此功能普遍開放使用時，便會移除此注意事項。 如需Customer Journey Analytics發行程式的相關資訊，請參閱[Customer Journey Analytics功能發行](/help/release-notes/releases.md)
    >


* 摘要資料集中的每一列所代表的意義。

| 摘要資料集<br/>事件型別<br/>元件尾碼 | 實體 | 劃分 | ![MetaMulti](/help/assets/icons2/MetaSolid.svg) | ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) | ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) | ![Snapchat](/help/assets/icons2/Snapchat.svg) | ![TikTok](/help/assets/icons2/TikTok.svg) | 每一列代表 |
|---|---|---|:---:|:---:|:---:|:---:|:---:|---|
| `paidmedia_ad_summary` <br/> `ad.summary`<br/>`\| Ad Summary` | 廣告 | 無 | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | 廣告的每日效能，不含人口統計或地理劃分。 |
| `paidmedia_ad_demographics` <br/> `ad.demographics`<br/>`\| Ad Demo` | 廣告 | 年齡、性別 | ![Checkmark](/help/assets/icons2/Checkmark.svg) | | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | 依年齡和性別劃分的廣告每日效能。 |
| `paidmedia_ad_geography` <br/> `ad.geography`<br/>`\| Ad Geo` | 廣告 | 國家/地區 | ![Checkmark](/help/assets/icons2/Checkmark.svg) | | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | 依國家/地區劃分的廣告每日效能。 |
| `paidmedia_experience_placement` <br/> `ad.experience.placement`<br>`\| Experience Placement` | 體驗 | 平台，位置 | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | 與廣告創意體驗相關的每日效能，依平台和位置劃分。 |
| `paidmedia_asset_summary` <br/>`ad.asset.summary`<br/>`\| Asset Summary` | 資產 | 無 | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | | | ![Checkmark](/help/assets/icons2/Checkmark.svg) | 在其廣告/行銷活動內容中的每日資產層級績效，沒有人口統計或地理劃分。 |
| `paidmedia_assets_demographics` <br/> `ad.asset.demographics`<br/>`\| Asset Demo` | 資產 | 年齡、性別 | ![Checkmark](/help/assets/icons2/Checkmark.svg) | | | | | 在其廣告/行銷活動內容中的每日資產層級績效，依年齡和性別細分。 |


此表格說明資料集涵蓋範圍，並不保證每個量度或中繼資料欄位都由特定網路填入。 檢查分析所需的欄位。 無法使用的欄位或不支援的劃分與欄位測量到的零值不同。

描述帳戶、行銷活動、廣告群組、廣告、體驗和資產的個別查詢資料集。 它們會使用實體GUID提供名稱和中繼資料。 摘要資料集和六個查詢資料集之間沒有一對一的配對。

摘要資料分組會將相等的維度彙整在一起；分組不會將六個效能量度總計加總。

## 元件

Content Analytics付費媒體管道啟用後，也會產生許多資料檢視元件。 這些元件會提供元件尾碼，以區別彼此的類似命名元件。

### 量度

不同的廣告網路會傳回不同的效能劃分。 Content Analytics會保留這些差異，而非將每個版本的量度視為可互換。

例如：

| 元件 | 含義 | 適當的開始分析 |
| --- | --- | --- |
| 點選次數\|廣告摘要 | 在廣告的無劃分層級報告的點按次數 | 行銷活動或廣告效益 |
| 點選次數\|資產摘要 | 資產層級報告的點按次數 | Creative-asset效能 |
| 點選次數\|廣告地理 | 廣告地理報表的點按次數 | 依國家或地區的績效 |
| 點選次數\|體驗位置 | 體驗放置報表的點按次數 | Creative各位置績效 |

每個點按量度元件會提供不同的報表內容。 您不能僅將這些量度元件總計為總量。 同一個基礎廣告活動可以在多個摘要資料集中表示。

### 維度

每個摘要資料集都包含ID和GUID。 ID是廣告網路提供的身分識別（帳戶、行銷活動、廣告群組、廣告、體驗和資產），且在&#x200B;**廣告網路資料中是唯一的**。 GUID是Adobe提供的身分識別（適用於帳戶、行銷活動、廣告群組、廣告、體驗和資產），且在&#x200B;**個廣告網路中是唯一的**。 ID和GUID可用來查詢對應的名稱和中繼資料。

### 衍生欄位

衍生欄位是自動報告設定的一部分。 衍生欄位會將識別碼轉譯為名稱和中繼資料、公開創意屬性，並支援跨報表來源使用的對等維度。 它們不會建立其他廣告活動或自動歸因網站轉換。

在分析中的量度使用相同的劃分，以及該劃分支援的維度。 請注意，人口統計和地理總計並不一定等於廣告網路的未劃分總計，也不表示擷取失敗。

## 報告與分析

完成Content Analytics付費媒體設定和擷取後，您就可以開始報告和分析。 如需一些範例，請參閱下表。 使用標準分組維度（如果可用），並從相符的報告層級選擇量度。

| 業務問題 | 開始層級 | 行和劃分 | 開始量度 | 重要界限 |
| --- | --- | --- | --- | --- |
| 我的行銷活動和廣告表現如何？ | 廣告摘要 | 行銷活動名稱、廣告群組名稱、廣告名稱；可選擇廣告網路和帳戶名稱 | 曝光數\|廣告摘要、點按數\|廣告摘要、支出\|廣告摘要、比對CTR和CPC | 使用單一層級進行傳遞/支出總計；在合併帳戶之前驗證貨幣 |
| 哪些創意資產獲得最強的回應？ | 資產摘要 | 資產名稱（付費媒體）、資產身分；可選擇廣告網路 | 曝光數\|資產摘要、點按數\|資產摘要、點進率\|資產摘要 | 這是網路所報告的資產效能，不是日後站上轉換的證據 |
| 哪些影像特徵與效能相關？ | 資產摘要 | 資產標籤、資產物件、資產人員類別、資產場景或其他可用的資產屬性 | 資產摘要曝光數、點按數和CTR | 屬性擷取必須可用；多值屬性類別可以重疊 |
| 哪些訊息特徵與付費效能有關？ | 體驗位置 | 體驗關鍵字、體驗色調、體驗說服策略或其他可用的體驗屬性；可選擇平台和位置 | 曝光次數\|體驗位置、點選次數\|體驗位置，符合CTR | 需要填入體驗屬性；結果會因位置而異，說明關聯，而非因果影響 |
| 哪些位置表現最佳？ | 體驗位置 | 體驗名稱、平台、位置 | 曝光次數\|體驗位置、點選次數\|體驗位置，符合CTR | 位置定義和可用值因廣告網路而異 |
| Meta和Google的廣告/資產/體驗有何差異？ | 為問題選擇的廣告摘要、資產摘要或體驗位置 | 廣告網路與適當的行銷活動、資產或體驗維度 | 兩個網路的相同層級和度量定義 | 僅比較兩個網路填入的欄位；Google不會在此模型中填入三個人口統計/地理摘要 |

這些報表可顯示創意屬性與效能之間的關聯，但不能證明屬性造成了結果。

避免不相容的組合：資產名稱（付費媒體）與廣告摘要量度無法取代資產報表。 使用「資產摘要」量度進行資產分析，並使用「廣告地理」量度進行區域分析。 來自不相容配對的空白或零儲存格不應解譯為無活動的證明。

### 廣告行銷活動績效範例

您想要報告廣告層級的促銷活動成效。 在Analysis Workspace中，使用促銷活動名稱作為維度（列），並使用下表所述的量度。 每個量度都有相同的元件尾碼。

| 量度 | 報告層級 |
| --- | --- |
| 曝光數 | 廣告摘要 |
| 點擊數 | 廣告摘要 |
| 支出 | 廣告摘要 |
| 點進率 | 廣告摘要 |
| 每次點按成本 | 廣告摘要 |

可選擇性地依「廣告名稱」劃分「促銷活動名稱」，但將全部五個欄保留在「廣告摘要」層級。

若要調查個別資產，請使用單獨的表格，其中包含「資產名稱」（付費媒體）和相符的「資產摘要」欄。 請勿將兩個表格的總計相加。

### 網路最佳表現廣告範例

您想瞭解Meta廣告在哪裡表現最佳嗎？

若要調查，請使用地理和人口統計的其他劃分。 使用「促銷活動名稱」或「廣告名稱」作為維度，並使用下表所述的量度。 每個量度都有相同的元件尾碼。

| 量度 | 報告層級 |
| --- | --- |
| 曝光數 | 廣告地理 |
| 點擊數 | 廣告地理 |
| 支出 | 廣告摘要 |
| 點進率 | 廣告地理 |
| 每次點按成本 | 廣告摘要 |


