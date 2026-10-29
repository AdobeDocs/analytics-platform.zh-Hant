---
title: 與同事一起分析和建置Workspace專案
description: 使用同事的產品內體驗來摘要開啟的專案、尋找深入分析，以及從自然語言提示建立面板、表格和區段。
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ae3aff40-b2f6-4df1-8c01-0b0720d1510f
    internal-label: AI Tools
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: 88e67c92fc170b340149c9ab73ad5eea2122da2b
workflow-type: tm+mt
source-wordcount: '1960'
ht-degree: 1%
---
# 使用同事的產品內體驗

>[!AVAILABILITY]
>
>本區段中描述的功能處於發佈的有限測試階段，可能尚未開放使用於您的環境中。 此外， Co-worker使用產生式AI，可能會產生不準確或意外的結果。 在您對專案採取行動或共用專案之前，請先檢閱同事的回應以及它對專案所做的任何變更。

同事的產品內體驗可在Analysis Workspace右側的聊天面板中取得。 Co-worker使用開啟的專案作為前後關聯，因此您可以詢問您的分析或讓Co-worker建置專案，而無需說明其中包含的內容。

## 瞭解Workspace中的同事

### 先決條件

* **為您的組織啟用同事**：同事的產品內體驗預設為停用。 Customer Journey Analytics管理員必須先為組織啟用此功能，使用者才能加以存取。

  如果您無法存取Workspace中的同事，請聯絡您的管理員。 如需詳細資訊，請參閱[IMS組織偏好設定](/help/analysis-workspace/user-preferences.md#ims-organization-preferences)。<!-- need to update this section with the new toggle -->

* **資料檢視存取**：同事使用您現有的Analysis Workspace和資料檢視許可權。 無法存取您尚未存取的資料或元件。

<!--
FOLLOW-UP: Coworker permissions are still being finalized. The Coworker permission name below is a placeholder. Confirm the name, category, and Admin Console steps with the SME.

* **Permissions**: In the [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] **[!UICONTROL Coworker]** permission determines access to Coworker. A [product profile administrator](https://helpx.adobe.com/tw/enterprise/using/manage-product-profiles.html) must add this permission to your product profile. For more information, see [Access control](/help/technotes/access-control.md#access-control).

-->

### 在Workspace中的同事與同事應用程式之間選擇

同事的產品內體驗具有許多與[CX Enterprise Coworker應用程式](https://experienceleague.adobe.com/zh-hant/docs/coworker/content/chat/use-cases/data-insights/analytics-chat)相同的功能，包括您可以存取的技能。 不過，在決定您何時可以使用其中一個變數時，有一些重要的差異：

| | 同事的產品內體驗 | 同事應用程式 |
| --- | --- | --- |
| **何時使用** | 您想要建置您打算保留、與其他使用者共用或隨著時間更新的專案。 | 您想要快速解答。 如有需要，您可以選擇稍後將分析轉換為Workspace專案。 |
| **內容** | 以專案為中心<p>以開啟的Workspace專案為起點。 您可以參照並建置專案中已存在的面板、表格和元件。</p> | 以資料檢視為中心<p>使用您有權存取的資料檢視或您在Co-worker記憶體中設定為偏好設定的資料檢視。 您可以在提示中說明要分析的內容。</p> |
| **一般使用者** | 在Workspace中建置及驗證分析的分析師。 | 需要答案而不需要存取或學習Workspace的商業使用者。 |
| **輸出** | 同事可將面板、表格和元件直接新增至Workspace專案。 <p>在適當的時候，它也會在聊天中回答。</p> | 交談中提供答案和分析，並可選擇在Analysis Workspace中開啟。 |

### 您可以與同事一起做什麼

#### 詢問關於開啟專案的問題

您可以詢問同事的問題，例如：

* 概述專案。
* 尋找資料中的見解和異常標幟。
* 在面板上執行根本原因分析。
* 說明如何在Analysis Workspace中執行一些操作，例如如何新增折線圖或如何根據表格儲存格的值為其著色。
* 說明元件，例如量度或維度。

如需詳細資訊，請參閱[詢問專案相關問題](#ask-questions-about-a-project)。

#### 建置並編輯開啟的專案

您可以要求同事執行下列動作：

* 使用您指定的維度、量度和日期範圍建立自由面板。
* 將面板新增至專案。 同事新增面板，不會覆寫您現有的面板。
* 劃分表格或新增比較欄。
* 變更面板的日期範圍或視覺效果型別，例如將表格變更為折線圖。
* 重新命名面板。
* 依名稱套用現有區段、從純語言說明建立區段，或複製區段並變更其邏輯。
* 建立日期範圍和簡單的計算量度。
* 新增說明或包含專案深入分析的文字視覺效果。
* 建立具有多個面板的專案，或複製專案並因應不同對象或區域進行調整。
* 儲存專案。

如需詳細資訊，請參閱[更新專案](#update-a-project)。

### 當同事更新專案或在聊天中回答時

同事會根據您的要求，決定是在聊天面板中接聽，還是變更專案。 如需詳細資訊，請參閱[更新專案](#update-a-project)和[詢問專案相關問題](#ask-questions-about-a-project)。

您也可以明確說明您希望同事做什麼。 例如，您可以在聊天中使用&#x200B;_之類的片語_&#x200B;或&#x200B;_只要告訴我_&#x200B;在聊天面板中取得答案，或在此資料表&#x200B;_中使用類似_&#x200B;加入專案&#x200B;_或_&#x200B;之類的片語來更新專案。

## 將同事用於您的專案

同事可以看到開啟專案中的每個面板和表格。 您可以要求同事回答有關專案的問題或協助您更新專案。

>[!TIP]
>
>您可以隨時中斷Co-worker或更新專案：
>
>* **引導或停止工作**：當同事正在工作時，按&#x200B;**Shift+Enter**&#x200B;讓工作方向更明確，或按&#x200B;**Esc**&#x200B;停止工作。
>
>* **在Workspace中更新專案**：如果您在同事工作時編輯專案，同事會辨識您的變更。

### 更新專案

當您要求同事在專案中建立或編輯某些內容時，同事會相應地更新專案。 這包括以&#x200B;_新增_、_建立_、_編輯_、_劃分_、_變更_&#x200B;和&#x200B;_比較_&#x200B;等字詞開頭的請求。 例如，您可以要求Co-worker新增面板和表格、劃分資料或建立區段。

1. 在Customer Journey Analytics中，開啟現有的Workspace專案或建立新專案。

1. 選取標題右上角的&#x200B;**同事**&#x200B;圖示![詢問同事](/help/assets/icons/coworker.svg)以開啟同事聊天面板。

1. 在聊天面板中，說明您希望同事做什麼。

   下表列出範例提示。

   | 提示 | 同事的作用 |
   | --- | --- |
   | _依頁面顯示上個月_&#x200B;的工作階段 | 新增新的自由面板，其中包含您指定的維度、量度和日期範圍。 不會覆寫現有面板。 |
   | _依裝置劃分此資料表_ | 將劃分新增至您參考的表格。 |
   | _在此資料表中新增與上個月的比較_ | 新增比較資料欄至您參考的表格。 |
   | _將此面板的日期範圍變更為上個月_ | 更新面板的日期範圍。 |
   | _將此表格變更為折線圖_ | 變更面板的視覺效果型別。 |
   | _將此面板重新命名為行動效能_ | 重新命名面板。 |
   | _將行動使用者區段套用至此面板_ | 將現有區段套用至面板。 同事不知道區段定義，因此請確認區段包含您預期的內容。 |
   | _為來自加拿大的訪客建立區段_ | 建立區段並將其新增至專案。 重新整理頁面後，區段會顯示在元件清單中。 |
   | _複製加拿大訪客區段，並將其變更為來自墨西哥的訪客_ | 使用更新的邏輯建立區段的復本，並將其新增至專案。 |
   | _建立過去6週的日期範圍_ | 建立日期範圍。 日期範圍會出現在元件清單中，而不會重新整理。 |
   | _為每個工作階段建立收入的計算量度_ | 建立計算量度。 同事可以建立簡單的計算量度。 |
   | _新增說明至此面板，說明造訪次數下降_ | 將說明新增至面板。 |
   | _新增包含重要深入分析的文字視覺效果_ | 新增包含專案深入分析的文字視覺效果。 |
   | _建立具有流量、轉換和收入面板的專案_ | 建立專案，專案中包含您說明的每個區域的面板。 |
   | _複製此專案並針對EMEA地區進行調整_ | 建立專案的復本，並依照您指定的區域加以調整。 |
   | _儲存專案_ | 儲存專案。 |
   | _復原您新增的劃分_ | 復原您指定的變更。 |
   | _刪除舊面板_ | 列出計畫刪除的面板，並等待您的確認後再刪除它們。 |

1. 檢閱Co-worker對專案所做的變更。 如需詳細資訊，請參閱[驗證同事結果](#verify-coworker-results)。

### 提出有關專案的問題

當您就專案提出問題時，同事會在聊天面板中回答。 這包括&#x200B;_說明_、_摘要_、_討論_&#x200B;和&#x200B;_告訴我更多_&#x200B;等要求。 根本原因分析和類似技能的結果也會保留在聊天面板中，直到您要求同事將它們新增到專案為止。

1. 在Customer Journey Analytics中，開啟現有的Workspace專案或建立新專案。

1. 選取標題右上角的&#x200B;**同事**&#x200B;圖示![詢問同事](/help/assets/icons/coworker.svg)以開啟同事聊天面板。

1. 在聊天面板中，說明您希望同事做什麼。

   下表列出範例提示。

   | 提示 | 同事的作用 |
   | --- | --- |
   | _摘要此專案_ | 在聊天面板中提供摘要，並提供將它新增至專案做為文字視覺效果。 |
   | _在此專案中尋找深入分析_ | 提供聊天面板中的深入分析，並提供專案新增發現的專案。 |
   | _在此面板中標幟任何異常_ | 說明聊天面板中的異常。 如果您要求同事在視覺化效果中顯示異常，這些異常可能不會顯示。 請參閱[目前的限制](#current-limitations)。 |
   | _對行動造訪次數中的下降進行根本原因分析_ | 在聊天面板中提供分析，並提供將結果新增至專案的功能。 |
   | _我如何根據儲存格的值來設定顏色？_ | 說明聊天面板中的步驟。 |
   | _說明跳出率量度_ | 說明聊天面板中的元件。 說明並非來自[資料字典](/help/components/data-dictionary/data-dictionary-overview.md)。 計畫在未來版本支援資料字典定義。 |

1. 檢閱Co-worker提供的答案。 如需詳細資訊，請參閱[驗證同事結果](#verify-coworker-results)。

## 驗證同事結果

同事協助您檢查其結果的準確性。 檢閱時，請牢記下列事項：

* **同事顯示其工作**：同事用來回答問題的區段、量度和篩選器已新增至專案，以便您進行驗證。

* **澄清問題**：當要求模糊或符合多個元件時，同事會詢問澄清問題或建議可選擇的選項。 例如，如果有多個量度符合您使用的名稱，Co-worker會建議符合的量度。

* **資料品質備註**：同事在答案中包含資料品質備註。 例如，如果您比較剛開始的月份和剛開始的月份，Co-worker會告訴您比較是根據部分資料。

## 目前限制

Co-worker的產品內體驗有下列限制：

* **區段定義**：當您依名稱參考區段時，同事不知道區段的定義。 同事可以根據區段的名稱來推斷該區段包含的內容。 在依賴結果之前，請驗證區段定義。

* **資料字典**：同事未連線至[資料字典](/help/components/data-dictionary/data-dictionary-overview.md)。 它無法使用資料字典中的定義來說明量度和維度。

* **已核准的元件**：同事未給予已核准元件優先順序超過類似元件。

* **正在複製面板**：同事無法複製面板。

* **元件清單中的新區段**：在您重新整理頁面之前，Co-worker建立的區段不會出現在左側邊欄的元件清單中。 Co-worker建立的日期範圍會在未重新整理的情況下顯示。

* **異常偵測**：當您要求同事在視覺化效果上顯示異常時，可能不會顯示異常。

* **交談記錄**：已儲存每個使用者的交談，而非專案的交談。 其他開啟專案的使用者看不到您與同事的交談。 若要與其他使用者共用前後關聯，請將其新增至專案中面板的說明。

* **多個瀏覽器分頁**：如果您在多個瀏覽器分頁中開啟同一個交談，同事可能會失去對其工作內容的追蹤。

* **非英文語言**：在使用非英文語言的資料檢視中，同事可能會在其回應中使用英文和資料檢視語言的組合。


