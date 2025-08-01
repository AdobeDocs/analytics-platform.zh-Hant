---
description: 瞭解如何評論Analysis Workspace中的專案
title: 在專案中新增和管理註解
feature: Workspace Basics
role: User
exl-id: 05f69a1c-31c2-40d8-ae8b-a084169897b1
source-git-commit: 518bebc18611136873fce5c23dd7041afafe1220
workflow-type: tm+mt
source-wordcount: '1857'
ht-degree: 0%

---

# 在專案中新增和管理註解 {#comment-on-projects}

Analysis Workspace中的評論可讓您在Analysis Workspace專案的上下文中分享見解和提出問題。 如此可簡化有關資料的討論，讓對話保持在討論的資料內容中。

>[!NOTE]
>
>您可以在專案層級或組織層級停用在專案上新增和管理註解的功能。 如果您無法依照本節所述新增及管理註解，Customer Journey Analytics管理員或專案所有者已停用此功能。
>
>* **專案：**&#x200B;專案所有者可以停用專案的這項功能，如[建立專案](/help/analysis-workspace/build-workspace-project/create-projects.md)中所述。
>* **組織：** Customer Journey Analytics管理員可以停用組織的這項功能，如[偏好設定](/help/analysis-workspace/user-preferences.md)中所述。

## 檢視評論

您可以從右側邊欄的註解區域或註解徽章（若有的話）檢視註解。

>[!NOTE]
>
>必須先儲存專案，才能在右側邊欄中看到註解區域。 如果專案先前未儲存，您需要[儲存專案](/help/analysis-workspace/build-workspace-project/save-projects.md)才能新增註解。


![在Analysis Workspace中檢視註解](assets/workspace-comments-view.png)

### 在註解區域中檢視註解

在Analysis Workspace專案中所做的所有註解都會顯示在右側邊欄的註解區域中。 現有註解的總數會顯示在註解圖示上。

1. 依預設，當您第一次開啟專案時，Analysis Workspace中每個專案的註解區域都會展開。

   選取專案右側邊欄中的註解區域圖示，以開啟或關閉註解區域。

   ![評論區域已關閉](assets/comments-area-closed.png)

   每個註解都顯示註解張貼當天的時間戳記。 如果註解是在當天發佈，則會顯示當天的時間。 將滑鼠移至白天或時間上，即可顯示發表評論的完整日期和時間。

1. （選擇性）若要搜尋評論區域，請選取搜尋圖示![搜尋圖示](assets/comments-search-icon.png)，然後輸入字詞或片語。 「註解」區域經過篩選，僅包含包含包含該字或片語的註解。

### 在專案中檢視評論徽章

在專案的特定區域[上所做的](#comment-on-a-specific-area-of-the-project)評論具有&#x200B;**評論徽章** ![評論徽章](assets/comment-indicator.svg)，該徽章會顯示在評論所屬的專案區域上。 選取徽章以檢視評論。 選取徽章後，您可以選取註解本身，以在右側邊欄的註解區域中反白註解。

編號會顯示在專案中的每個徽章上，並依照其建立順序排序。 如果在專案的相同區域放入多個註解，徽章會顯示3個點![註解徽章多個](assets/comment-indicator-multiple.svg)。 選取3點徽章以顯示該區域中的所有註解。

<!-- Insert screeshot-->

若要隱藏專案中的所有註解徽章：

1. 在Analysis Workspace中開啟專案後，在Analysis Workspace的右側邊欄中選取評論區域圖示![評論區域圖示](/help/assets/icons/Comment.svg)。

1. 在註解區域底部，啟用選項&#x200B;**[!UICONTROL 隱藏置入的徽章]**。

## 新增註解

您可以新增參考專案特定區域的註解，也可以新增一般註解。

### 對專案特定區域發表評論

若要評論專案的特定區域（例如自由表格中的量度值）：

1. 在Analysis Workspace中開啟專案時，在專案中您要插入註解的區域按一下右鍵。

   所有視覺效果都支援視覺效果標題上的註解徽章，但只有下列視覺效果才支援視覺效果中特定資料點的註解徽章：

   * 自由格式表格
   * 同類群組表格
   * 折線圖

   <!--add screenshot-->

1. 選取&#x200B;**[!UICONTROL 新增註解]**。

1. 在&#x200B;**[!UICONTROL 新註解]**&#x200B;欄位中，指定您的註解。

   註解最多可包含15,000個字元，並可包含基本標籤、超連結、專案符號和編號清單以及表情符號。

1. （選擇性）輸入@符號，然後輸入註解名稱，將註解通知其他人。 如需使用@符號通知其他人的詳細資訊，請參閱[在註解中加入其他人](#include-others-in-a-comment)。

1. 選取「**[!UICONTROL 提交]**」。

   **註解徽章** ![註解徽章](assets/comment-indicator.png)位於您新增註解的Workspace專案區域，如[檢視專案中的註解徽章](#view-comment-badges-in-a-project)所述。 註解也會顯示在右側邊欄的註解區域頂端。

### 新增專案的一般註解

若要在Analysis Workspace中為專案新增註解：

1. 在Analysis Workspace中開啟專案後，在Analysis Workspace的右側邊欄中選取評論區域圖示![評論區域圖示](/help/assets/icons/Comment.svg)。<!-- add screen shot -->

1. 在&#x200B;**[!UICONTROL 新註解]**&#x200B;欄位中，指定您的註解。

   註解最多可包含15,000個字元，並可包含基本標籤、超連結、專案符號和編號清單以及表情符號。

1. （選擇性）輸入@符號，然後輸入註解名稱，將註解通知其他人。 如需使用@符號通知其他人的詳細資訊，請參閱[在註解中加入其他人](#include-others-in-a-comment)。

1. 選取「**[!UICONTROL 提交]**」。

   註解會顯示在註解區域的頂端，如[在註解區域檢視註解](#view-comments-in-the-comments-area)中所述。

## 在評論中包含其他專案

Analysis Workspace中的評論功能可讓您更輕鬆地與他人合作。

當使用@符號在註解中包含人時，請考量下列事項：

* 您加入的人員會根據其Adobe Experience Cloud通知設定收到通知。

  如需詳細資訊，請參閱[接收有關註解的通知](#receive-notifications-about-comments)。

* 您可以在註解中加入組織中的任何人並擁有Customer Journey Analytics的存取權，但這樣做不會自動授予他們編輯專案的存取權。

若要在您的評論中加入其他人：

1. 輸入@符號，然後開始輸入您要包含之人員的名字、姓氏或電子郵件地址。

   ![標籤使用者](assets/comments-tag-user.png)

1. 當人員出現在下拉式功能表中時，請選取其名稱。

## 回複評論

1. 在Analysis Workspace中，開啟您要新增註解的專案。

1. 在Analysis Workspace的右側邊欄中選取評論區域圖示![評論區域圖示](/help/assets/icons/Comment.svg)，然後選取您要回覆之評論旁的&#x200B;**[!UICONTROL 回覆]**。

   若要包含您要回覆的註解文字，並將原始文字包裝在引號標籤中，請選取您要回覆的特定註解或回覆旁的3點圖示，然後選取&#x200B;**[!UICONTROL 引號回覆]**。 引號回覆是指出您的評論所參考之評論或回覆的好方法。

   或

   在產生註解的面板或視覺效果上選取註解圖示，然後選取&#x200B;**[!UICONTROL 回覆]**。

1. 在&#x200B;**[!UICONTROL 新註解]**&#x200B;欄位中，指定您的註解。

   註解最多可包含15,000個字元，並可包含基本標籤、超連結、專案符號和編號清單以及表情符號。

1. （選擇性）輸入@符號，然後輸入註解名稱，將註解通知其他人。 如需使用@符號通知其他人的詳細資訊，請參閱[在註解中加入其他人](#include-others-in-a-comment)。

1. 選取「**[!UICONTROL 提交]**」。

## 接收有關評論的通知

專案所有者和您提到的[特定人員](#include-others-in-a-comment)會根據其Adobe Experience Cloud通知設定收到通知。 依預設，使用者會收到應用程式內通知，可在Customer Journey Analytics中的[Experience Cloud通知](https://experienceleague.adobe.com/zh-hant/docs/core-services/interface/features/account-preferences#view-notifications)圖示![Experience Cloud通知圖示](assets/experience-cloud-notification.svg)中看到。

此外，使用者可以透過訂閱[電子郵件通知](https://experienceleague.adobe.com/zh-hant/docs/core-services/interface/features/account-preferences#subscribe-to-in-app-and-email-notifications)和[訂閱Experience Cloud通知](https://experienceleague.adobe.com/zh-hant/docs/core-services/interface/features/account-preferences#slack)，設定其Slack通知設定來接收電子郵件通知和Slack通知。

## 為現有評論放置徽章

如果右側邊欄的註釋區域中有註釋可用，但專案中尚未有徽章，您可以新增該徽章。

1. 在Analysis Workspace中開啟專案後，在Analysis Workspace的右側邊欄中選取評論區域圖示![評論區域圖示](/help/assets/icons/Comment.svg)。

1. 選取您要放置徽章的評論旁的更多圖示![更多圖示](/help/assets/icons/MoreSmallList.svg)，然後選取&#x200B;**[!UICONTROL 放置徽章]**。

1. 選取您要為現有註解放置徽章的專案區域。

   **註解徽章** ![註解徽章](assets/comment-indicator.png)已放置在您所選取的Workspace專案區域中。 註解也會顯示在右側邊欄的註解區域頂端。

   如需詳細資訊，請參閱[在專案中檢視註解徽章](#view-comment-badges-in-a-project)。

若要移除徽章：

1. 選取您要移除的徽章，然後選取&#x200B;**[!UICONTROL 移除徽章]**。

   徽章已移除，但右側欄的註解區域仍可使用註解。

## 移動現有評論的徽章

您可以移動已放置給現有註解的註解徽章。

1. 在Analysis Workspace中開啟專案後，找到您要移動之評論的徽章。

1. 在徽章上按一下滑鼠右鍵，然後選取&#x200B;**[!UICONTROL 移動位置]**。

1. 選取您要放置徽章的專案區域。

<!-- add section about adding images to comments. will be available at GA. Include that "you can have a maximum of 5 images per comment, and each image can be up to 2 MB." -->

## 複製評論的連結

您可以將連結複製到評論並與他人共用連結。 只有已存取專案的使用者才能透過連結存取專案。

若要複製註解的連結：

1. 在Analysis Workspace中開啟專案後，在Analysis Workspace的右側邊欄中選取評論區域圖示![評論區域圖示](/help/assets/icons/Comment.svg)。

1. 選取您要複製其連結之評論旁的更多圖示![更多圖示](/help/assets/icons/MoreSmallList.svg)，然後選取&#x200B;**[!UICONTROL 複製連結]**。

   連結會複製到您的系統剪貼簿。 您可以在電子郵件或其他型別的訊息中貼上連結。

## 複製註解的文字

您可以複製註解的正文並與他人共用。

複製註解內文：

1. 在Analysis Workspace中開啟專案後，在Analysis Workspace的右側邊欄中選取評論區域圖示![評論區域圖示](/help/assets/icons/Comment.svg)。

1. 選取包含您要複製之文字的註解旁的更多圖示![更多圖示](/help/assets/icons/MoreSmallList.svg)，然後選取&#x200B;**[!UICONTROL 複製內文]**。

   註解的內文會複製到您的系統剪貼簿。

## 喜歡評論

1. 在Analysis Workspace中開啟專案後，在Analysis Workspace的右側邊欄中選取評論區域圖示![評論區域圖示](/help/assets/icons/Comment.svg)。

1. 在您要簽署的註解下選取&#x200B;**[!UICONTROL 贊]**。

## 刪除評論

當您刪除註解時，原始註解及任何回覆或附件也會一併刪除。

已刪除的註解無法復原。

若要刪除註解：

1. 在Analysis Workspace中開啟專案後，在Analysis Workspace的右側邊欄中選取評論區域圖示![評論區域圖示](/help/assets/icons/Comment.svg)。

1. 選取您要刪除的評論旁的更多圖示![更多圖示](/help/assets/icons/MoreSmallList.svg)，然後選取&#x200B;**[!UICONTROL 刪除]**。

1. 再次選取&#x200B;**[!UICONTROL 刪除]**&#x200B;以確認刪除。

## 解決評論

當您解析註釋時，註釋會在註釋區域中標籤為已解析和隱藏。 如果評論有關聯的徽章，則會從專案中移除該徽章。

若要解決註解，請執行下列動作：

1. 在Analysis Workspace中開啟專案後，在Analysis Workspace的右側邊欄中選取評論區域圖示![評論區域圖示](/help/assets/icons/Comment.svg)。

1. 選取您要解析之評論旁的更多圖示![更多圖示](/help/assets/icons/MoreSmallList.svg)，然後選取&#x200B;**[!UICONTROL 解析]**。

1. 再次選取&#x200B;**[!UICONTROL 解析]**&#x200B;以確認。

依預設，已解析的註釋會隱藏在註釋區域中。 若要顯示已解決的註解：

1. 在註解區域中選取篩選圖示，然後取消選取&#x200B;**[!UICONTROL 隱藏已解析的註解]**&#x200B;選項。
