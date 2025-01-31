---
title: 在自由格式表格中建立超連結
description: 瞭解如何在Analysis Workspace的自由格式表格中建立維度專案的超連結
feature: Visualizations
role: User
exl-id: 24fc2d24-b8c2-4664-8b9c-beda284f9033
source-git-commit: 4bf8c616965718426efe880865acb0e5054b6a31
workflow-type: tm+mt
source-wordcount: '1607'
ht-degree: 1%

---

# 在自由格式表格中建立超連結

您可以建立維度專案的超連結，讓維度專案在Analysis Workspace的自由格式表格中可供點按。

在為以下型別的維度專案建立超連結時，此功能特別有用：

* Dimension具有URL值的專案（例如頁面URL維度）。

* 包含具有URL值的劃分的Dimension專案（例如，具有「頁面URL」維度劃分的「頁面名稱」維度）。

* Dimension其值屬於URL的專案或劃分（例如，屬於URL的「頁面名稱」維度）。


>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [在自由格式表格中建立超連結](https://video.tv.adobe.com/v/3430411/?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]


## 建立超連結

當您建立一或多個維度專案的超連結時，請考量下列事項：

* 您建立的超連結會儲存在Analysis Workspace專案內的自由格式表格中。 在另一個表格或其他專案中使用相同的維度或維度專案時，超連結不會持續存在。

* 如果您變更自由表格的資料檢視，表格中為維度或維度專案建立的任何超連結仍然可用。 此功能假設維度仍存在於資料檢視中。

* 當您建立超連結時，不會檢查URL是否有效。 如果您

   * 建立具有無效URL的超連結，或
   * 建立參照沒有URL值的維度專案的超連結（直接參照維度專案或使用`$value`或`$breakdown`變數），

  然後按一下超連結的使用者會看到一則錯誤訊息，指出URL無效。

* 為單一維度專案建立的超連結會覆寫在維度上建立的超連結。

* 超連結在[下載的PDF檔案](/help/analysis-workspace/export/download-send.md)中無法運作。

若要建立一或多個維度專案的超連結：

1. 在Analysis Workspace的自由格式表格中，執行下列任一項作業：

   * **為單一維度專案建立超連結：**&#x200B;在您要為其建立超連結的表格中的維度專案上按一下滑鼠右鍵，然後選取&#x200B;[!UICONTROL **建立超連結**]。

      1. 開啟維度專案的內容功能表。
      1. 從內容功能表選取&#x200B;[!UICONTROL **建立超連結**]。

         顯示&#x200B;[!UICONTROL **建立超連結**]&#x200B;對話方塊。 您要建立超連結的維度專案名稱會顯示在對話方塊中。

         ![為單一專案對話方塊建立超連結](assets/hyperlink-dialog-single.png)

   * **為維度欄中的所有維度專案建立超連結：**&#x200B;在維度欄標題中的維度名稱上按一下滑鼠右鍵，然後選取&#x200B;[!UICONTROL **為所有維度專案建立超連結**]。

      1. 從維度欄標題開啟內容功能表。
      1. 從內容功能表選取&#x200B;[!UICONTROL **為所有維度專案建立超連結**]。

         <!-- Do we really need a screenshot ![Create hyperlink for a dimension](assets/hyperlink-multiple-add.png) -->

         顯示&#x200B;[!UICONTROL **為所有維度專案建立超連結**]&#x200B;對話方塊。 您要建立超連結的維度名稱會顯示在對話方塊中。

         ![建立超連結對話方塊](assets/hyperlink-dialog-multiple.png)

1. 從下列選項中選擇：

   * [!UICONTROL **使用維度專案的值做為URL**]：請為具有URL值的維度專案（例如頁面URL維度）選擇此選項。

     例如，如果您使用頁面URL維度，其中每個維度專案的值都為URL，則選取此選項會建立指向URL的超連結。

   * [!UICONTROL **建立自訂URL**]：請指定靜態或動態自訂URL。 選擇此選項可以為沒有URL值的維度專案建立超連結。

     例如：您使用頁面名稱維度，其中每個維度專案的值是頁面名稱（而非完整URL）。 然後選取此選項，以指定超連結作為維度專案的連結。

     如果您想要為多個維度專案建立動態URL，可以在自訂URL中使用`$value`和`$breakdown`變數。 如需詳細資訊，請參閱下表。

     若要建立自訂URL，請指定下列資訊：

     | 欄位 | 說明 |
     |---------|----------|
     | [!UICONTROL **自訂URL**] | 指定您要用於超連結的自訂URL。 URL必須以完整限定的URL輸入。 例如︰<https://www.example.com><p>您建立的自訂URL可以是靜態或動態：</p> <ul><li>**靜態URL：**&#x200B;您可以為單一維度專案或所有維度專案指定靜態URL，讓這些專案連結至相同的URL。 例如︰`https://wiki.internal.company_name/page_name#item_definition`</p></li><li>**動態URL：**&#x200B;如果您想要為多個維度專案或維度欄中的所有維度專案建立唯一的超連結，可以建立動態URL。<p>若要讓自訂URL成為動態的，請在URL中加入變數，以根據維度的值或劃分維度的值變更URL。</p><p>使用變數時，任何包含在URL中無效字元的維度專案（例如空格）都會使用URL編碼。</p><p>下列變數可供使用： （**注意**：雖然您可以在相同的URL中使用這些變數，但比較常見的是分別使用它們。）</p> <ul><li>**`$value`：**&#x200B;可讓您將維度專案的值插入您指定的URL。 <p>假設您想為自由表格中的所有「頁面名稱」維度專案建立超連結，每個維度專案的值都是網頁URL的一部分。 在此情況下，您可以建構單一自訂URL，以動態方式調整每個維度專案。 <br/>例如：`https://company-name.com/browse/product#\$value`</p><p>當此自訂URL套用至值為「ProductY」和「ProductZ」的「頁面名稱」維度專案時，產生的超連結看起來會像這樣： <br/>`https://company-name.com/browse/product#ProductY`和<br/>`https://company-name.com/browse/product#ProductZ` </p><p>![在超連結中使用值](assets/table-hyperlinks-vaule.png)</p><p>**提示**：僅將`$value`變數新增至「自訂URL」欄位，等於在建立URL時選取&#x200B;[!UICONTROL **使用維度專案的值**]&#x200B;選項。</p></li><li>**`$breakdown`：**&#x200B;可讓您將劃分維度專案的值插入您指定的URL。 透過`$breakdown`，您可以在報表中使用具有好記名稱的維度（例如產品名稱維度）。 而且根據可能不怎麼好記的劃分維度（例如產品ID或頁面URL維度）產生超連結。<p>參考劃分維度時，指定維度專案通常只有一個劃分專案。 如果指定的維度專案有多個劃分專案，則會在URL中使用第一個劃分專案的值。 如果未列出任何劃分專案，則URL無效。 與套用至表格一樣，套用至劃分專案的排序順序也相同。</p><p>您在下面的&#x200B;[!UICONTROL **劃分維度**]&#x200B;欄位中指定劃分維度。</p> <p>請考量以下&#x200B;[!UICONTROL **劃分維度**]&#x200B;欄位中描述的範例案例。</p></li></ul> |
     | [!UICONTROL **劃分維度（選擇性）**] | 開始輸入您要使用的劃分維度名稱，然後從下拉式清單中選取。 <p>如果您在此欄位中選取劃分維度，您必須使用您在&#x200B;[!UICONTROL **自訂URL**]&#x200B;欄位中指定的URL中的`$breakdown`變數來參照它。</p><p>假設您想為自由表格中的所有產品名稱維度專案建立超連結。 每個「產品名稱」維度專案都包含「產品ID」維度的劃分。</p></p>在此情況下，您可以使用產品ID劃分維度的值，為每個產品名稱維度建立超連結，將使用者導向至產品頁面。 </p><p>將`$breakdown`變數新增至您在&#x200B;[!UICONTROL **自訂URL**]&#x200B;欄位中指定的自訂URL結尾。 例如：</p><p>`https://company-name.com/browse/product/$breakdown`</p>將此自訂URL套用至您的產品名稱維度專案（具有劃分維度專案的值為「ProductY」和「ProductZ」）時，產生的超連結看起來會像這樣：<br/>`https://company-name.com/browse/product/ProductY`和<br/>`https://company-name.com/browse/product/ProductZ`</p><p>您接著可以在&#x200B;[!UICONTROL **劃分維度**]&#x200B;欄位中選取產品識別碼維度 </p><p>![在超連結中使用劃分](assets/table-hyperlinks-breakdown.png)</p> |

1. 選取&#x200B;[!UICONTROL **建立**]。

   檢視自由表格的使用者會看到超連結維度專案。 按一下維度專案時，使用者會在單獨的瀏覽器標籤中進入超連結頁面。

   <!-- add screenshot of a table with hyperlinks.-->

1. [儲存專案](/help/analysis-workspace/build-workspace-project/save-projects.md)以儲存您的變更。

## 編輯超連結

您可以在自由表格中，編輯針對維度或維度專案建立的超連結。

1. 在Analysis Workspace的自由格式表格中，執行下列任一項作業：

   * **編輯單一維度專案的超連結：**

      1. 開啟維度專案的內容功能表。
      1. 從內容功能表選取&#x200B;[!UICONTROL **編輯超連結**]。

     <!-- Do we really need a screenshot? ![Edit hyperlink for a single dimension item](assets/hyperlink-single-edit.png)-->

   * **編輯維度資料行中所有維度專案的超連結：**

      1. 從維度欄標題開啟內容功能表。
      1. 從內容功能表選取&#x200B;**[!UICONTROL 編輯所有維度專案的超連結]**。

     <!-- Do we really need a screenshot? ![Edit hyperlink for a dimension](assets/hyperlink-dimension-edit.png)-->

1. 從滑鼠右鍵功能表中選取&#x200B;[!UICONTROL **編輯所有維度專案的超連結**]。

   顯示&#x200B;[!UICONTROL **維度專案**]&#x200B;的「編輯超連結」對話方塊。

1. 如需有關編輯超連結的組態選項的資訊，請參閱以上[建立一或多個維度專案的超連結](#create-hyperlinks-for-one-or-more-dimension-items)區段中的步驟3，然後在完成更新時選取&#x200B;[!UICONTROL **套用**]。

1. [儲存專案](/help/analysis-workspace/build-workspace-project/save-projects.md)以儲存您的變更。

## 移除超連結

您可以移除為自由表格中的維度專案建立的超連結。

>[!NOTE]
>
>在自由表格中，如果您刪除包含超連結的維度，則在您將相同維度新增回自由表格時，超連結不會持續存在。

若要從維度專案移除超連結：

1. 在Analysis Workspace的自由格式表格中，執行下列任一項作業：

   * **從單一維度專案移除超連結：**

      1. 開啟維度專案的內容功能表。
      1. 從內容功能表中選取&#x200B;[!UICONTROL **移除超連結**]。
         <!-- Do we really need a screenshot? ![Remove hyperlink from a single dimension item](assets/hyperlink-single-remove.png)-->

   * **從維度資料行中的所有維度專案移除超連結：**

      1. 從維度欄標題開啟內容功能表。
      1. 從內容功能表中選取&#x200B;**[!UICONTROL 移除所有維度專案的超連結]**。

     <!-- Do we really need a screenshot? [Remove hyperlink from a dimension](assets/hyperlink-dimension-remove.png)-->



   如果您選取單一維度專案，則會從單一維度專案中移除超連結。 或者，如果您在維度欄標題中選取維度名稱，則從所有維度專案中選取。

1. [儲存專案](/help/analysis-workspace/build-workspace-project/save-projects.md)以儲存您的變更。
