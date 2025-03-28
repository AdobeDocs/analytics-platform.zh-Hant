---
title: 建立 Customer Journey Analytics 的行銷管道衍生欄位
description: 瞭解如何為Customer Journey Analytics建立行銷管道衍生的欄位
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 2a74da97-61cb-4c98-949b-3fc428839d70
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 25%

---

# 建立 Customer Journey Analytics 的行銷管道衍生欄位 {#create-marketing-channel-derived-field}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channel"
>title="建立行銷管道衍生欄位"
>abstract="衍生欄位是在資料視圖中建立的。<br><br>使用預設行銷管道設定只需幾分鐘；建立高度自訂的行銷管道設定可能需要數小時。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

使用Analytics來源聯結器時，行銷管道資料會通過該聯結器流入Customer Journey Analytics。 行銷管道規則是在傳統 Adobe Analytics 中設定，且部分規則不受支援。如需詳細資訊，請參閱[使用行銷管道維度](/help/use-cases/aa-data/marketing-channels.md)。

若要在使用Customer Journey Analytics Web SDK時使用Experience Platform中的行銷管道，您可以在資料檢視中使用衍生欄位，為Customer Journey Analytics重新建立相同的行銷管道和處理規則。

1. 在Customer Journey Analytics中，選取您要新增行銷管道的資料檢視。

1. 在資料檢視中，選取&#x200B;**[!UICONTROL 元件]**&#x200B;標籤。

1. 在左側邊欄中選取&#x200B;**[!UICONTROL 建立衍生欄位]**。

1. 在&#x200B;**[!UICONTROL 建立衍生欄位]**&#x200B;對話方塊中，從下拉式功能表中選取&#x200B;**[!UICONTROL 函式範本]**。

   ![建立衍生欄位函式範本](assets/derived-field-create.png)

1. 將&#x200B;**[!UICONTROL 行銷管道]**&#x200B;範本拖曳至空白畫布。

1. 自訂每個行銷管道的邏輯，以確保其符合您在Adobe Analytics環境中用於識別每個管道的邏輯。

   您可以修改輸出管道名稱或新增邏輯以識別組織特定的其他管道。

1. 在右欄，指定行銷管道的名稱和說明。

1. 選取「**[!UICONTROL 儲存]**」。

   您新的衍生欄位會新增至衍生欄位>容器，做為資料檢視左側邊欄中的「結構」欄位的一部分。

{{upgrade-final-step}}
