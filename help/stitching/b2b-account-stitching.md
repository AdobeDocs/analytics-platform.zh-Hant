---
title: B2B帳戶拼接
description: 瞭解Customer Journey Analytics中的B2B帳戶拼接如何運用帳戶資訊豐富事件資料集，並啟用您B2B資料的完整歷程分析。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
role: Admin
autotag-review: '2026-05-19T11:01:07.331Z'
TQID: 'https://experienceleague.adobe.com/-7rHOhYVCp-nSMqdE7YlAlCJ0zRQYvPOViMHSCNuKV8'
product_v2:
  - id: d3f42e9e-bb51-4077-a732-358b801d8b29
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: faea9abd-7024-4c5e-a5b4-87919e09b24b
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 0552cfeb3d7ee834ba7928a40dc151b782dc9330
workflow-type: tm+mt
source-wordcount: 1926
ht-degree: 23%

---

# B2B帳戶拼接

B2B帳戶拼接讓您的事件資料集與帳戶身分更加豐富，並且可以在Customer Journey Analytics的完整客戶歷程中進行完整分析。 當事件缺少帳戶ID （Customer Journey Analytics B2B edition需要帳戶識別碼才能進行內嵌）時，帳戶拼接會使用您提供的[人員對帳戶對應資料集](#prerequisites)自動衍生並新增該資訊。

若沒有帳戶拼接，擷取期間會捨棄任何不含帳戶ID的事件。 帳戶拼接可透過查詢與每個事件中的個人相關聯的帳戶來解決此限制，在事件被擷取及回溯時新增帳戶ID。

>[!NOTE]
>
>B2B帳戶拼接需要您有權在您的環境中使用[Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md)，然後才能設定功能。

帳戶拼接會對資料集執行以下操作：

* **提升人員身分**：每個事件上的人員ID都會使用身分圖表提升至已設定的身分名稱空間。
* **新增遺失的帳戶身分識別**：對於包含人員ID的事件，[人員對帳戶對應](#prerequisites)是用來衍生及新增帳戶身分識別。 事件本身的任何帳戶身分都會當作遞補方法使用。

## B2B帳戶銜接的運作方式

為了說明B2B帳戶拚接的運作方式，下方顯示的資料集會作為起點。

### 基本事件資料集

在Customer Journey Analytics B2B edition中，會忽略此非拼接範例事件資料集中沒有帳戶ID的事件，且不會擷取(![DeleteOutline](/help/assets/icons/DeleteOutline.svg))。

| 動作 | 時間戳記 | 永久 ID | 帳戶 ID | 人員 ID | 事件型別 |
|:---:|--:|--|---|---|---|
| ![資料新增](/help/assets/icons/DataAdd.svg) | 1/3/25 | 1234 | Adobe | matt@adobe.com | Page view |
| ![篩選刪除](/help/assets/icons/DeleteOutline.svg) | 1/3/25 | 5678 |  | | |
| ![資料新增](/help/assets/icons/DataAdd.svg) | 3/4/25 | 9012 | 普遍性 | cory@sky.com |  |
| ![資料新增](/help/assets/icons/DataAdd.svg) | 3/7/25 | 4321 | 天空 | emily@sky.com | 呼叫中心 |
| ![篩選刪除](/help/assets/icons/DeleteOutline.svg) | 5/5/25 | 6106 | | carmen@adobe.com |  |
| ![資料新增](/help/assets/icons/DataAdd.svg) | 6/1/25 | 8989 | 普遍性 | cassidy@ubiquity.com | |
| ![篩選刪除](/help/assets/icons/DeleteOutline.svg) | 6/2/25 | 1111 |  | | |

B2B帳戶拚接會使用以下作業來防止事件被忽略或擷取：

* [提升人員身分](#elevate-person-identities)。
* [新增遺失的帳戶身分](#add-missing-account-identitiers)。


### 提升人員身分

+++ 詳細資料

為了支援B2B帳戶拼接，您提供個人對帳戶對應資料集。 例如：

| CRM ID | 帳戶 ID |
|---|---|
| 12hsd123 | Adobe |
| f82jsd32 | 天空 |
| hg2023m2 | 天空 |
| b978bbw9 | 普遍性 |
| fs453ghi | Adobe |

該個人對帳戶對應資料集是使用圖表式拚接的提升許可權。 例如，您提供電子郵件作為要使用的名稱空間。 結果，會以提升的人員ID產生更新的人員 — 帳戶對應資料集。

| CRM ID | 提升的人員ID | 帳戶 ID |
|---|---|---|
| 12hsd123 | matt@adobe.com | Adobe |
| f82jsd32 | emily@sky.com | 天空 |
| hg2023m2 | cory@sky.com | 天空 |
| b978bbw9 | cassidy@ubiquity.com | 普遍性 |
| fs453ghi | carmen@adobe.com | Adobe |

圖表式拚接也可用來提升體驗事件資料集中的人員ID。 例如，檢視&#x200B;**emily@adobe.com**&#x200B;的更新值。

| 時間戳記 | 永久 ID | 原始帳戶ID | 原始人員ID | 提升的人員ID |
|--|--|---|---|---|
| 1/3/25 | 1234 | Adobe | matt@adobe.com | matt@adobe.com |
| 1/3/25 | 5678 |  | | **emily@adobe.com** |
| 3/4/25 | 9012 | 普遍性 | cory@sky.com | cory@sky.com |
| 3/7/25 | 4321 | 天空 | emily@sky.com | emily@sky.com |
| 5/5/25 | 6106 | | carmen@adobe.com | carmen@adobe.com |
| 6/1/25 | 8989 | 普遍性 | cassidy@ubiquity.com | cassidy@ubiquity.com |
| 6/2/25 | 1111 |  | 111 | 111 |


+++

### 新增缺少的帳戶識別碼

+++ 詳細資料

此個人對帳戶資料集可再次用於提升體驗事件資料集中的帳戶ID。 例如，請參閱emily@sky.com的增加值&#x200B;**Sky**&#x200B;和carmen@adobe.com的&#x200B;**Adobe**。 以及cory@sky.com的更新值&#x200B;**Sky** （來自Ubiquity）。

| 時間戳記 | 永久 ID | 原始帳戶ID | 原始人員ID | 提升的帳戶ID | 提升的人員ID |
|---|---|---|---|---|---|
| 1/3/25 | 1234 | Adobe | matt@adobe.com | Adobe | matt@adobe.com |
| 1/3/25 | 5678 | | | **天空** | **emily@sky.com** |
| 3/4/25 | 9012 | 普遍性 | cory@sky.com | **天空** | cory@sky.com |
| 3/7/25 | 4321 | 天空 | emily@sky.com | 天空 | emily@sky.com |
| 5/5/25 | 6106 | | carmen@adobe.com | **Adobe** | carmen@adobe.com |
| 6/1/25 | 8989 | 普遍性 | cassidy@ubiquity.com | 普遍性 | cassidy@ubiquity.com |
| 6/2/25 | 1111 |  | 1111 |  | 1111 |

+++

### 結果

此範例顯示B2B帳戶拼接如何根據您提供作為輸入的人員 — 帳戶對應資料集，使用缺少的人員識別碼以及缺少和不正確的帳戶識別碼來更新體驗事件資料。


## 先決條件

啟用B2B帳戶拼接之前，請先在Adobe Experience Platform中準備以下資料集：

| 資料集 | 必要 | 說明 |
|---|---|---|
| **個人對帳戶資料集** | 必填 | 至少包含人員ID （含名稱空間）和帳戶ID的查詢（記錄，非時間序列）資料集。 這些ID用於衍生個人與帳戶的關係對應。 |

>[!IMPORTANT]
>
>**[!UICONTROL 個人對帳戶]**&#x200B;資料集中的人員ID欄位必須在結構描述中標示為身分。

## 啟用帳戶拼接 {#enable-account-stitching}

您首先需要在連線層級啟用和設定B2B帳戶拼接。 當連線設定B2B帳戶拼接時，您可以接著對該連線中的個別事件資料集啟用帳戶拼接。

### 設定 B2B 拼接設定 {#configure-b2b-stitching-settings}

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_open_configuration"
>title="設定 B2B 帳戶拼接"
>abstract="選取「**[!UICONTROL 開啟 B2B 拼接設定]**」以設定 B2B 帳戶拼接。 如果連線尚未儲存，該設定會標示為「**[!UICONTROL _未儲存的變更_]**」。"

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person_identifier_namespace"
>title="人員識別碼命名空間"
>abstract="選取與您的報告最相關的人員身分識別命名空間。 例如：電子郵件。 任何已啟用&#x200B;**[!UICONTROL 個人對帳戶拼接]**&#x200B;的事件資料集，都會將永久性個人ID提升至此個人識別碼名稱空間。"

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person_to_account_dataset"
>title="人員至帳戶資料集"
>abstract="選取將人員 ID 對應至帳戶 ID 的查詢資料集。"

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person"
>title="人員 ID"
>abstract="選取資料集中包含人員 ID 的欄位。 此欄位的命名空間可以與所選人員識別碼命名空間不同或相同。 如果兩者不同，則需要在身分識別圖中連結這兩個命名空間。"

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_account"
>title="帳戶 ID"
>abstract="選取資料集中包含唯一帳戶識別碼值的欄位。 啟用&#x200B;**[!UICONTROL 人員至帳戶拼接]**&#x200B;後，帳戶 ID 資訊在任何事件資料集的列上都會變為可用。"

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_start_time"
>title="開始時間"
>abstract="選取時間戳記欄位，其指出人員至帳戶關係何時變為有效。"


>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_mapping_creation_time"
>title="對應建立時間"
>abstract="選取代表人員與帳戶對應建立日期與時間的欄位 (可選)。 適用於人員隨時間切換多個帳戶的情況。"


1. 在Customer Journey Analytics中，導覽至&#x200B;**[!UICONTROL 連線]**&#x200B;並[建立新連線](/help/connections/create-connection.md#create-a-connection)或[編輯現有連線](/help/connections/create-connection.md#edit-a-connection)。

1. 在&#x200B;**[!UICONTROL 連線設定]**&#x200B;中，將&#x200B;**[!UICONTROL 主要識別碼]**&#x200B;設定為![正在建置](/help/assets/icons/Building.svg) **[!UICONTROL 帳戶]**。

1. 請確定您選取要在B2B連線中使用的&#x200B;**[!UICONTROL 選用容器]**。 儲存B2B拼接設定後，您就無法修改這些容器的選取範圍。

1. 選取&#x200B;**[!UICONTROL 開啟B2B拼接組態]**。

   ![B2B帳戶標題設定](assets/b2b-account-stitching-configuration.png)

   >[!NOTE]
   >
   >先前針對未儲存的連線所設定的B2B拼接組態會以&#x200B;**[!UICONTROL _未儲存的變更_]**&#x200B;表示。 您無法修改先前設定的B2B拼接組態的&#x200B;**[!UICONTROL 選用容器]**。

1. 在&#x200B;**[!UICONTROL B2B拼接組態]**&#x200B;對話方塊中：

   ![B2B拼接組態](assets/b2b-stitching-configuration.png)

   1. 設定&#x200B;**[!UICONTROL 人員]**&#x200B;區段：

      * 選取&#x200B;**[!UICONTROL 人員識別碼名稱空間]**，例如&#x200B;**[!UICONTROL 電子郵件]**，您希望將任何人員ID提升至該名稱空間。 此欄位為必填項。

   1. 設定&#x200B;**[!UICONTROL Person to Account]**&#x200B;底下的&#x200B;**[!UICONTROL 帳戶]**&#x200B;區段。

      | 欄位 | 必要 | 說明 |
      |---|:---:|---|
      | **[!UICONTROL 帳戶資料集的人員]** | ![必要](/help/assets/icons/Required.svg) | 選取將人員對應至帳戶的查詢（記錄或非時間序列資料集）。 |
      | **[!UICONTROL 個人 ID]** | ![必要](/help/assets/icons/Required.svg) | 選取資料集中包含人員 ID 的欄位。 該欄位必須標示為身分，且不能與&#x200B;**[!UICONTROL 帳戶識別碼]**&#x200B;欄位或&#x200B;**[!UICONTROL 開始時間]**&#x200B;欄位相同。 |
      | **[!UICONTROL 帳戶 ID]** | ![必要](/help/assets/icons/Required.svg) | 選取資料集中包含帳戶 ID 的欄位。 該欄位不能與&#x200B;**[!UICONTROL 人員ID]**&#x200B;欄位或&#x200B;**[!UICONTROL 開始時間]**&#x200B;欄位相同。 |
      | **對應建立時間** | | 選取代表人員與帳戶對應建立日期與時間的欄位 (可選)。 適用於人員隨時間切換多個帳戶的情況。<br/><br/>**範例** （選取&#x200B;**update_date**&#x200B;欄位時）：<table><thead><tr><th>update_date</th><th>人員</th><th>account</th></tr></thead><tbody><tr><td>20260401</td><td>a@b.com</td><td>Apple</td></tr><tr><td>20260501</td><td>a@b.com</td><td>Adobe</td></tr></tbody></table><ul><li>對於2026年5月1日之前在&#x200B;**[!UICONTROL update_date]**&#x200B;欄位中具有時間戳記的所有事件： a@b.com已對應至Apple。</li><li>對於2026年5月1日或之後在&#x200B;**[!UICONTROL update_date]**&#x200B;欄位中具有時間戳記的所有事件： a@b.com已對應至Adobe。</li></ul>未指定對應時間時，會使用字典第一帳戶。 當兩個不同的帳戶名稱具有完全相同的&#x200B;**[!UICONTROL update_date]**&#x200B;值，並且指定了對應建立時間時，也會使用相同的演演算法。 |

      >[!NOTE]
      >
      >如果在載入欄位選項時發生錯誤，下拉選單將顯示為空白，並且每個受影響的欄位下方都會顯示錯誤指示器。 請驗證您的資料集結構，然後再試一次。

   1. 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以關閉&#x200B;**[!UICONTROL B2B拼接組態]**&#x200B;對話方塊並返回連線設定。

   1. **[!UICONTROL _未儲存的變更_]**&#x200B;指標會出現在&#x200B;**開啟B2B拼接設定**&#x200B;按鈕旁，直到您[儲存](#save)連線為止。

### 在事件資料集上啟用 B2B 拼接


>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_enable_person_to_account"
>title="啟用人員至帳戶拼接"
>abstract="如果啟用，此資料集便會使用 B2B 人員至帳戶拼接。 **[!UICONTROL 持續性人員ID]**&#x200B;值會提升為來自已設定的&#x200B;**[!UICONTROL 人員識別碼名稱空間]**&#x200B;的值，然後用來根據人員對帳戶資料集查詢帳戶ID。<br/>如果停用，此資料集便不會使用 B2B 人員至帳戶拼接，而您必須改為選取所需的&#x200B;**[!UICONTROL 帳戶 ID]**。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/stitching/b2b-account-stitching#configure-b2b-stitching-settings" text="設定 B2B 拼接設定"

在連線層級設定B2B拼接後，您必須針對要拼接的每個事件資料集個別啟用B2B帳戶拼接。

1. 在「連線設定」中，選取&#x200B;**[!UICONTROL 新增資料集]**&#x200B;或開啟現有事件資料集的設定。<br/>如需詳細資訊，請參閱[新增資料集](/help/connections/create-connection.md#add-datasets)或[編輯資料集](/help/connections/create-connection.md#edit-a-dataset)。

1. 針對您要設定B2B帳戶拼接的特定事件資料集，請切換&#x200B;**[!UICONTROL 啟用人員到帳戶的拼接]**。

>[!BEGINTABS]

>[!TAB 於]

當&#x200B;**[!UICONTROL 啟用人員帳戶拼接]**&#x200B;為&#x200B;**on**&#x200B;時，您已為資料集設定B2B帳戶拼接。

* 人員ID的設定為必填。 該人員ID是用來根據[人員對帳戶資料集](#prerequisites)查詢帳戶ID。
* 帳戶ID的設定為選用。

在![&#128279;](assets/b2b-event-dataset-stitching-on.png)的事件資料集上彙整B2B帳戶

>[!TAB 關閉]

當&#x200B;**[!UICONTROL 啟用人員帳戶拼接]**&#x200B;為&#x200B;**關閉**&#x200B;時，您有&#x200B;*未*&#x200B;為資料集設定了B2B帳戶拼接。

* 需要設定帳戶ID。
* 人員ID的設定為選用。

![B2B帳戶正在拼接事件資料集](assets/b2b-event-dataset-stitching-off.png)


>[!ENDTABS]




### 儲存

在您設定B2B拼接設定並完成新增或編輯資料集後，選取「**[!UICONTROL 儲存]**」以儲存連線。

>[!IMPORTANT]
>
>在儲存連線後，B2B拼接設定將變得不可變動。 若要在儲存後檢視您的設定，請選取&#x200B;**開啟B2B拼接組態**。 所有欄位都會以唯讀狀態顯示。 此外，如果在Experience Platform中刪除用於[個人對帳戶對應](#prerequisites)的資料集，則會刪除此連線。

## 資料更新排程

帳戶拼接每天從您的[個人對帳戶資料集](#prerequisites)衍生出身分對應，並依照下列排程使用此資訊來更新已啟用短期和長期拼接的資料集：

| 重播 | 頻率 | 資料視窗 |
|---|---|---|
| 短期 | 每週 | 最近 7 天 |
| 長期 | 按月 | 過去3個月（Prime套件）<br/>過去6個月（Ultimate套件） |

## 隱私權與資料衛生

帳戶拼接遵循個人身份的標準隱私和衛生請求，與B2C拼接行為一致。 如果之後透過隱私權或衛生請求移除人員ID，則使用身分圖表執行的相關銜接作業會反轉。

在隱私權或衛生請求期間，不會移除透過拼接新增到事件的B2B實體，例如帳戶ID、帳戶ID和全域帳戶ID。 這些值不包含個人識別資訊，因此不存在移除這些值的法律義務。

>[!MORELIKETHIS]
>
>* [拼接概述](overview.md)
>* [設定B2B的連線](../connections/create-connection.md)
>* [有關銜接的常見問題](faq.md)

