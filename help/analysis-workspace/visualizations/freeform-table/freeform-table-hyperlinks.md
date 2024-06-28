---
title: 在Analysis Workspace的自由格式表格中建立超連結
description: 瞭解如何在Analysis Workspace的自由格式表格中建立維度專案的超連結
feature: Visualizations
role: User
exl-id: 24fc2d24-b8c2-4664-8b9c-beda284f9033
source-git-commit: afa6a3cf8763a2d6419ec859385abc4cf095f214
workflow-type: tm+mt
source-wordcount: '1737'
ht-degree: 1%

---

# 為自由格式表格中的維度建立超連結

您可以建立維度專案的超連結，讓維度專案在Analysis Workspace的自由格式表格中可供點按。

在為以下型別的維度專案建立超連結時，此功能特別有用：

* Dimension具有您要連結之URL值的專案（例如頁面URL維度）

* Dimension包含劃分（其URL值為您要連結至）的專案（例如，具有「頁面URL」維度劃分的「頁面名稱」維度）

* Dimension含有您要連結至URL之值的一部分的專案或劃分（例如，屬於URL一部分的「頁面名稱」維度）

以下是此功能的影片示範：

>[!VIDEO](https://video.tv.adobe.com/v/3430411/?learn=on)

## 建立一或多個維度專案的超連結

為維度專案建立超連結時，請考量下列事項：

* 您建立的超連結會儲存在Analysis Workspace專案內的自由格式表格中。 在另一個表格或其他專案中使用相同的維度或維度專案時，超連結不會持續存在。

* 如果您變更自由表格的資料檢視，只要資料檢視中存在維度，表格中為維度或維度專案建立的任何超連結仍可使用。

* 當您建立超連結時，不會檢查URL是否有效。

  如果您建立具有無效URL的超連結，或您建立參照沒有URL值的維度專案的超連結(直接參照維度專案或使用 `$value` 或 `$breakdown` 變數)，則按一下超連結的使用者會看到錯誤訊息，指出URL無效。

* 為單一維度專案建立的超連結會覆寫在維度上建立的超連結。

* 超連結在中無法運作 [下載的PDF檔案](/help/analysis-workspace/export/download-send.md).

若要建立一或多個維度專案的超連結：

1. 在Analysis Workspace的自由格式表格中，執行下列任一項作業：

   * **為單一維度專案建立超連結：** 以滑鼠右鍵按一下表格中要建立超連結的維度專案，然後選取 [!UICONTROL **建立超連結**].

     ![為單一維度專案建立超連結](assets/hyperlink-single-add.png)

     此 [!UICONTROL **建立超連結**] 對話方塊隨即顯示。 您要建立超連結的維度專案名稱會顯示在對話方塊中。

     ![為單一專案對話方塊建立超連結](assets/hyperlink-dialog-single.png)

   * **為維度欄中的所有維度專案建立超連結：** 在維度欄標題中的維度名稱上按一下滑鼠右鍵，然後選取 [!UICONTROL **為所有維度專案建立超連結**].

     ![建立維度的超連結](assets/hyperlink-multiple-add.png)

     此 [!UICONTROL **為所有維度專案建立超連結**] 對話方塊隨即顯示。 您要建立超連結的維度名稱會顯示在對話方塊中。

     ![建立超連結對話方塊](assets/hyperlink-dialog-multiple.png)

1. 從下列選項中選擇：

   * [!UICONTROL **使用維度專案的值做為URL**]：針對具有URL值的維度專案（例如頁面URL維度）選擇此選項。

     例如，如果您使用頁面URL維度，其中每個維度專案的值都為URL，則選取此選項會建立指向URL的超連結。

   * [!UICONTROL **建立自訂URL**]：指定靜態或動態自訂URL。 選擇此選項可以為沒有URL值的維度專案建立超連結。

     例如，如果您使用「頁面名稱」維度，其中每個維度專案的值是頁面名稱（而非完整URL），則選取此選項可讓您指定超連結以用作維度專案的連結。

     如果您想要為多個維度專案建立動態URL，可以使用 `$value` 和 `$breakdown` 自訂URL中的變數。 如需詳細資訊，請參閱下表。

     若要建立自訂URL，請指定下列資訊：

     | 欄位 | 說明 |
     |---------|----------|
     | [!UICONTROL **自訂URL**] | 指定您要用於超連結的自訂URL。 URL必須以完整限定的URL輸入。 例如︰<https://www.example.com><p>您建立的自訂URL可以是靜態或動態：</p> <ul><li>**靜態URL：** 如果您為個別維度專案建立超連結，靜態URL可能就足夠了。 <p>請考量下列範例：例如，如果您有「頁面名稱」維度專案，您可以建立靜態URL，將使用者連結至您要與頁面名稱建立關聯的特定網頁。</p><p>假設您想要為維度專案清單建立超連結，每個連結都會連結至內部Wiki頁面中檔案內的個別定義。</p><p>您可以為每個維度專案建立靜態URL來達到此目的。 例如：</p><p>https://wiki.internal.company_name/page_name#item_definition</p></li><li>**動態URL：** 如果您要針對多個維度專案或維度欄中的所有維度專案建立超連結，則動態URL可能更實用。 <p>若要讓自訂URL成為動態的，請在URL中加入變數，讓URL可依據維度本身的值或劃分維度的值動態變更。</p><p>使用變數時，任何包含在URL中無效字元的維度專案（例如空格）都會使用URL編碼。</p><p>可使用下列變數： (**注意**：雖然您可以在相同URL中使用這些變數，但分開使用它們可能會比較常見。)</p> <ul><li>**`$value`：** 可讓您將維度專案的值插入您指定的URL中。 <p>以下列案例為例：</p><p>假設您想為自由表格中的所有「頁面名稱」維度專案建立超連結，每個維度專案的值都是網頁URL的一部分。 在此情況下，您可以建構單一自訂URL，以動態方式調整每個維度專案。 </p><p>您可以透過新增 `$value` 變數加到您指定的自訂URL結尾。 例如：</p> <p>https://company-name.com/browse/product#\$value</p><p>當此自訂URL套用至值為「ProductY」和「ProductZ」的「頁面名稱」維度專案時，產生的超連結看起來會像這樣： </p><p>https://company-name.com/browse/product#ProductY</p><p>與</p><p> https://company-name.com/browse/product#ProductZ </p><p>![在超連結中使用值](assets/table-hyperlinks-vaule.png)</p><p>**秘訣**：如果您只新增 `$value` 變數填入「自訂URL」欄位中，其效果與選取 [!UICONTROL **使用維度專案的值**] 選項。</p></li><li>**`$breakdown`：** 可讓您將劃分維度專案的值插入您指定的URL。 這可讓您在根據可能不怎麼好記的劃分維度（例如產品ID或頁面URL維度）建立超連結時，使用報表中具有好記名稱的維度（例如產品名稱維度）。<p>參考劃分維度時，指定維度專案通常只有一個劃分專案。 如果指定的維度專案有多個劃分專案，則會在URL中使用第一個劃分專案的值。 如果未列出任何劃分專案，則URL將無效。 與套用至表格一樣，套用至劃分專案的排序順序也相同。</p><p>您可在「 」中指定劃分維度 [!UICONTROL **劃分維度**] 下方的欄位。</p> <p>請考量以下專案的範例情境 [!UICONTROL **劃分維度**] 下方的欄位。</p></li></ul> |
     | [!UICONTROL **劃分維度（選擇性）**] | 開始輸入您要使用的劃分維度名稱，然後從下拉式清單中選取。 <p>如果您在此欄位中選取劃分維度，您必須使用 `$breakdown` 變數中的資料 [!UICONTROL **自訂URL**] 欄位。</p><p>以下列案例為例：</p><p>假設您想為自由表格中的所有產品名稱維度專案建立超連結。 每個「產品名稱」維度專案都包含「產品ID」維度的劃分。</p></p>在此情況下，您可以使用產品ID劃分維度的值，為每個產品名稱維度建立超連結，將使用者導向至產品頁面。 </p><p>您可以透過新增 `$breakdown` 變數填入至您在中指定的自訂URL結尾 [!UICONTROL **自訂URL**] 欄位。 例如：</p><p>https://company-name.com/browse/product/$breakdown</p><p>當此自訂URL套用至具有劃分維度專案（其值為「ProductY」和「ProductZ」）的產品名稱維度專案時，產生的超連結看起來會像這樣：</p><p>https://company-name.com/browse/product/ProductY</p><p>與</p><p>https://company-name.com/browse/product/ProductZ</p><p>然後，您可以選取「 」中的「產品ID 」維度 [!UICONTROL **劃分維度**] 欄位 </p><p>![在超連結中使用劃分](assets/table-hyperlinks-breakdown.png)</p> |

1. 選取「[!UICONTROL **建立**]」。

   檢視自由表格的使用者會看到超連結維度專案。 按一下維度專案時，使用者會在單獨的瀏覽器標籤中進入超連結頁面。

   <!-- add screenshot of a table with hyperlinks.-->

1. [儲存專案](/help/analysis-workspace/build-workspace-project/save-projects.md) 以儲存變更。

## 編輯超連結

您可以在自由表格中，編輯針對維度或維度專案建立的超連結。

1. 在Analysis Workspace的自由格式表格中，執行下列任一項作業：

   * **編輯單一維度專案的超連結：** 以滑鼠右鍵按一下表格中要編輯超連結的維度專案。

     ![編輯單一維度專案的超連結](assets/hyperlink-single-edit.png)

   * **編輯維度欄中所有維度專案的超連結：** 在維度欄標題中的維度名稱上按一下滑鼠右鍵。

     ![編輯維度的超連結](assets/hyperlink-dimension-edit.png)

1. 選取 [!UICONTROL **編輯超連結**] 在功能表中按一下滑鼠右鍵。

   此 [!UICONTROL **編輯維度專案的超連結**] 對話方塊隨即顯示。

1. 如需有關編輯超連結的組態選項的資訊，請參閱 [建立一或多個維度專案的超連結](#create-hyperlinks-for-one-or-more-dimension-items) 部分，然後選取 [!UICONTROL **套用**] 完成更新時。

1. [儲存專案](/help/analysis-workspace/build-workspace-project/save-projects.md) 以儲存變更。

## 移除超連結

您可以移除為自由表格中的維度專案建立的超連結。

>[!NOTE]
>
>在自由表格中，如果您刪除包含超連結的維度，則在您將相同維度新增回自由表格時，超連結將不會持續存在。

若要從維度專案移除超連結：

1. 在Analysis Workspace的自由格式表格中，執行下列任一項作業：

   * **從單一維度專案移除超連結：** 以滑鼠右鍵按一下表格中您要移除超連結的維度專案。

     ![從單一維度專案移除超連結](assets/hyperlink-single-remove.png)

   * **從維度欄中的所有維度專案移除超連結：** 在維度欄標題中的維度名稱上按一下滑鼠右鍵。

     ![從維度移除超連結](assets/hyperlink-dimension-remove.png)

1. 選取 [!UICONTROL **移除超連結**] 在功能表中按一下滑鼠右鍵。

   超連結會從單一維度專案（如果您選取了單一維度專案）或所有維度專案（如果您在維度欄標題中選取維度名稱）中移除。

1. [儲存專案](/help/analysis-workspace/build-workspace-project/save-projects.md) 以儲存變更。
