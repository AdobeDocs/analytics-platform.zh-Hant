---
title: 建立Customer Journey Analytics的行銷管道衍生欄位
description: 瞭解如何建立行銷管道衍生的欄位以供Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 1e4c14334da54a5a6e4a0f36b3538c6e4d1a0b6f
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 5%

---

# 建立Customer Journey Analytics的行銷管道衍生欄位

>[!NOTE]
> 
>必須先完成所有先前的升級步驟，才能依照本頁面的步驟操作。 您可以依照[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)操作，也可以依照[Adobe Analytics為您的組織動態產生的升級步驟操作，以Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。
>
>完成此頁面上的步驟後，請繼續依照建議的升級步驟或動態產生的升級步驟操作。

使用Analytics來源聯結器時，行銷管道資料會通過該聯結器流入Customer Journey Analytics。 行銷管道規則是在傳統 Adobe Analytics 中設定，且部分規則不受支援。如需詳細資訊，請參閱[使用行銷管道維度](/help/use-cases/aa-data/marketing-channels.md)。

若要在使用Experience Platform Web SDK時，在Customer Journey Analytics中使用行銷管道，您可以在資料檢視中使用衍生欄位，為Customer Journey Analytics重新建立相同的行銷管道和處理規則。

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

