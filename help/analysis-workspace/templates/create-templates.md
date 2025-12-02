---
description: 了解在 Analysis Workspace 中如何建立和管理範本。
title: 建立和管理範本
feature: Workspace Basics
role: User, Admin
exl-id: 23cdf02f-56a1-4465-ae7f-b3a1bcad28af
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1851'
ht-degree: 100%

---

# 建立和管理範本

管理員可以建立範本並將其保存以供公司中的其他登入人使用。

登入公司中的人員可以依照「[使用範本](/help/analysis-workspace/templates/use-templates.md)」中的說明使用這些公司範本。

## 建立範本 {#create-templates}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="use-case-ajo-template"
>title="在 Journey Optimizer 中使用範本"
>abstract="當您在 Journey Optimizer 中使用此範本時，會使用在 Adobe Journey Optimizer 中設定為預設資料視圖的資料視圖，不論 Customer Journey Analytics 中此範本選取的資料視圖為何。"

<!-- markdownlint-enable MD034 -->

若要建立可供您登入公司的人員使用的新範本：

1. 在 Analysis Workspace 中，將專案建置成您想要的狀態。

1. 選取「[!UICONTROL **專案**] > **[!UICONTROL 另存為範本…]**」。

   ![公司範本](assets/company-template-save.png)

1. 在「[!UICONTROL 另存為範本]」對話框中註明以下資訊：

   | 欄位 | 說明 |
   |---------|----------|
   | **[!UICONTROL 名稱]** | 為範本提供說明性名稱。 |
   | **[!UICONTROL 說明]** | 為範本提供簡短說明，內容要說明其預期用途。 |
   | **[!UICONTROL 為什麼使用此範本]** | 提供簡短說明，以告知組織中的人員如何使用此範本。此說明會顯示在範本的預覽頁面上。 |
   | **[!UICONTROL 頻道]** | 選擇套用於此範本的任何適用管道。您可以選取多個管道： **[!UICONTROL 網頁]**、**[!UICONTROL 行動]**、**[!UICONTROL 跨管道]**、**[!UICONTROL 呼叫中心]**&#x200B;和&#x200B;**[!UICONTROL 商店內]**<p>您選取的選項會決定範本的顯示位置，以及從組織範本頁面存取該範本要採用的區段。</p> |
   | **[!UICONTROL 使用案例]** | 選擇套用此範本的任何使用案例。您可以選取多個使用案例： **[!UICONTROL 參與度]**、**[!UICONTROL 轉換率]**、**[!UICONTROL 客群]**、**[!UICONTROL 贏取]**&#x200B;和 **[!UICONTROL Journey Optimizer]**。 <p>您的選擇決定範本在組織範本頁面上的位置。使用者可以導覽至範本，也可以按使用案例來篩選清單。 </p><p>**備註：**&#x200B;當您選取 **[!UICONTROL Journey Optimizer]** 選項後，該範本可在 Adobe Journey Optimizer 中使用。在 Journey Optimizer 中，**[!UICONTROL 報告]**&#x200B;頁面上有一個下拉式選單，允許使用者選取此範本或預設範本。若要了解更多資訊，請參閱 Journey Optimizer 中的「[開始使用更新的報告體驗](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/reporting/channel-report/report-gs-cja)」。</p><p>選取 Journey Optimizer 選項時請考慮以下事項：</p><ul><li>唯有當您在 Customer Journey Analytics 中使用的資料視圖內有 Journey Optimizer 資料時，才能使用此選項。</li><li>當您在 Journey Optimizer 中使用此範本時，會使用在 Adobe Journey Optimizer 中設定為預設資料視圖的資料視圖，不論 Customer Journey Analytics 中此範本選取的資料視圖為何。<br/>如需有關在 Journey Optimizer 中將資料視圖設定為預設資料視圖的詳細資訊，請參閱[建立或編輯資料視圖](/help/data-views/create-dataview.md)中的[相容性](/help/data-views/create-dataview.md#compatibility)。</li></ul> |
   | **[!UICONTROL Journey Optimizer 活動類型]** | 選擇要與此範本關聯的 Journey Optimizer 活動類型： **[!UICONTROL 行銷活動]**、**[!UICONTROL 歷程]**、**[!UICONTROL 登陸頁面]**、**[!UICONTROL 報告]**&#x200B;或 **[!UICONTROL 訂閱]**。 <p>如果您希望此範本與所有活動類型關聯，請將此欄位留空。</p><p>只有在「**[!UICONTROL 使用案例]**」欄位中選取 **[!UICONTROL Journey Optimizer]** 時，此欄位才會顯示。</p> |
   | **[!UICONTROL Journey Optimizer 活動]** | 選擇要與此範本關聯的 Journey Optimizer 活動。 <p>如果您希望此範本與所選活動類型的所有活動相關聯，請將此欄位留空。</p><p>只有在「**[!UICONTROL 使用案例]**」欄位中選取 **[!UICONTROL Journey Optimizer]** 時，此欄位才會顯示。</p> |
   | **[!UICONTROL 標記]** | 指定您想要套用於範本的任何索引標籤。人員可以根據您新增的索引標籤來篩選範本清單。 |

1. 選取「[!UICONTROL **另存為範本**]」。

若要了解關於使用者如何根據範本建立專案的資訊，請參閱[使用範本](/help/analysis-workspace/templates/use-templates.md)中的「[根據範本建立專案](/help/analysis-workspace/templates/use-templates.md#create-a-project-based-on-a-template)」。

## 編輯或刪除範本

管理員可以編輯或刪除公司範本。

1. 在 Analysis Workspace 中，選取 [!UICONTROL **Workspace**] 索引標籤，然後在左側欄中的「**[!UICONTROL 範本]**」下，選取  **[!UICONTROL _login_company_name _範本]**

1. 如果您正在查看欄檢視 ![欄檢視圖示](assets/column-view-icon.png) 中的範本：

   1. 前往要編輯或刪除的範本，選取範本名稱旁邊的資訊圖示。

      ![公司範本資訊](assets/company-template-info.png)

   1. 選取「**[!UICONTROL 預覽]**」。

   1. 選取更多圖示，然後選取「**[!UICONTROL 編輯]**」或「**[!UICONTROL 刪除]**」。

      ![編輯或刪除範本](assets/company-template-edit-delete.png)

1. 如果您正在查看卡片檢視 ![卡片檢視圖示](assets/card-view-icon.png) 中的範本：

   1. 找到您要編輯或刪除的範本。

      ![公司範本卡片檢視](assets/company-template-cards.png)

   1. 將滑鼠停留在範本上，然後選取「**[!UICONTROL 預覽]**」。

   1. 選取更多圖示，然後選取「**[!UICONTROL 編輯]**」或「**[!UICONTROL 刪除]**」。

      ![公司範本卡片編輯或刪除](assets/company-template-card-edit-delete.png)

1. 如果您正在編輯範本，請進行所需的編輯，然後選取「[!UICONTROL **專案**] > **[!UICONTROL 另存為範本...]**」。

   ![公司範本](assets/company-template-save.png)

1. 在「[!UICONTROL 另存為範本]」對話框中註明以下資訊：

   | 欄位 | 說明 |
   |---------|----------|
   | **[!UICONTROL 名稱]** | 為範本提供說明性名稱。 |
   | **[!UICONTROL 說明]** | 為範本提供簡短說明，內容要說明其預期用途。 |
   | **[!UICONTROL 為什麼使用此範本]** | 提供簡短說明，以告知組織中的人員如何使用此範本。此說明會顯示在範本的預覽頁面上。 |
   | **[!UICONTROL 頻道]** | 選擇套用於此範本的任何適用管道。您可以選取多個管道： **[!UICONTROL 網頁]**、**[!UICONTROL 行動]**、**[!UICONTROL 跨管道]**、**[!UICONTROL 呼叫中心]**&#x200B;和&#x200B;**[!UICONTROL 商店內]**&#x200B;如果未選取任何管道，則範本會包含在所有管道中。<p>您選擇的選項會決定範本的顯示位置，以及從組織範本頁面存取該範本要採用的篩選器。</p> |
   | **[!UICONTROL 使用案例]** | 選擇套用此範本的任何使用案例。您可以選取多個使用案例： **[!UICONTROL 參與度]**、**[!UICONTROL 轉換率]**、**[!UICONTROL 客群]**、**[!UICONTROL 贏取]**&#x200B;和 **[!UICONTROL Journey Optimizer]**。 <p>您的選擇決定範本在組織範本頁面上的位置。使用者可以導覽至範本，也可以按使用案例來篩選清單。 </p><p>**備註：**&#x200B;當您選取 **[!UICONTROL Journey Optimizer]** 選項後，該範本可在 Adobe Journey Optimizer 中使用。在 Journey Optimizer 中，**[!UICONTROL 報告]**&#x200B;頁面上有一個下拉式選單，允許使用者選取此範本或預設範本。若要了解更多資訊，請參閱 Journey Optimizer 中的「[開始使用更新的報告體驗](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/reporting/channel-report/report-gs-cja)」。</p><p>選取 Journey Optimizer 選項時請考慮以下事項：</p><ul><li>唯有當您在 Customer Journey Analytics 中使用的資料視圖內有 Journey Optimizer 資料時，才能使用此選項。</li><li>當您在 Journey Optimizer 中使用此範本時，會使用在 Adobe Journey Optimizer 中設定為預設資料視圖的資料視圖，不論 Customer Journey Analytics 中此範本選取的資料視圖為何。<br/>如需有關在 Journey Optimizer 中將資料視圖設定為預設資料視圖的詳細資訊，請參閱[建立或編輯資料視圖](/help/data-views/create-dataview.md)中的[相容性](/help/data-views/create-dataview.md#compatibility)。</li></ul> |
   | **[!UICONTROL Journey Optimizer 活動類型]** | 選擇要與此範本關聯的 Journey Optimizer 活動類型： **[!UICONTROL 行銷活動]**、**[!UICONTROL 歷程]**、**[!UICONTROL 登陸頁面]**、**[!UICONTROL 報告]**&#x200B;或 **[!UICONTROL 訂閱]**。 <p>如果您希望此範本與所有活動類型關聯，請將此欄位留空。</p><p>只有在「**[!UICONTROL 使用案例]**」欄位中選取 **[!UICONTROL Journey Optimizer]** 時，此欄位才會顯示。</p> |
   | **[!UICONTROL Journey Optimizer 活動]** | 選擇要與此範本關聯的 Journey Optimizer 活動。 <p>如果您希望此範本與所選活動類型的所有活動相關聯，請將此欄位留空。</p><p>只有在「**[!UICONTROL 使用案例]**」欄位中選取 **[!UICONTROL Journey Optimizer]** 時，此欄位才會顯示。</p> |
   | **[!UICONTROL 標記]** | 指定您想要套用於範本的任何索引標籤。人員可以根據您新增的索引標籤來篩選範本清單。 |

1. 選取「[!UICONTROL **另存為範本**]」。

## 重新命名、標記或核准範本

管理員可以重新命名、標記和核准公司範本。

1. 在 Analysis Workspace 中，選取「[!UICONTROL **Workspace**]」索引標籤，然後選取左側邊欄中的「**[!UICONTROL 專案索引標籤]**」。

1. 選取篩選器圖示，以篩選專案清單。

1. 在篩選器邊欄中，選取「**[!UICONTROL 其他篩選器]**」，然後選取「**[!UICONTROL 公司範本]**」。

   顯示公司範本清單。 除非已釘選，否則不會顯示所有的一般專案。

   公司範本可從範本名稱前面的![範本圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileTemplate_18_N.svg)來辨識。

   ![顯示公司範本篩選器](assets/company-templates-filter.png)

1. 按一下範本旁的「**...**」省略號圖示，可查看可用選項。

   ![公司範本行動](assets/company-templates-actions.png)

1. 選取「**[!UICONTROL 重新命名]**」、「**[!UICONTROL 標籤]**」或「**[!UICONTROL 核准]**」。

   您也可以刪除範本，或可以依[編輯或刪除範本](#edit-or-delete-templates)的說明來刪除範本。

1. (選項) 若要返回一般檢視，請在篩選器邊欄中取消選取「**[!UICONTROL 公司範本]**」。

## 將缺少的元件新增至所提供範本的資料檢視

依預設，Adobe 所提供的部分範本無法使用，因為這些範本含有不在您資料檢視中的元件。

對於每個缺少的元件，資料檢視中都有一個相符的內容標籤。您需要將相符的內容標籤新增至資料檢視中已有的元件，或者需要將新元件新增至資料檢視並向其新增內容標籤。

若要將缺少的元件新增至範本：

1. 在 Analysis Workspace 中，選取 [!UICONTROL **Workspace**] 索引標籤，然後在左側邊欄中的「**[!UICONTROL 範本]**」下，選取「**[!UICONTROL Adobe 範本]**」。

1. 選取篩選器圖示，以篩選範本清單。

1. 選取「**[!UICONTROL 未準備好供使用]**」，顯示需要不在資料檢視中的元件範本。

   ![使用缺少元件的範本](assets/template-not-ready.png)

1. 尋找未準備好用在資料檢視的範本。

1. 進行下列一項：

   * **如果您正在查看欄檢視** ![欄檢視圖示](assets/column-view-icon.png) 中的範本：

      1. 前往尚未準備好用在資料檢視的範本，然後選取範本名稱旁邊的資訊圖示。

         ![公司範本資訊](assets/company-template-info.png)

      1. 選取「**[!UICONTROL 預覽]**」。

         ![範本預覽頁面](assets/template-preview.png)

   * **如果您正在查看卡片檢視** ![卡片檢視圖示](assets/card-view-icon.png) 中的範本：

      1. 尋找未準備好用在資料檢視的範本。

         ![公司範本卡片檢視](assets/company-template-cards.png)

      1. 將滑鼠停留在範本上，然後選取「**[!UICONTROL 預覽]**」。

         ![範本預覽頁面](assets/template-preview.png)

1. **[!UICONTROL 缺少元件]**&#x200B;部分會顯示資料檢視缺少的元件清單。選取「**[!UICONTROL 將這些元件新增至您的資料檢視]**」。

   資料檢視的設面頁面會顯示在新的索引標籤中。

1. 選取資料檢視的「**[!UICONTROL 元件]**」索引標籤。

   ![資料檢視元件索引標籤](assets/template-dataview.png)

1. 對於每個被列為範本缺失的元件，請在「**[!UICONTROL 元件]**」索引標籤進行下列一項：

   * 在「**[!UICONTROL 包含的元件]**」部分中，選取您想供缺失元件使用且已包含在資料檢視中的元件。

   * 新增元件至您想要供缺失元件使用的資料檢視，然後選取該元件。

     若要新增元件至資料檢視，請搜尋結構描述欄位清單，然後將其拖曳至「**[!UICONTROL 包含的元件]**」部分。

1. 選取元件後，在右欄找到「**[!UICONTROL 內容標籤]**」下拉式選單。

   ![資料檢視元件索引標籤](assets/template-dataview-context-label.png)

1. 在「**[!UICONTROL 內容標籤]**」下拉式選單中，選取與缺失元件同名稱的內容標籤。

1. 選取&#x200B;**[!UICONTROL 「儲存並繼續」]**。

1. 對於缺少的元件，將符合的內容標籤新增至資料檢視中的元件；然後，對每個缺少元件重複此過程。


## 存取公司範本

如同使用 Adob&#x200B;&#x200B;e 提供的範本一樣，組織中的使用者可以存取管理員建立的範本。

有關如何存取公司範本的資訊，請參閱「[存取並執行範本](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template)」(在「[使用範本](/help/analysis-workspace/templates/use-templates.md)」中)。

## 隱藏「範本」索引標籤

管理員可以為組織內的所有使用者隱藏「範本」索引標籤。

1. 前往「**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 元件]** > **[!UICONTROL 偏好設定]** > **[!UICONTROL 公司]**」。
1. 選取選項至&#x200B;**[!UICONTROL 「隱藏範本」索引標籤]**。
