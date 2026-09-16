---
title: 從AppMeasurement或標籤移轉至XDM
description: 瞭解如何從AppMeasurement或標籤移轉至XDM
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
source-git-commit: 39d6847296cc385d501defda292b5b3cae98b46a
workflow-type: tm+mt
source-wordcount: '2338'
ht-degree: 16%
---
# 從標記移轉至 XDM {#upgrade-migration-planner}

{{upgrade-note-step}}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_intro"
>title="移轉概觀"
>abstract="升級至 Customer Journey Analytics 時，將標記實施移轉至 Adobe Experience Platform Web SDK。<br/>繼續現有的移轉，或開始新的移轉。"

<!-- markdownlint-enable MD034 -->

移轉規劃工具提供移轉精靈，可自動將標籤移轉至XDM，包括建立結構。 這些是從Adobe Analytics升級至Customer Journey Analytics相關的最複雜和最耗時的工作。

## 支援的Adobe Analytics實作

移轉規劃工具支援使用Analytics擴充功能（標籤）的Adobe Analytics實施。

移轉規劃工具不適用於使用AppMeasurement或Experience Platform Web SDK的Adobe Analytics實施。

## 升級移轉規劃工具中包含的任務

移轉規劃工具提供移轉精靈，可自動化下列複雜且耗時的升級工作：

* **XDM結構描述建立**：根據您的Adobe Analytics報表套裝變數，自動建立新的XDM結構描述。 移轉規劃工具會聰明地掃描您的Adobe Analytics報表套裝變數，然後使用該資訊在XDM中建立必要的欄位。 產生的XDM結構描述僅包含Customer Journey Analytics結構描述中所需的欄位。

  或者，您可以指向現有的XDM結構描述，或從頭開始建立XDM結構描述。

  +++ 如果您選擇從頭開始建立XDM結構描述，您可以展開本區段以取得有用資源的相關資訊。

  * [規劃您的 XDM 結構描述架構](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md){target="_blank"}。

  * [在 Adobe Experience Platform 中建立您所要的自訂結構描述](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}。

    建立結構描述時，請考慮以下選項：

    * 如果要將 Customer Journey Analytics 與 RTCDP 整合，您必須在結構描述啟用&#x200B;**[!UICONTROL 設定檔]**&#x200B;選項，如「[建立 XDM 結構描述以搭配 Customer Journey Analytics 使用](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}」中所述。 啟用此選項後，根據此結構描述將資料攝取至資料集時，該資料就會合併至即時客戶輪廓中。

    * 如果你想包含串流媒體資料，你必須[設定結構描述以攝取和使用串流資料](/help/data-ingestion/streaming.md){target="_blank"}。

    +++

  * **將您的Adobe Analytics實作移轉至網頁SDK**：無論您的Adobe Analytics實作是使用標籤還是JavaScript，移轉規劃工具都會引導您完成移轉至Experience Platform網頁SDK的流程。

    * **將標籤屬性從AppMeasurement移轉至Web SDK**：

    * **將JavaScript實作從AppMeasurement移轉至Web SDK JavaScript資料庫**

  * **在Customer Journey Analytics中建立資料檢視**：根據建立的XDM結構描述欄位，自動建立資料檢視並填入元件。


## 開始之前

在建立移轉之前，請確定您具備下列條件：

* 支援的Adobe Analytics實作（標籤的Analytics擴充功能）。 請參閱[支援的Adobe Analytics實作](#supported-adobe-analytics-implementations)。

* 在您登入的Adobe組織中，存取您要移轉的Experience Cloud Tags屬性。

* 存取您要將其變數對應至XDM的Adobe Analytics報表套裝。

* 在Adobe Experience Platform中建立結構描述的許可權。

<!-- Confirm the exact roles and permissions required to use the Migration Planner and to create schemas and Data Views. -->

## 將Analytics實作移轉至Web SDK

移轉會經過三個階段： [!UICONTROL **稽核**]、[!UICONTROL **對應**]&#x200B;以及&#x200B;[!UICONTROL **實作**]。 使用下列步驟建立移轉，然後繼續進行[驗證並部署移轉](#validate-and-deploy-a-migration)以完成每個階段。

1. 在Customer Journey Analytics中，開啟&#x200B;[!UICONTROL **移轉規劃工具**]。

   <!-- Confirm the exact navigation path to open the Migration Planner in Customer Journey Analytics. -->

1. 在移轉規劃工具的&#x200B;[!UICONTROL **移轉**]&#x200B;標籤上，選取&#x200B;[!UICONTROL **新增**]。

   <!-- Confirm the exact image: ![The migration overview page with the Audit, Mapping, and Implementation stage cards.](assets/migration-planner-overview.png) -->


1. 註明下列資訊：

   | 欄位名稱 | 函數 |
   | --------- | ---------- |
   | [!UICONTROL **名稱**] | 指定此移轉的名稱。 |
   | [!UICONTROL **說明**] | 指定此移轉的選擇性說明。 |
   | [!UICONTROL **標籤屬性**] | 選取您要移轉的Adobe Tags屬性。 如需詳細資訊，請參閱Experience Platform檔案中的[屬性](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/admin/companies-and-properties){target="_blank"}。 |
   | [!UICONTROL **標籤庫**] | 選取移轉所根據的標籤程式庫快照。 快照會決定要使用標籤程式庫的版本。 如需詳細資訊，請參閱Experience Platform檔案中的[發佈概觀](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/publish/overview){target="_blank"}。 |

1. 在&#x200B;[!UICONTROL **移轉名稱**]&#x200B;欄位中，指定此移轉的名稱，然後選取&#x200B;[!UICONTROL **下一步**]。

1. 選取您要移轉的標籤屬性，然後選取&#x200B;[!UICONTROL **下一步**]。

   只會顯示您登入的Experience Cloud組織可用的標籤屬性。

1. 選取您要移轉的標籤程式庫快照，然後選取&#x200B;[!UICONTROL **下一步**]。

   快照會決定移轉所根據的標籤程式庫版本。 每個快照都會顯示其環境（例如&#x200B;[!UICONTROL **開發**]、[!UICONTROL **暫存**]&#x200B;或&#x200B;[!UICONTROL **生產**]）。

1. 選取對應集以決定Analytics變數將如何對應至XDM結構描述欄位。

   進行下列一項：

   * 選取&#x200B;[!UICONTROL **建立新的對應集**]。

   * 選取現有的對應集。

     在先前移轉期間建立或作為獨立對應集建立的對應集可供選取。

     在多個移轉中重複使用對應集，會將相同的對應套用至每個移轉。

1. 選取&#x200B;[!UICONTROL **建立移轉**]。

1. 繼續下列章節，[驗證並部署移轉](#validate-and-deploy-a-migration)。

## 驗證和部署移轉

建立移轉後，請開啟它以完成其三個階段： [!UICONTROL **稽核**]、[!UICONTROL **對應**]&#x200B;以及&#x200B;[!UICONTROL **實作**]。

1. 在移轉規劃工具中，選取&#x200B;[!UICONTROL **移轉**]&#x200B;標籤。

1. 在您要驗證的移轉旁邊，選取&#x200B;[!UICONTROL **開啟**]。

   移轉概觀頁面會顯示要完成的三個階段，以及移轉及其成品的摘要。

   <!-- Confirm the exact image: ![The migration overview page with the Audit, Mapping, and Implementation stage cards.](assets/migration-planner-overview.png) -->

1. 完成&#x200B;[!UICONTROL **稽核**]&#x200B;階段：

   1. 在稽核卡（[!UICONTROL **標籤延伸稽核**]&#x200B;或&#x200B;[!UICONTROL **JavaScript稽核**]，視您的移轉型別而定）中，選取&#x200B;[!UICONTROL **開始稽核**]&#x200B;以檢閱移轉中包含的規則和資料元素。

      <!-- Confirm the exact image: ![The audit page, where you select rules and data elements and resolve any findings.](assets/migration-planner-audit.png) -->

   1. 在&#x200B;[!UICONTROL **規則**]&#x200B;和&#x200B;[!UICONTROL **資料元素**]&#x200B;標籤上，選取要包含在移轉中的專案。

      資料庫&#x200B;**]中標示為[!UICONTROL **&#x200B;的規則已發佈。 標示為&#x200B;[!UICONTROL **屬性**]&#x200B;的規則僅存在於屬性中，但不是所選程式庫的一部分。

   1. 檢閱所選規則的任何發現專案。 針對每個發現，選取&#x200B;[!UICONTROL **檢閱**]&#x200B;以將其解析，或選取&#x200B;[!UICONTROL **忽略**]&#x200B;以保留其未定址。

      例如，當兩個規則具有相同的事件和條件時，[!UICONTROL **重複規則事件**]&#x200B;發現專案可讓您保留一個規則並移除另一個規則，或選取&#x200B;[!UICONTROL **不做任何動作**]&#x200B;認可該發現專案而不做變更。

      繼續之前，請先選擇解決發現。 如需發現專案型別的完整清單，以及如何解析每個型別，請參閱[檢閱並解析稽核發現專案](#review-and-resolve-audit-findings)。

   1. 選取&#x200B;[!UICONTROL **「儲存並繼續」**]。

1. 完成&#x200B;[!UICONTROL **對應**]&#x200B;階段：

   1. 在&#x200B;[!UICONTROL **Analytics → XDM對應**]&#x200B;卡片中，選取&#x200B;[!UICONTROL **建立新對應**]。

   1. 選擇是根據您的Analytics變數建立新結構描述，還是對應至現有的Experience Platform結構描述，然後依照提示選取您的報表套裝、對應欄位並檢閱結構描述。

      如需詳細步驟，請參閱[將Analytics變數對應至XDM欄位](#map-analytics-variables-to-xdm-fields)。 若要跨移轉重複使用對應集，請參閱[建立和管理對應集](#create-and-manage-mapping-sets)。

1. 完成&#x200B;[!UICONTROL **實作**]&#x200B;階段：

   1. 在&#x200B;[!UICONTROL **產生Web SDK實作**]&#x200B;卡片中，使用稽核與對應結果來產生Web SDK實作套件，然後將其部署至您的網站。

      如需詳細步驟，請參閱[產生並部署Web SDK實作](#generate-and-deploy-the-web-sdk-implementation)。


## 複查並解決稽核發現

在&#x200B;[!UICONTROL **稽核**]&#x200B;階段期間，移轉規劃工具會在您選取的規則上標示發現。 在繼續之前解決發現是選用的，但解決發現有助於確保乾淨的移轉。

針對每個發現，選取&#x200B;[!UICONTROL **檢閱**]&#x200B;以開啟發現並選取如何解析，或選取&#x200B;[!UICONTROL **忽略**]&#x200B;以保留未定址。

「移轉規劃工具」可標示下列搜尋結果型別：

* [!UICONTROL **重複的規則事件**]：兩個或多個規則具有相同的事件和條件。 檢閱發現專案時，請比較主要和重複規則，然後保留一個規則並移除另一個規則，或選取&#x200B;[!UICONTROL **不做任何動作**]&#x200B;認可發現專案而不做變更。

* [!UICONTROL **重複的規則邏輯**]：規則共用相同的邏輯。<!-- Confirm the exact remediation options for this finding type. -->

* [!UICONTROL **規則動作順序錯誤**]：規則的動作執行順序可能會造成移轉期間發生問題。<!-- Confirm the exact remediation options for this finding type. -->

如果發現專案沒有引導式修正，移轉規劃工具會顯示&#x200B;[!UICONTROL **沒有可用的修正詳細資料**]。 手動檢閱發現，並在解決後將其關閉。

[!UICONTROL **發現**]&#x200B;面板會顯示您已處理的發現專案數，以及仍開啟的發現專案數。 完成時，選取[儲存]並繼續&#x200B;**]。[!UICONTROL **

## 將Analytics變數對應至XDM欄位

在&#x200B;[!UICONTROL **對應**]&#x200B;階段期間，您會將您的Analytics變數對應到XDM欄位，並產生或選取目標結構描述。 在&#x200B;[!UICONTROL **Analytics → XDM對應**]&#x200B;卡片中，選取&#x200B;[!UICONTROL **建立新對應**]，然後完成下列步驟：

1. **結構描述選擇**：選擇是否要根據您的Analytics變數建立新的結構描述，或對映現有的Experience Platform結構描述。

1. **報表套裝**：選取您要對應其變數的Analytics報表套裝。

1. **Experience Platform結構描述**：建立目標XDM結構描述，或選取要對應的現有結構描述。

1. **手動對應**：檢閱自動對應，並調整個別Analytics變數對應至XDM欄位的方式。

1. **檢閱結構描述**：檢閱產生的對應和結構描述，然後確認。

<!-- The XDM mapping editor was not captured in the walkthrough. Confirm the exact steps, controls, and options on each step (Schema choice, Report suite, Experience Platform schema, Manual mapping, Review schema). -->

若要跨移轉重複使用對應集，請參閱[建立和管理對應集](#create-and-manage-mapping-sets)。

## 比較移轉輸出

在移轉總覽頁面上使用&#x200B;[!UICONTROL **比較輸出**]&#x200B;來驗證您的移轉，然後再進行部署。

<!-- The Compare outputs screen was not captured in the walkthrough. Confirm what the comparison shows (for example, AppMeasurement output compared with the Web SDK / XDM output) and how to interpret the results. -->

## 產生並部署網頁SDK實作

在&#x200B;[!UICONTROL **實作**]&#x200B;階段中，移轉規劃工具會使用您的稽核與對應結果來建置網頁SDK實作封裝。

1. 在移轉總覽頁面的&#x200B;[!UICONTROL **產生Web SDK實作**]&#x200B;卡片中，產生實作套件。

1. 選取&#x200B;[!UICONTROL **建立標籤程式庫**]，以建立移轉的標籤程式庫。

1. 設定雙重部署，然後將Web SDK實作部署至您的網站。

<!-- This stage was not captured in the walkthrough. Confirm the exact steps for generating the package, configuring the dual deployment, building the tag library, and deploying to the site. -->

如需此階段產生的成品，請參閱[匯出移轉成品](#export-migration-artifacts)。

## 匯出移轉人工因素

移轉總覽頁面會提供移轉規劃工具產生的人工因素。 您可以從&#x200B;[!UICONTROL **專案成品**]&#x200B;面板下載個別成品，或選取&#x200B;[!UICONTROL **全部匯出**]&#x200B;一次匯出所有成品。

下列成品可供使用：

* [!UICONTROL **對應JSON**]：您的Analytics變數與XDM欄位之間的對應。

* [!UICONTROL **XDM結構描述(JSON)**]：為移轉建立的目標XDM結構描述。

* [!UICONTROL **標籤開發程式庫**]：為Web SDK實作建立的標籤程式庫。

每個成品都會顯示其狀態，例如&#x200B;[!UICONTROL **就緒**]&#x200B;或&#x200B;[!UICONTROL **未建置**]。 成品在對應階段產生後，即可供下載。

## 建立及管理對應集 {#mapping-sets}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_sets"
>title="對應集"
>abstract="對應集會決定 Analytics 變數對應至 XDM 欄位的方式。<br/>建立新的對應集，或選擇現有的對應集，將相同的對應套用至多個移轉。 您也可以在其他移轉工作中參照對應集。"

<!-- markdownlint-enable MD034 -->

對應集可決定Analytics變數對應至XDM結構描述欄位的方式。

您可以在移轉程式](#migrate-an-analytics-implementation-to-the-web-sdk)期間建立新的對應集[。 或者，您可以建立獨立對應集，以便用於未來的移轉或其他移轉工作。

### 建立獨立的對應集 {#xdm-mapping}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_schema"
>title="選擇結構描述"
>abstract="對應集會決定 Analytics 變數對應至 XDM 欄位的方式。<br/>建立新的對應集，或選擇現有的對應集，將相同的對應套用至多個移轉。 您也可以在其他移轉工作中參照對應集。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_field_group"
>title="欄位群組偏好"
>abstract="盡可能選擇標準欄位群組，以便使用 Adobe 已發佈的欄位群組。 這樣能夠促進最高程度的一致性，並在沒有標準欄位可用時退回自訂租用戶欄位。<br/>盡可能選擇自訂欄位群組，以使用租用戶命名空間自訂欄位。 這樣能夠促進最高程度的彈性。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_lookback"
>title="回顧期間"
>abstract="在判斷哪些變數正在主動接收資料時，可用來控制所要回溯的時間長度。 包含回顧期間內資料的變數會納入在結構描述中。"

<!-- markdownlint-enable MD034 -->

1. 在移轉規劃工具中，選取&#x200B;[!UICONTROL **對應集**]&#x200B;標籤。

1. 選取&#x200B;[!UICONTROL **新對應集**]。

1. 在&#x200B;[!UICONTROL **Name**]&#x200B;欄位中輸入描述性名稱，以便稍後識別此對應集，然後選取&#x200B;[!UICONTROL **下一步**]。

1. 從&#x200B;[!UICONTROL **報表套裝**]&#x200B;功能表中，選取您要將其變數對應至XDM欄位的報表套裝，然後選取&#x200B;[!UICONTROL **下一步**]。

1. 在&#x200B;[!UICONTROL **為您的XDM對應區段選擇結構描述**]&#x200B;中，選擇是根據您的Analytics變數建立新的結構描述，還是對應現有的Experience Platform結構描述。

   選擇建立新結構描述會引導您完成將Analytics變數對應到XDM欄位的程式。 選擇使用現有結構描述可讓您手動將變數對應到Experience Platform結構描述登入中預先註冊的結構描述。

   <!-- Screenshot pending: the XDM mapping editor (Create new mapping) was not available for capture in the walkthrough. -->

   * [!UICONTROL **建立新的結構描述**]：執行基本和進階掃描以自動為您的Analytics變數建議XDM欄位對應，然後檢閱產生的結構描述。

   * [!UICONTROL **使用現有的結構描述**]：搜尋並選取已在Experience Platform結構描述登入中註冊的結構描述，然後手動將Analytics變數拖曳至XDM欄位。

1. 在&#x200B;[!UICONTROL **欄位群組偏好設定**]&#x200B;下拉式功能表中，選擇您要如何將自訂變陣列織到欄位群組中：

   * [!UICONTROL **標準優先**]：儘可能使用已發佈的Adobe欄位群組。 這樣能夠促進最高程度的一致性，並在沒有標準欄位可用時退回自訂租用戶欄位。

   * [!UICONTROL **自訂優先**]：儘可能使用租使用者 — 名稱空間自訂欄位。 這樣能夠促進最高程度的彈性。

   <!-- * [!UICONTROL **Ask each time**]: Prompt for each signal so you can decide individually. -->

1. 在&#x200B;[!UICONTROL **回顧期間**]&#x200B;欄位中，選取在判斷哪些變數正在主動接收資料時，要回顧多久的時間。 包含回顧期間內資料的變數會納入在結構描述中。

1. 選取&#x200B;[!UICONTROL **建立對應集**]。

新的對應集會顯示在&#x200B;[!UICONTROL **對應集**]&#x200B;標籤上，您可以在此開啟它以檢閱其詳細資料。

### 匯出對應集

您可以匯出對應集以搭配其他移轉任務或其他工具使用。

<!-- Confirm where the export control lives (the Mapping sets list exposes only an Open action) and the export format (for example, JSON). -->

### 發佈和版本對應集

每個對應集都有狀態和版本。 在&#x200B;[!UICONTROL **對應集**]&#x200B;標籤上，對應集可以顯示為：

* [!UICONTROL **草稿**]：對應集仍在編輯中。

* [!UICONTROL **已發佈**]：對應集已完成。

* 移轉&#x200B;**]中的[!UICONTROL **：對應集已繫結至一或多個移轉。

<!-- Confirm how to publish a mapping set, how versions are created (v1, v2, v3), and what "bindings" represent. -->

### 編輯對應集<!-- can you? -->

<!-- Steps pending: confirm whether a mapping set can be edited after creation and where the edit control lives (the Mapping sets list exposes only an Open action). -->

### 刪除對應集<!-- can you? -->

<!-- Steps pending: confirm whether a mapping set can be deleted, and whether deletion is blocked while the set is in use by a migration. -->

## 管理現有的移轉

### 尋找並追蹤您的移轉

[!UICONTROL **移轉**]&#x200B;索引標籤會列出您的移轉及其進度。 使用它來尋找要繼續的移轉，或檢查正在進行的移轉狀態。

* **搜尋**：使用搜尋欄位，依名稱或屬性尋找移轉。

* **篩選器**：依移轉型別或狀態篩選清單。

* **追蹤進度**：每個移轉都會顯示其在三個階段的進度（例如，1/3）以及整體狀態：

  * [!UICONTROL **未開始**]：移轉已建立，但未完成任何階段。

  * [!UICONTROL **進行中**]：至少有一個階段已完成。

  * [!UICONTROL **已完成**]：所有三個階段都已完成。

若要繼續移轉，請選取旁邊的&#x200B;[!UICONTROL **開啟**]。

<!-- The row actions ("...") menu was not captured in the walkthrough. Confirm which actions it contains (for example, rename, duplicate, or delete a migration). -->

