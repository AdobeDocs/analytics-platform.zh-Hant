---
title: 建立超連結
description: 瞭解如何在Analysis Workspace的自由格式表格中建立維度專案的超連結。
feature: Visualizations
role: User
exl-id: 24fc2d24-b8c2-4664-8b9c-beda284f9033
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1602'
ht-degree: 97%

---

# 在自由表格中建立超連結

您可以為維度項目建立超連結，以使這些在 Analysis Workspace 的自由格式表格中成為可點選項目。

為以下類型的維度項目建立超連結時，這項功能特別有用：

* 具有 URL 值的維度項目 (例如，「頁面 URL」維度)。

* 包含具有 URL 值劃分的維度項目 (例如，具有「頁面 URL」維度劃分的「頁面名稱」維度)。

* 具有屬於 URL 一部分的值的維度項目或劃分 (例如，屬於 URL 一部分的「頁面名稱」維度)。


>[!BEGINSHADEBOX]

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[「在自由格式表格中建立超連結」](https://video.tv.adobe.com/v/3430411/?quality=12&learn=on){target="_blank"}的示範影片。

>[!ENDSHADEBOX]


## 建立超連結

為一個或多個維度項目建立超連結時，請考慮以下事項：

* 您建立的超連結是儲存在 Analysis Workspace 專案內的自由格式表格中。在另一個表格或另一個專案中使用相同維度或維度項目時，超連結不會保留。

* 如果要變更自由格式表格的資料檢視，則為表中維度或維度項目建立的任何超連結仍然可用。此功能假定該維度仍然存在於資料檢視中。

* 建立超連結時不會查看 URL 的有效性。如果您

   * 建立具有無效 URL 的超連結，或者
   * 建立超連結，其中會引用沒有 URL 值的維度項目 (透過直接引用維度項目，或透過使用 `$value` 或 `$breakdown` 變數)，

  然後，點選超連結的使用者將看到一條錯誤訊息，指出該 URL 無效。

* 為單一維度建立的超連結將覆蓋在該維度上建立的超連結。

* 超連結無法在[下載的 PDF 檔案](/help/analysis-workspace/export/download-send.md)中起作用。

若要為一個或多個維度項目建立超連結：

1. 在 Analysis Workspace 自由格式表格中，執行下列其中一項：

   * **為單維度項目建立超連結：** 用滑鼠右鍵按一下表格內部要建立超連結的維度項目，然後選取「[!UICONTROL **建立超連結**]」。

      1. 開啟維度項目的內容選單。
      1. 從內容選單中，選取「[!UICONTROL **建立超連結**]」。

         「[!UICONTROL **建立超連結**]」對話框即會顯示。您建立超連結的維度項目名稱會顯示在對話方框中。

         ![為單一項目對話框建立超連結](assets/hyperlink-dialog-single.png)

   * **為維度欄內所有維度項目建立超連結：** 用滑鼠右鍵按一下維度欄標題中的維度名稱，然後選取「[!UICONTROL **為所有維度項目建立超連結**]」。

      1. 從維度欄標題開啟內容選單。
      1. 從內容選單中，選取「[!UICONTROL **為所有維度項目建立超連結**]」。

         <!-- Do we really need a screenshot ![Create hyperlink for a dimension](assets/hyperlink-multiple-add.png) -->

         「[!UICONTROL **為所有維度項目建立超連結**]」對話框即會顯示。您建立超連結的維度名稱會顯示在對話方框中。

         ![建立超連結對話框](assets/hyperlink-dialog-multiple.png)

1. 從下列選項中選擇：

   * [!UICONTROL **使用維度項目的值作為 URL**]：為具有 URL 值的維度項目選擇此選項，例如「頁面 URL」維度。

     例如，如果您使用「頁面 URL」維度，其中每個維度項目的值都是 URL，則選擇此選項會建立前往該 URL 的超連結。

   * [!UICONTROL **建立自訂 URL**]：指定靜態或動態的自訂 URL。選擇此選項可以為沒有 URL 值的維度項目建立超連結。

     例如：您正在使用「頁面名稱」維度，其中每個維度項目的值是頁面的名稱 (而不是完整的 URL)。然後選擇此選項可以指定一個超連結來用作維度項目的連結。

     如果要為多個維度項目建立動態 URL，可以使用自訂 URL 內的 `$value` 和 `$breakdown` 變數。如需詳細資訊，請參閱下面表格。

     若要建立自訂 URL，請指定以下資訊：

     | 欄位 | 說明 |
     |---------|----------|
     | [!UICONTROL **自訂 URL**] | 指定要用於超連結的自訂 URL。輸入的 URL 必須為完全限定的 URL。例如︰<https://www.example.com><p>您建立的自訂 URL 可以是靜態或動態：</p> <ul><li>**靜態 URL：** 當您希望所有維度項目都連結到同一個 URL 時，您可以為單一維度項目或所有維度項目指定靜態 URL。例如︰`https://wiki.internal.company_name/page_name#item_definition`</p></li><li>**動態 URL：** 如果想要為多個維度項目 (或一個維度欄中的所有維度項目) 建立唯一的超連結，則可以建立動態 URL。<p>若要讓自訂 URL 成為動態性質，您可以在 URL 中包含一個變數，以根據維度的值或劃分維度的值變更 URL。</p><p>使用變數時，若包含在 URL 中屬於無效的字元 (如空格)，這些維度項目都會經過 URL 編碼。</p><p>可用的變數如下：(**註**：雖然可在同一個 URL 中使用這些變數，但單獨使用還是更常見。</p> <ul><li>**`$value`：** 允許您將維度項目的值插入指定的 URL 中。 <p>假設您想要為自由格式表格內所有頁面名稱維度項目建立超連結，其中每個維度項目的值都是網頁 URL 的一部分。在這種情況下，您可以建立一個針對每個維度項目動態調整的單一自訂 URL。<br/>例如：`https://company-name.com/browse/product#\$value`</p><p>當此自訂 URL 套用於值為「ProductY」和「ProductZ」的頁面名稱維度項目時，產生的超連結將如下所示： <br/>`https://company-name.com/browse/product#ProductY` 和<br/>`https://company-name.com/browse/product#ProductZ` </p><p>![在超連結中使用值](assets/table-hyperlinks-vaule.png)</p><p>**提示**：僅將 `$value` 變數新增至自訂 URL 欄位，與建立 URL 時選取「[!UICONTROL **使用維度項目的值**]」選項相同。</p></li><li>**`$breakdown`：** 允許您將劃分維度項目的值插入指定的 URL 中。透過 `$breakdown`，您可以在報告中使用具有使用易記名稱的維度 (例如「產品名稱」維度)。同時，根據可能使對使用者不太好記的劃分維度 (例如產品 ID 或頁面 URL 維度) 產生超連結。<p>引用劃分維度時，最常見的情況是特定維度項只有一個劃分項目。如果特定維度項目有多個劃分項目，則在 URL 中使用第一個劃分項目的值。如果沒有列出劃分項目，則該 URL 無效。劃分項目的排序順序與表格的排序順序相同。</p><p>您可以在下面「[!UICONTROL **劃分維度**]」欄位中指定劃分維度。</p> <p>請考慮以下針對「[!UICONTROL **劃分維度**]」欄位描述的範例情境。</p></li></ul> |
     | [!UICONTROL **劃分維度 (選擇性)**] | 開始輸入您要使用之劃分維度的名稱，然後從下拉式功能表中選取它。 <p>如果您在此欄位中選取劃分維度，則您必須使用在「[!UICONTROL **自訂 URL**]」欄位中指定的 URL 中的 `$breakdown` 變數來引用該維度。</p><p>假設您想要為自由格式表格中的所有「產品名稱」維度項目建立超連結。每個「產品名稱」維度項目均包含「產品 ID」維度的劃分。</p></p>在這種情況下，您可以為每個「產品名稱」維度建立超連結，如此將透過使用「產品 ID」劃分維度的值將使用者導向至產品頁面。 </p><p>將 `$breakdown` 變數新增至您在&#x200B;[!UICONTROL **自訂 URL**] 欄位中指定的自訂 URL 結尾。例如：</p><p>`https://company-name.com/browse/product/$breakdown`</p>將此自訂 URL 套用至您的「產品名稱」維度項目 (其中劃分維度項目的值為「ProductY」和「ProductZ」) 時，產生的超連結如下所示：<br/>`https://company-name.com/browse/product/ProductY` 和<br/>`https://company-name.com/browse/product/ProductZ`</p><p>然後，您將在「[!UICONTROL **劃分維度**]」欄位中選取「產品 ID」維度 </p><p>![在超連結中使用劃分](assets/table-hyperlinks-breakdown.png)</p> |

1. 選取「[!UICONTROL **建立**]」。

   查看自由格式表格的使用者會看到有超連結的維度項目。當您按一下維度項目時，使用者將被帶往個別瀏覽器標籤中的超連結頁面。

   <!-- add screenshot of a table with hyperlinks.-->

1. [儲存專案](/help/analysis-workspace/build-workspace-project/save-projects.md)以儲存您的變更。

## 編輯超連結

您可編輯已在自由格式表格內維度或維度項目建立的超連結。

1. 在 Analysis Workspace 自由格式表格中，執行下列其中一項：

   * **編輯單一維度項目的超連結：**

      1. 開啟維度項目的內容選單。
      1. 從內容選單中，選取「[!UICONTROL **編輯超連結**]」。

     <!-- Do we really need a screenshot? ![Edit hyperlink for a single dimension item](assets/hyperlink-single-edit.png)-->

   * **編輯維度欄中所有維度項目的超連結：**

      1. 從維度欄標題開啟內容選單。
      1. 從內容選單中，選取「**[!UICONTROL 編輯所有維度項目的超連結]**」。

     <!-- Do we really need a screenshot? ![Edit hyperlink for a dimension](assets/hyperlink-dimension-edit.png)-->

1. 從按滑鼠右鍵選單中，選取「[!UICONTROL **編輯所有維度項目的超連結**]」。

   「[!UICONTROL **編輯維度項目的超連結**]」對話框會顯示。

1. 有關編輯超連結的設定選項資訊，請參閱上文「[為一個或多個維度項目建立超連結](#create-hyperlinks-for-one-or-more-dimension-items)」部分中的步驟 3，然後在完成更新後選取「[!UICONTROL **套用**]」。

1. [儲存專案](/help/analysis-workspace/build-workspace-project/save-projects.md)以儲存您的變更。

## 移除超連結

您可以移除已為自由格式表格內維度項目建立的超連結。

>[!NOTE]
>
>在自由格式表中，如果移除包含超連結的維度，則將相同維度新增回自由格式表格時，超連結將不會保留。

若要從維度項目移除超連結：

1. 在 Analysis Workspace 自由格式表格中，執行下列其中一項：

   * **從單一維度項目移除超連結：**

      1. 開啟維度項目的內容選單。
      1. 從內容選單中，選取「[!UICONTROL **移除超連結**]」。
         <!-- Do we really need a screenshot? ![Remove hyperlink from a single dimension item](assets/hyperlink-single-remove.png)-->

   * **移除維度欄內所有維度項目的超連結：**

      1. 從維度欄標題開啟內容選單。
      1. 從內容選單中，選取「**[!UICONTROL 移除所有維度項目的超連結]**」。

     <!-- Do we really need a screenshot? [Remove hyperlink from a dimension](assets/hyperlink-dimension-remove.png)-->



   如果您已選取單一維度項目，則超連結會從單一維度項目中移除。或者，如果您在維度欄標題中選取了維度名稱，則會從所有維度項目中移除。

1. [儲存專案](/help/analysis-workspace/build-workspace-project/save-projects.md)以儲存您的變更。
