---
title: 將付費媒體資料擷取至Customer Journey Analytics
description: 瞭解如何透過Adobe Experience Platform來源聯結器擷取付費媒體資料，以及在Customer Journey Analytics中準備連線、資料檢視和量度。
solution: Customer Journey Analytics
feature: Use Cases
hold: true
role: Admin
source-git-commit: 29a21d57b6b50d873a4464d1a705c1b4855dd3ea
workflow-type: tm+mt
source-wordcount: '1198'
ht-degree: 0%
---

# 擷取及使用付費媒體資料

付費媒體資料包含來自[!DNL Meta Ads]、[!DNL Google Ads]、[!DNL TikTok]和[!DNL LinkedIn]等平台的廣告效能和中繼資料。 本指南說明如何將這些資料擷取至Adobe Experience Platform，並提供給Customer Journey Analytics用於報告和分析。

付費媒體資料通常要經過三個階段：

1. Advertising平台提供行銷活動、廣告、資產和效能資料。
1. Adobe Experience Platform會透過來源聯結器擷取該資料，並將其儲存在標準付費媒體資料集中。
1. Customer Journey Analytics會透過連線和資料檢視公開資料集，讓您能夠在Workspace中分析資料。

付費媒體資料是透過Experience Platform來源聯結器擷取。 例如，您可以在Advertising類別中使用[!DNL Meta Ads]聯結器。 當您連線支援的來源時，Adobe會根據全域付費媒體方案和欄位群組來布建標準付費媒體資料集。

## 先決條件

請確定您在Experience Platform中擁有下列存取權：

* 檢視和管理來源的許可權。
* 建立結構描述、資料集和資料流程的許可權。
* 選取要使用的沙箱。 繼續進行設定步驟之前，請先選擇沙箱。

如果您使用[!DNL Meta Ads]做為來源，請確定您也有下列必要條件：

* [!DNL Meta Business Manager]帳戶至少有一個使用中的廣告帳戶，其中包含行銷活動、廣告集、廣告和資產。
* 已針對[!DNL Graph API]和[!DNL Marketing API]授權的[!DNL Meta]應用程式，已在[!DNL Meta]開發人員主控台中設定，並連結至[!DNL Business Manager]。
* 已核准應用程式的`ads_read`和`ads_management`範圍。
* 授權連線的使用者的廣告商層級或更高的存取權。
* 已驗證[!DNL Meta]使用者介面中預期廣告帳戶的存取權。

聯結器的驗證使用[!DNL OAuth 2.0]。 在安裝期間，您登入並授予聯結器的存取權。 由於存取權杖已過期，請準備好在撤銷授權時重新授權連線。

## 資料模型

[Content Analytics付費媒體自動設定](/help/content-analytics/config/paid-media.md)詳細說明付費媒體資料模型。 該自動設定會建立並設定所需的一般資料集和元件，以及專門用於分析內容。

若要瞭解付費媒體資料模型，請參閱本檔案。 用它來決定要在Customer Journey Analytics中使用哪些資料集。 已設定的來源聯結器會產生這些資料集。

## 擷取付費媒體資料

使用以下程式來連線來源，並將付費媒體資料擷取到Experience Platform：

1. 確認您擁有必要的Experience Platform來源許可權和廣告平台存取權。
1. 在Experience Platform中，移至&#x200B;**[!UICONTROL 來源]** > **[!UICONTROL 目錄]** > **[!UICONTROL Advertising]**。
1. 確保您處於包含付費媒體資料集的沙箱中。
1. 選取您要使用的聯結器，例如&#x200B;**[!DNL Meta Ads]**。 選取[設定] ****&#x200B;以建立新連線，或選取[新增資料] ]**以將更多資料新增到現有連線。**[!UICONTROL 
1. 以具有所需廣告商層級存取許可權的使用者登入，向[!DNL OAuth 2.0]進行驗證。
1. 選取您要內嵌的廣告帳戶、實體和insight資料。
1. 確認查詢資料集和摘要量度資料集已正確布建。
1. 輸入資料流設定、確認目標資料集，然後設定擷取排程。
1. 儲存資料流並監視&#x200B;**[!UICONTROL 來源]** > **[!UICONTROL 資料流]**&#x200B;中的執行。
1. 驗證標準付費媒體資料集是否存在並包含資料。

前往Customer Journey Analytics前，請先驗證擷取的資料：

* 確認實體`GUID`和原生ID值在摘要度量和查詢資料集中均以一致的方式填入。
* 確認每個摘要量度列都包含時間戳記。
* 確認例如維度（例如： `channel`、`adNetwork`）與量度（例如： `impressions`、`clicks`、`spend`）的關鍵報表欄位包含值。 請注意，並非所有來源平台都會填入某些欄位，例如`region`。
* 確認相關帳戶的貨幣和時區值一致。

## 使用付費媒體資料

Customer Journey Analytics不會直接針對Experience Platform資料集製作報表。 相反地，您會透過連線公開資料集，然後建立資料檢視，定義報告中使用的維度、量度和邏輯。

### 建立或更新連線

請使用下列程式來建立或更新連線：

1. 在Customer Journey Analytics中，[建立或編輯現有的連線](/help/connections/create-connection.md)。
1. 請確保您選取的沙箱包含付費媒體資料集，做為連線設定的一部分。
1. 將摘要量度資料集新增為摘要資料。 如果有多個摘要量度資料集可供使用，請使用[搜尋](/help/connections/create-connection.md#add-datasets)依`Paid Media`類別篩選，以識別正確的資料集。
1. 將每個查詢資料集新增為查詢資料集。 使用帳戶、行銷活動、廣告群組、廣告、資產和體驗的對應實體GUID識別碼（Adobe產生的全域索引鍵），將查詢資料集加入摘要資料。 有些來源平台也支援加入原生ID值。
1. 如果您想要將彙總付費媒體資料與共用中繼資料（例如ID、追蹤程式碼或`UTM`引數）建立關聯，您可以選擇性地新增點按流事件資料。
1. 檢閱每個資料集的[資料集專屬設定](/help/connections/create-connection.md#dataset-settings)。
1. 儲存連線並確認連線開始回填資料。

付費媒體資料是彙總資料，不依賴人員層級的身分拼接。 摘要表格中的實體識別碼可用來聯結查閱表格中的類似身分。

### 建立資料釋圖

連線準備就緒後，您需要為連線建立或編輯一個或多個資料檢視：


1. 在Customer Journey Analytics中，[建立或編輯一或多個資料檢視](/help/data-views/create-dataview.md)：
1. 定義預設設定，例如時區和貨幣。
1. 新增付費媒體分析所需的元件。

包含下列元件：

* **維度**：行銷活動、頻道、廣告網路、廣告群組、廣告、資產、帳戶、地區和裝置型別。
* **量度**：曝光數、點按數、點進率、支出、轉換、轉換值、參與，以及相關視訊或曝光分享量度。
* **衍生欄位**：使用[剖析](/help/data-views/derived-fields/derived-fields.md#url-parse)、[規則運算式](/help/data-views/derived-fields/derived-fields.md#regex-replace)或[查詢](/help/data-views/derived-fields/derived-fields.md#lookup)邏輯，將維度標準化或分類，以產生跨廣告網路一致的管道和促銷活動值。
* **摘要群組**： [將來自多個資料集的相關值合併為單一報告維度](/help/data-views/component-settings/summary-data-group.md)，例如統一的付費管道維度。
* **計算量度**：定義可重複使用的效率量度，例如CPC、CPM、CPA、CTR和轉換率。

### 建立專案

若要回報及分析付費媒體資料，請在Analysis Workspace中建立專案。

## 驗證

使用下列檢查清單來驗證實施。

### Adobe Experience Platform檢查

* 確認來源許可權和Ad-Platform存取權已就緒。
* 確認聯結器已驗證，且資料流已依排程執行。
* 確認所有付費媒體資料集皆存在且已填入。
* 確認結構描述使用全域付費媒體類別和欄位群組。
* 確認已填入聯結金鑰、時間戳記和金鑰報告欄位。

### Customer Journey Analytics檢查

* 確認連線包含摘要量度資料集和六個查詢資料集。
* 確認資料檢視包含必要的廣告維度和付費媒體量度。
* 確認衍生欄位會如預期般標準化頻道和行銷活動值。
* 確認摘要分組會視需要整合多網路資料。
* 確認已為貴組織使用的比率定義計算量度。
* 確認Workspace報表與來源廣告平台報表一致。


>[!MORELIKETHIS]
>
>[Meta Ads來源聯結器](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/advertising/meta-ads)
>[Content Analytics付費媒體自動設定](/help/content-analytics/config/paid-media.md)
