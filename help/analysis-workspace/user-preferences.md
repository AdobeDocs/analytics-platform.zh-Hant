---
title: 如何設定 Analysis Workspace 內的使用者偏好設定
description: 您可以設定使用者的一般和專案偏好設定。
feature: Workspace Basics
exl-id: 6a934be7-0612-41ff-964e-77abc0b1efda
solution: Customer Journey Analytics
role: User
source-git-commit: 191693bc970fcf59ee51706365abde0ee30e3d3d
workflow-type: tm+mt
source-wordcount: '3873'
ht-degree: 75%

---

# 使用者偏好設定

對於您建立的所有新專案或面板，您可以管理 Analysis Workspace 以及相關元件的使用者設定或偏好設定。現有專案和面板不受影響。

## 更新偏好設定

您可以透過以下方式更新您的偏好設定：

- 從 Workspace 主介面選取![UserAdmin](/help/assets/icons/UserAdmin.svg)**[!UICONTROL 編輯偏好設定]**。
- 在 Workspace 專案中工作時，從選單中選取&#x200B;**[!UICONTROL 專案]** > **[!UICONTROL 使用者偏好設定]**。
- 從Customer Journey Analytics的頂端功能表列選取&#x200B;**[!UICONTROL 元件]** > **[!UICONTROL 偏好設定]** （僅適用於產品管理員）。

## 設定偏好設定

您可以設定以下偏好設定：

### 一般偏好設定

一般偏好設定適用於瀏覽器中您的 Customer Journey Analytics 體驗。如需如何存取這些偏好設定的相關資訊，請參閱[更新偏好設定](#update-preferences)。

| 偏好設定 | 選項 |
| --- | --- |
| **[!UICONTROL 登陸頁面]** | 選擇存取 Customer Journey Analytics 時顯示為預設頁面的頁面： <ul><li>專案清單 (預設)</li><li>空白專案</li><li>空白趨勢引導式分析</li><li>特定專案，從清單中選取</li></ul> |
| **[!UICONTROL 秘訣]** | 在 Analysis Workspace 右下方區域的藍色框中顯示提示。 <p>此選項已預設啟用。</p> |
| **[!UICONTROL 左側面板群組中顯示的元件]** | 在左側面板的「元件」選單中，選取每個元件的顯示數量。 <p>如果為元件群組選擇 0，則無法再從左側面板存取此元件群組。</p><p>預設情況下，以下每個元件群組皆顯示 5 個元件：</p> <ul><li>維度</li><li>量度</li><li>篩選器</li><li>日期範圍</li></ul> <p>如需有關 Analysis Workspace 中元件的詳細資訊，請參閱[元件概觀](/help/components/overview.md)。</p> |

### IMS 組織偏好設定 {#ims-organization-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_shareonlyworkspace"
>title="僅允許與 Workspace 使用者共用"
>abstract="啟用後，在共用 Analysis Workspace 專案時，使用者將無法再使用&#x200B;**[!UICONTROL 與任何人共用]**&#x200B;選項。先前透過此共用選項獲得專案存取權的人員無法再存取該專案。"

>[!CONTEXTUALHELP]
>id="workspace_prefs_requireexperiencecloudauth"
>title="需要 Experience Cloud 驗證"
>abstract="啟用後，透過 Analysis Workspace 中的「與任何人共用」選項取得專案存取權限的人員，就必須使用其 Experience Cloud 認證進行驗證。"

<!-- markdownlint-enable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_prefs_projectcommenting"
>title="允許評論專案"
>abstract="啟用後，Analysis Workspace中每個專案的右側邊欄中都會顯示註解區域。"

<!-- markdownlint-enable MD034 -->

您可以更新套用於組織內所有使用者和專案的公司偏好設定。如需如何存取這些偏好設定的相關資訊，請參閱[更新偏好設定](#update-preferences)。

| 區域 | 偏好設定 | 選項 |
| --- | --- | --- |
| **專案共用** | | |
| | 僅允許與 Workspace 使用者共用 | 啟用此選項後，組織中的使用者無法在&#x200B;**[!UICONTROL 共用]**&#x200B;選單中看到&#x200B;**[!UICONTROL 與任何人共用]**&#x200B;選項。這表示使用者無法與組織中沒有 Analysis Workspace 帳戶的人員共用專案，如[共用專案](/help/analysis-workspace/curate-share/share-projects.md)中的[與任何人共用專案 (無需登入) ](/help/analysis-workspace/curate-share/share-projects.md#share-public-link)所述。<br/>依照預設，除了擁有已授權之 Healthcare Shield 的客戶以外，所有組織均停用此選項 (亦即使用者可以與組織外部的人員共用專案)。 <p>啟用或停用此選項時，請考慮以下事項：<ul><li>啟用此選項後，之前透過[!UICONTROL 與任何人共用]共用選項取得專案存取權限的人員，就無法再存取該專案。</li><li>如果啟用此選項 (僅允許與 Workspace 使用者共用)，之後再停用 (允許與任何人共用)，則之前透過[!UICONTROL 與任何人共用]共用選項取得專案存取權限的人員，不會自動重新取得專案的存取權限。在這種情況下，共用專案的使用者與任何人共用專案時，就必須啟用可用的&#x200B;[!UICONTROL **連結使用中**]&#x200B;選項&#x200B;**([!UICONTROL 共用]** > **[!UICONTROL 與任何人共用]**)，如[共用專案](/help/analysis-workspace/curate-share/share-projects.md)中的[與任何人共用專案 (無需登入)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) 所述。</li><li>**對於授權 Healthcare Shield 的客戶：**&#x200B;此選項預設為啟用且無法停用。在您停用此選項讓使用者可以使用[!UICONTROL 與任何人共用]共用選項之前，您必須先在 Adobe Admin Console 新增[!UICONTROL 與任何人共用專案連結]權限 (位於[!UICONTROL 報告工具]下方)。新增權限後，您可以停用此選項，然後接受所產生的法律注意事項。如需有關如何在 Admin Console 中新增權限的資訊，請參閱[在 Admin Console 中管理產品權限](https://helpx.adobe.com/tw/enterprise/using/manage-permissions-and-roles.html)。</li></ul> |
| | 需要 Experience Cloud 驗證 | 當啟用此選項時，透過Analysis Workspace中的「與任何人共用」選項取得專案存取權的使用者，必須使用其Experience Cloud憑證進行驗證。<p>啟用此選項後，每當使用者使用[!UICONTROL 與任何人共用]共用選項共用專案時，共用對話框就會啟用[!UICONTROL 需要 Experience Cloud 驗證]選項，且共用專案的使用者無法停用該選項。如需有關使用者如何與任何人共用專案的資訊，請參閱[與任何人共用專案 (無需登入)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) (在[共用專案](/help/analysis-workspace/curate-share/share-projects.md)中)。 <p> <p>啟用此選項時請考慮以下事項： <ul><li>啟用此選項後，之前透過[!UICONTROL 與任何人共用]共用選項共用，以及未啟用[!UICONTROL 需要 Experience Cloud 驗證]選項的所有專案都會停用。<p>如果啟用此選項 (要求 Experience Cloud 驗證) 之後再停用 (允許擁有該連結的任何人存取專案)，則之前透過[!UICONTROL 與任何人共用]共用選項取得專案存取權限的人員，不會自動重新取得專案的存取權。在這種情況下，共用專案的使用者與任何人共用專案時，必須啟用可用的[!UICONTROL 連結使用中]*選項&#x200B;**([!UICONTROL 共用]** > **[!UICONTROL 與任何人共用]** > **[!UICONTROL 連結使用中]**)，如[共用專案](/help/analysis-workspace/curate-share/share-projects.md)中的[與任何人共用專案 (無需登入)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link)所述。</li><li>您的組織實作 SSO 時才可使用這個選項。如需有關系統管理員如何為您的組織啟用 SSO 的資訊，請參閱「[設定身分識別和單一登入](https://helpx.adobe.com/tw/enterprise/using/set-up-identity.html)」。</p><p>如果您的組織設定 SSO，請檢查主控台是否實作任何種類的自動帳戶建立作業。系統管理員通常會加以設定，如[啟用自動帳戶建立](https://helpx.adobe.com/tw/enterprise/using/automatic-account-creation.html)中所述。</li><li>如果您的組織授權 Healthcare Shield，預設就會啟用此選項且無法停用。</li></ul> |

{style="table-layout:auto"}

<!-- 

Add this to the table above - exchange - for pipe: (End of April, 2025 when project commenting is GA)

**Project commenting** 
- - Allow commenting on projects - When this option is enabled, a comments area is available in the right rail of each project in Analysis Workspace. <p>Project owners can disable the comments area for a given project, as described in [Create projects](/help/analysis-workspace/build-workspace-project/create-projects.md).</p> <p>For more information about commenting in Analysis Workspace projects, see [Add and manage comments in projects](/help/analysis-workspace/build-workspace-project/comment-projects.md).</p> 

-->

### 專案和分析偏好設定 {#project-and-analysis-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_categoricalpalette"
>title="分類調色盤"
>abstract="適用於 Analysis Workspace 和引導式分析中的許多視覺效果。每種顏色代表不同的類別值。"

>[!CONTEXTUALHELP]
>id="workspace_prefs_divergingpalette"
>title="發散調色盤"
>abstract="適用於 Analysis Workspace 和使用者增長引導分析中的同類群組表格。此調色盤具有數值含意，有兩個極端和中間的基準線。"

>[!CONTEXTUALHELP]
>id="workspace_prefs_sequentialpalette"
>title="序列調色盤"
>abstract="適用於頻率趨勢 (堆疊條狀圖) 引導式分析。此調色盤具有從淺到深的數值含意。"

您可以為所有新的 Analysis Workspace 專案、新的 Analysis Workspace 面板和新的引導式分析自訂這些偏好設定。如需有關如何存取這些偏好設定的資訊，請參閱[更新偏好設定](#update-preferences)。

您也可以針對 Analysis Workspace 中的個別專案自訂其中部分相同偏好設定，如[專案概觀](/help/analysis-workspace/build-workspace-project/freeform-overview.md)中所述。

| 區域 | 偏好設定 | 選項 |
| --- | --- | --- |
| **顯示** | | |
|  | [檢視密度](/help/analysis-workspace/build-workspace-project/view-density.md) | 減少左側面板、自由格式表格和同類群組表格的垂直邊框間距，以選擇要在畫面上顯示多少內容。 <ul><li>精簡</li><li>舒適</li><li>展開 (預設)</li></ul> |
| | [調色盤](/help/analysis-workspace/build-workspace-project/color-palettes.md) | 選擇 Analysis Workspace 和引導式分析中使用的視覺效果調色盤。 <ul><li> 類別調色盤：套用至 Analysis Workspace 和引導式分析的多個視覺效果。每種顏色代表相異的類別值。從 Adobe 提供的選項中進行選擇，或輸入由逗號分隔的十六進位值定義的自訂調色盤。</li><li> 偏離調色盤：套用至 Analysis Workspace 和使用者增長引導式分析中的同類群組表格。此調色盤具有數值含義，其中包含兩個極端和中間的基線。<li> 循序調色盤：套用至頻率趨勢 (堆疊長條) 引導式分析。該調色盤具有從淺到深的數值含義。</li></ul> |
| **資料** | | |
|  | [資料視圖](/help/analysis-workspace/c-panels/panels.md#data-view) | 從表格和視覺效果衍生其資料的位置進行資料選擇。 <ul><li>最近使用 (預設)</li><li>從清單中選取的特定資料視圖</li></ul> |
|  | [行事曆](/help/analysis-workspace/c-panels/panels.md#calendar) | 從以下清單中選取： <ul><li>Adobe 提供的範圍 (預設為「本月」)</li><li>您可以啟用[!UICONTROL 預設使日期範圍元件與面板行事曆相對應]。</li></ul> |
|  | [面板類型](/help/analysis-workspace/c-panels/panels.md#panel-types) | <ul><li>自由格式 (預設)</li><li>空白</li><li>快速深入分析</li></ul> |
|  | 實例計數 | 啟用[!UICONTROL 計算重複實例數]以指定是否要將重複實例計入報告中。例如，若啟動，多次連續檢視相同頁面視為檢視多個頁面。停用後，多次連續檢視相同頁面將計為單次頁面檢視。 <p>**注意：**&#x200B;此設定只會影響特定量度 (例如工作階段)，不適用於「流程」或「流失」視覺效果。</p> |
|  | 數字格式 | <ul><li>1,000.00 (預設)</li><li>1.000,00</li><li>1 000,00</li></ul> |
|  | CSV 分隔字元 | <ul><li>逗號 (預設)</li><li>分號</li><li>冒號</li><li>直立線符號</li><li>時段</li><li>空格</li><li>定位</li></ul> |
|  | 顯示註解 | 選取專案中是否顯示註解。如需註解的詳細資訊，請參閱[註解概觀](/help/components/annotations/overview.md)。 |


### 自由格式表格偏好設定 {#freeform-table-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_showanomalies"
>title="顯示異常狀況"
>abstract="選取&#x200B;**[!UICONTROL 顯示異常狀況]**&#x200B;將自動對新增至時間序列自由格式表格視覺效果的第一個量度欄執行異常偵測。"

>[!CONTEXTUALHELP]
>id="workspace_prefs_showforecast"
>title="顯示預測"
>abstract="選取&#x200B;**[!UICONTROL 顯示預測]**&#x200B;將自動對新增至時間序列自由格式表格視覺效果的第一個量度欄進行預測。"


>[!CONTEXTUALHELP]
>id="workspace_prefs_defaulttablemetric"
>title="預設表格量度"
>abstract="選取用於自由格式表格的預設量度。如果選取的資料檢視不包含選取的預設量度，表格會自動切換至另一個主要量度。"


您可以為在 Analysis Workspace 中建立的所有新專案自訂自由格式表格偏好設定。如需如何存取這些偏好設定的相關資訊，請參閱[更新偏好設定](#update-preferences)。

也可為個別表格自訂其中一些相同偏好設定。

選取連結的區段標題，以取得有關可用偏好設定的詳細資訊和內容。

| 區域 | 偏好設定 | 選項 |
| --- | --- | --- |
| **表格** | | |
| | 表格類型 | <ul><li>自由格式</li><li>表格產生器</li></ul> |
| | 預設表格量度 | <ul><li>發生次數</li><li>不重複訪客</li><li>造訪</li></ul> |
| | 預設表格維度 | 從分鐘、小時、日、週、月、季度或年中選擇。 |
| | 統一日期 | 選取此選項，讓每一欄的日期與同一列中所有開始日期一致。 |
| **[欄](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)** | | |
| | 繞排標題文字 | 讓您自由格式表格中的標頭文字環繞，讓標頭變得更容易閱讀，表格也更便於分享。這項設定對 PDF 的轉譯還有較長名稱的量度來說，非常實用。預設啟用。 |
| | 顯示總計 | 此總數通常等於[!UICONTROL 總量]或是其子集。 它反映的是在自由表格中套用的任何表格區段，包括[!UICONTROL 不包含任何專案]選項。 |
| | 顯示總計 | 此總數代表已收集的所有事件，有時稱為&#x200B;*資料檢視總數*。 在面板層級或自由表格內套用區段時，這項總計會經過調整，藉此反映所有符合區段條件的事件。 具[靜態列](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md)的表格或劃分不支援全部總計。 |
| | 顯示走勢圖 | 顯示或隱藏圖表底部的折線圖。隱藏時，圖例會變更為不再以視覺化方式參照線條。 |
| | 數字 | 決定儲存格是否要顯示/隱藏量度數值。例如，如果量度為「頁面檢視」，則該數值為列項目的頁面檢視數量。 |
| | 百分比 | 決定儲存格是否要顯示/隱藏量度百分比值。例如，如果量度是頁面檢視，則百分比值是列專案的頁面檢視次數除以欄的頁面檢視總次數。  注意：為了比例更精確，您可以顯示超過100%的數值。 您也可以將上限移動到1,000%，以確保欄位的寬度可以變得太大。 |
| | 顯示異常狀況 <!-- This setting was moved from the "Project" tab. this is already in the tool/docs under "Freeform table, But the doc doesn't give a definition. --> | 決定是否要在該欄的數值中執行異常偵測。 |
| | 顯示預測 | 決定是否會對您建立之任何時間序列自由格式表格中的第一個量度欄自動顯示預測值。 |
| | 將零解讀為沒有值 | 針對含有 0 值的儲存格，決定顯示 0 或空白儲存格。如果您要查看某月的每日資料，而當月有部分天數尚未發生，這個方法就相當實用。若不想在未來的日期中顯示 0 值，則可選擇顯示空白儲存格。圖表也會遵循此設定（例如，勾選此設定時，購物車不會顯示帶有0值的線條或長條）。 |
| | 背景 | 決定儲存格是否要顯示/隱藏所有儲存格格式，包括長條圖和條件式格式 <ul><li>長條圖</li> 顯示長條圖，當中呈現相對於欄總數的儲存格數值。 <li>條件式格式</li>如需條件式格式的詳細資訊，請參閱[欄設定](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)中的「條件式格式」</ul> |
| | 儲存格預覽 | 顯示目前已套用選定格式選項之各儲存格的呈現方式預覽。 |
| **[列](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)** | | |
| | 依位置劃分 | 如果您希望劃分保留在項目的位置，而非項目本身，請選取此選項。如需劃分的詳細資訊，請參閱[劃分維度](/help/components/dimensions/t-breakdown-fa.md)。 |
| | 百分比計算 | <ul><li>欄</li><li>列</li></ul> |
| | 欄總計 (僅限靜態列) | <ul><li>顯示列總和：顯示各個條列項目的總和 </li><li>顯示全部總量：顯示已排除重複項目後的列總和。</li></ul> |

### 視覺效果偏好設定 {#visalization-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaultflowcontainer"
>title="預設容器"
>abstract="選取用於[!UICONTROL 流量]視覺效果的預設容器。如果選取的資料檢視未包含選取的預設容器，則[!UICONTROL 流量]視覺效果會自動切換至另一個主要容器。"

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaultfalloutcontainer"
>title="預設容器"
>abstract="選取用於[!UICONTROL 流失]視覺效果的預設容器。如果選取的資料檢視未包含選取的預設容器，[!UICONTROL 流失]視覺效果會自動切換至另一個主要容器。"

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaulthistogramcountingmethod"
>title="預設計數法"
>abstract="選取用於[!UICONTROL 直方圖]視覺效果的預設計數法。如果選取的資料檢視未包含選取的預設計數方法，[!UICONTROL 色階分佈圖]視覺效果會自動切換至另一個主要計數方法。"

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaultjourneycanvascontainer"
>title="預設容器"
>abstract="選取用於[!UICONTROL 歷程畫布]視覺效果的預設容器。如果選取的資料檢視未包含選取的預設容器，[!UICONTROL 歷程畫布]視覺效果會自動切換至另一個主要容器。"


您可以為在 Analysis Workspace 中建立的所有新專案更新偏好設定。如需如何存取這些偏好設定的相關資訊，請參閱[更新偏好設定](#update-preferences)。

也可為個別視覺效果自訂其中一些相同偏好設定。

選取連結的區段標題，以取得有關可用偏好設定的詳細資訊和內容。

| 區域 | 偏好設定 | 選項 |
| --- | --- | --- |
| **一般預設值** | | |
| | 百分比 | 以百分比顯示所有視覺效果的值。 |
| | 可見圖例 | 可讓您隱藏所有視覺效果的詳細圖例文字。 |
| | 限制項目數量上限 | 減少所有視覺效果的 X 軸項目數量。如果您有大型資料集，此偏好設定相當實用。 |
| | 顯示雙軸 (適用時) | 僅適用於具有兩個量度時 - 可在左側 (針對一個量度) 和右側 (針對另一個量度) 各顯示一個 Y 軸。當繪製的量度大小非常不同時，此偏好設定會很有幫助。 |
| | 標準化 (適用時) | 強制量度為相同比例。當繪製的量度大小非常不同時，此偏好設定會很有幫助。 |
| | 將 Y 軸固定於零 | 如果圖表上繪製的所有值都明顯大於零，則圖表預設值會將y軸底部更新為非零。 如果您核取此方塊，Y軸會強製為零（並重新繪製圖表）。 |
| | 錨點異常縮放 Y 軸 | y軸會使用異常值來縮放。 |
| **[折線圖](/help/analysis-workspace/visualizations/line.md)** | | |
| | 百分比 | 以百分比顯示線條視覺效果的值。 |
| | 可見圖例 | 可讓您隱藏線條視覺效果的詳細圖例文字。 |
| | 限制項目數量上限 | 減少線條視覺效果的 X 軸項目數量。如果您有大型資料集，此偏好設定相當實用。 |
| | 顯示雙軸 (適用時) | 僅適用於具有兩個量度時 - 可在左側 (針對一個量度) 和右側 (針對另一個量度) 各顯示一個 Y 軸。當繪製的量度大小非常不同時，此偏好設定會很有幫助。 |
| | 標準化 (適用時) | 強制量度為相同比例。當繪製的量度大小非常不同時，此偏好設定會很有幫助。 |
| | 顯示 x 軸 | 在折線圖上顯示 x 軸。 |
| | 顯示 y 軸 | 在折線圖上顯示 y 軸。 |
| | 固定 Y 軸 | 如果圖表上繪製的所有值都明顯大於零，則圖表預設會呈現y軸底部的「非零」。 如果您核取此方塊，Y軸將被強製為零（並重新繪製圖表）。 |
| | 允許異常縮放 Y 軸 | 如果圖表中有多個量度，您必須將滑鼠移到每個異常值上方，才能查看該量度的信賴帶。為了讓視覺效果更清晰，異常偵測信賴區間不會自動縮放 Y 軸。此設定允許信賴區間來縮放視覺效果。 <p>如需詳細資訊，請參閱[在 Analysis Workspace 中檢視異常](/help/analysis-workspace/c-anomaly-detection/view-anomalies.md)。</p> |
| | 允許預測縮放 Y 軸 | 如果您的預測值在歷史值上下限之外，Y軸不會自動縮放這些預測值。 開啟時，此選項會正確縮放預測值的y軸。 |
| | 顯示最小值 | 覆蓋最小值標籤，以快速反白標示量度中的谷值。 注意：最小值是從視覺效果中的可見資料點衍生而來，而非維度中的完整數值集。 |
| | 顯示最大值 | 覆蓋最大值標籤，以快速反白標示量度中的尖峰。 注意：最大值是從視覺效果中的可見資料點衍生而來，而非維度中的完整數值集。 |
| | 顯示趨勢線 | 顯示迴歸或移動平均趨勢線至您的折線圖序列。趨勢線有助於描繪出資料中更清晰的模式。 |
| **[同類群組](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)** | | |
| | 詳細程度 | 對於趨勢視覺效果，您可以變更時間詳細程度 (日、週、月、季或年)。這項變更也適用於資料來源表。 |
| | 僅顯示百分比 | 移除數值並僅顯示百分比。 |
| | 將百分比四捨五入到最接近的整數 | 將百分比四捨五入為最接近的整數，而非顯示小數值。 |
| | 顯示平均百分比列 | 在表格頂端插入新列，然後在每個欄中加入平均值。 |
| **[組合圖](/help/analysis-workspace/visualizations/combo-charts.md)** | | |
| | 顯示 X 軸 | 在組合圖上顯示 x 軸。 |
| | 顯示 Y 軸 | 在組合圖上顯示 y 軸。 |
| | 在線上顯示節點 | 在組合圖中的線上顯示節點。 |
| **[關鍵量度摘要](/help/analysis-workspace/visualizations/key-metric.md)** | | |
| | 摘要顯示類型 | <ul><li>強調百分比變化</li><li>強調數字值</li></ul> |
| | 顯示走勢圖 | 顯示或隱藏圖表底部的折線圖。隱藏時，圖例會變更為不再以視覺化方式參照線條。 |
| | 在走勢圖上顯示最大值和最小值 | 在主要和比較折線圖上顯示最小值和最大值. |
| | 顯示比較 | 顯示比較資料。隱藏時，比較折線圖和摘要變更物件將會從視圖中隱藏。 |
| | 數字值選項 | 在&#x200B;[!UICONTROL **關鍵量度摘要**] 一節 <ul><li>顯示百分比變化</li><li>顯示原始差異</li>主要日期範圍與次要日期範圍中量度總值之間的原始差異</ul> |
| **[流失](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md)** | | |
| | 容器 | 選取要分析路徑分析的偏好容器。 偏好的容器可協助您瞭解各種B2B容器層級[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}的帳戶參與情形、個人層級的人員參與情形（跨工作階段），或將分析限制在單一工作階段。 <p>提供下列選項：</p> <ul><li>全域帳戶[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>帳戶[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>購買群組[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>商機[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>工作階段</li><li>人員</li></ul> |
| **[流量](/help/analysis-workspace/visualizations/c-flow/create-flow.md)** | | |
| | 容器 | 選取要分析的偏好容器。 偏好的容器可協助您瞭解各種B2B容器層級[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}的帳戶參與情形、個人層級的人員參與情形（跨工作階段），或將分析限制在單一工作階段。 <p>提供下列選項：</p> <ul><li>全域帳戶[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>帳戶[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>購買群組[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>商機[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>工作階段</li><li>人員</li></ul> |
| | 繞排標籤 | 一般而言，系統會截斷「流量」元素的標籤以節省螢幕空間，但您可勾選此方塊以完整顯示標籤。預設 = 未勾選。 |
| | 包含重複例項 | 「流量」視覺效果是根據維度的例項而定。此設定提供您要包括或排除重複例項的選項，例如頁面重新載入次數。不過，無法從包含多值維度 (例如 listVars、listProps、s.product、銷售 eVars 等) 的「流量」視覺效果中移除重複項目。預設 = 未勾選。 |
| | 顯示工具提示 | 決定當滑鼠懸停在流量視覺效果內的個別節點上時，是否顯示包含節點資料的工具提示。 |
| | 欄數 | 決定您的流量圖中要有多少欄。 |
| | 每欄展開的項目 | 每欄中想要多少項目。 |
| **[歷程畫布](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)** | | |
| | 容器 | 選取要分析路徑分析的偏好容器。 偏好的容器可協助您瞭解各種B2B容器層級[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}的帳戶參與情形、個人層級的人員參與情形（跨工作階段），或將分析限制在單一工作階段。 <p>提供下列選項：</p> <ul><li>全域帳戶[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>帳戶[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>購買群組[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>商機[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}</li><li>工作階段</li><li>人員</li></ul> |
| **堆疊圖** | | |
| | 100% 堆疊 | 區域圖堆疊、橫條圖堆疊、水平橫條圖堆疊等視覺效果的這項設定，會將圖表轉變為「100％ 堆疊」視覺效果。 <p>如需詳細資訊，請參閱[橫條圖和棧疊橫條圖](/help/analysis-workspace/visualizations/bar.md)。</p> |
| **[直方圖](/help/analysis-workspace/visualizations/histogram.md)** | | |
| | 貯體數 | 在視覺效果中選擇日期範圍 (貯體) 的數量。貯體的最大數量是 50。 <p>如需詳細資訊，請參閱[直方圖](/help/analysis-workspace/visualizations/histogram.md)。</p> |
| | 計算方法 | 從下列選項中選擇： <ul><li>點擊</li><li>工作階段</li><li>人員</li></ul> <p>例如，搭配頁面檢視使用時，您可以選擇每人頁面檢視次數、造訪的頁面檢視次數，或每個事件的頁面檢視次數。 若為點擊，自由格式表格會將「發生次數」設為 Y 軸的量度。</p> |
| **[摘要變更](/help/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | 值 | <!-- Seem to be basically the same options as in "Number value options" --> <ul><li>百分比變更</li><li>原始差異</li></ul> |
| | 百分比 | 以百分比顯示摘要變更視覺效果的值。 |
| | 可見圖例 | 可讓您隱藏摘要變更視覺效果的詳細圖例文字。 |
| **[摘要數字](/help/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | 百分比 | 以百分比顯示摘要數字視覺效果的值。 |
| | 可見圖例 | 可讓您隱藏摘要數字視覺效果的詳細圖例文字。 |
| | 摘要值依據 | 從最大值、最小值、平均值、中位數和總和中選擇。 |
| | 縮簡值 | 在&#x200B;**[!UICONTROL 摘要數字]** 一節 |
| **[樹狀圖](/help/analysis-workspace/visualizations/treemap.md)** | | |
| | 百分比 | 以百分比顯示樹狀圖視覺效果的值。 |
| | 限制項目數量上限 | 減少樹狀圖視覺效果的 X 軸項目數量。如果您有大型資料集，此偏好設定相當實用。 |
| **[Venn](/help/analysis-workspace/visualizations/venn.md)** | | |
| | 可見圖例 | 可讓您隱藏 Venn 視覺效果的詳細圖例文字。 |
| **[散佈圖](/help/analysis-workspace/visualizations/scatterplot.md)** | | |
| | 百分比 | 以百分比顯示散佈圖視覺效果的值。 |
| | 可見圖例 | 讓您隱藏散佈圖視覺效果的詳細圖例文字。 |
| | 限制項目數量上限 | 減少散佈圖視覺效果中X軸上的專案數量。  如果您有大型資料集，此偏好設定相當實用。 |
| | 將 y 軸固定於零 | 如果圖表上繪製的所有值都明顯大於零，則圖表預設會呈現y軸底部的「非零」。 如果您核取此方塊，Y軸會強製為零（並重新繪製圖表）。 |

## 還原預設偏好設定

您可以將所有使用者偏好設定還原為系統預設值。此偏好設定不影響公司標籤下的管理員偏好設定。

此動作無法復原。

1. 在 Customer Journey Analytics 中，從頂部選單選取&#x200B;[!UICONTROL **元件**] **>** [!UICONTROL **偏好設定**]。或從 Workspace 選單中選取&#x200B;**[!UICONTROL 專案]** > **[!UICONTROL 使用者設定]**。

1. 在右上方，選取&#x200B;**[!UICONTROL 還原預設值]**。

1. 在&#x200B;**[!UICONTROL 還原系統預設設定]**&#x200B;中選取&#x200B;**[!UICONTROL 還原預設值]**。

## [!UICONTROL 深色佈景主題]

如果您偏好將您的 Customer Journey Analytics 使用者介面設定為深色背景，您可切換至[!UICONTROL 深色佈景主題]。

1. 選取右上方的 Experience Cloud 使用者圖示。

   ![dark-theme](assets/dark-theme.png)

1. 啟用&#x200B;**[!UICONTROL 深色主題]**。

