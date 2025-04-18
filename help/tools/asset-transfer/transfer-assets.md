---
title: 轉移資產
description: 瞭解如何將元件從一個使用者轉讓給另一個使用者
role: Admin
solution: Customer Journey Analytics
exl-id: c5ed81ea-1d55-4193-9bb1-a2a93ebde91f
source-git-commit: 9f954709a3dde01b4e01581e34aece07fe0256b1
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 0%

---

# 轉移資產

資產轉移工具可讓您將資產的所有權轉移給其他使用者。 Assets可包含專案、區段、日期範圍、計算量度、註解、警報和已排程專案等元件。

Assets通常會與個別擁有者繫結，而在某些情況下，例如區段和計算量度，甚至管理員也無法編輯或共用。 當使用者離開組織或變更其角色時，可能有必要將這些資產的所有權轉移給其他使用者，以確保連續性和適當的存取權。

## 權限

「資產轉移」需要Customer Journey Analytics的產品管理員許可權。

## 轉移資產

1. 在CJA中，導覽至&#x200B;**[!UICONTROL 工具]** > **[!UICONTROL 資產轉移]**。

   ![資產轉移功能表專案](/help/tools/asset-transfer/assets/asset-transfer.png)

1. 在&#x200B;**[!UICONTROL 使用者]**&#x200B;對話方塊中，搜尋並選取您要轉移資產的使用者。

   >[!IMPORTANT]
   >
   >您只能進行1:1傳輸，從一位使用者傳輸到另一位使用者。 不支援一對多或多對一傳輸。


1. 選取使用者後，「轉移資產」選項會顯示在畫面底部。

   ![功能表選項](/help/tools/asset-transfer/assets/after-selection.png)

1. 按一下&#x200B;**[!UICONTROL 轉移資產]**。

1. 在&#x200B;**[!UICONTROL 轉移資產]**&#x200B;畫面上，先選取您要轉移資產的收件者。

1. 現在，請瀏覽左側導覽的每個元件資料夾，以選取要傳輸的資料夾中的個別元件或所有資產。

   >[!NOTE]
   >
   >將資產從管理員轉讓給非管理員不會將收件者升級為管理員。


   >[!NOTE]
   >
   >    傳輸參考其他元件的資產（例如參考其他區段和計算量度的專案）時，專案目前所有者未擁有的元件將只會與收件者共用。 所有其他元件的擁有權將轉移給收件者。

1. 若要選取資料夾中的&#x200B;_所有_&#x200B;資產，請核取表格頂端&#x200B;**[!UICONTROL Name]**&#x200B;旁的方塊。

   ![選取要轉移的資產](/help/tools/asset-transfer/assets/select-assets.png)

1. 完成所有選擇後，按一下右上方的&#x200B;**[!UICONTROL 轉移]**。

1. 出現確認訊息時，按一下&#x200B;**[!UICONTROL 確認]**。

   >[!IMPORTANT]
   >
   >請勿在傳輸期間關閉熒幕，以避免流程中止。 這可確保順暢的傳輸體驗。

## 傳輸結果

傳輸有三種可能的結果：

- **傳輸成功**：「Assets已成功傳輸」。

- **部分成功**：「部分資產已成功轉移。」

- **傳輸失敗**：「無法傳輸資產。 請再試一次。」

## 從Adobe Analytics升級至Customer Journey Analytics期間轉移資產

資產轉移的主要使用案例之一是從Adobe Analytics升級至Customer Journey Analytics期間。

Adobe Analytics中的[元件移轉](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/component-migration)功能可讓您將管理員擁有的專案移轉給其他管理員。 然後會在Customer Journey Analytics中重新建立組成這些專案的所有元件，且收件者管理員會擁有所有這些元件，無論這些元件的建立者為何。

此「資產轉移」工具隨後可讓管理員將元件重新指派給其合法擁有者，無論他們是否為管理員。

>[!IMPORTANT]
>
>雖然您可以使用此工具傳輸元件，但身為管理員的您仍需確保收件者有權存取檢視/使用這些元件所需的資料檢視。 您可以在[Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html)中檢視及指派許可權。

## 匯出至 CSV

「**[!UICONTROL 匯出至CSV]**」選項僅可讓管理員下載顯示為.csv檔案的使用者清單。 它不允許他們將已轉移資產的清單匯出至.csv檔案。

<!---## Unknown users

All previously deleted users appear under one unknown user entry, along with all their orphan components. These components can be transferred to a new recipient. This feature will be available in January.-->
