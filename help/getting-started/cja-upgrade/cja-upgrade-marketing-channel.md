---
title: 建立 Customer Journey Analytics 的行銷管道衍生欄位
description: 了解如何建立 Customer Journey Analytics 的行銷管道衍生欄位
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 2a74da97-61cb-4c98-949b-3fc428839d70
TQID: https://experienceleague.adobe.com/nwxJ3KEss3SlZxpGB-CW4qDW9QpQqXL1kN-VslhuAVE
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 291
ht-degree: 100%

---

# 建立 Customer Journey Analytics 的行銷管道衍生欄位 {#create-marketing-channel-derived-field}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channel"
>title="建立行銷管道衍生欄位"
>abstract="衍生欄位是在資料視圖中所建立。<br><br>使用預設行銷管道設定只需幾分鐘；建立高度自訂的行銷管道設定可能需要數小時。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

使用 Analytics 來源連接器時，行銷管道資料會透過該連接器流入 Customer Journey Analytics。 行銷管道規則是在傳統 Adobe Analytics 中設定，且部分規則不受支援。 如需了解更多資訊，請參閱「[使用行銷管道維度](/help/use-cases/aa-data/marketing-channels.md)」。

為了在使用 Experience Platform Web SDK 時使用 Customer Journey Analytics 中的行銷管道，您可以使用資料檢視中的衍生欄位為 Customer Journey Analytics 重新建立相同的行銷管道和處理規則。

1. 在 Customer Journey Analytics 中，選取您要新增行銷管道的資料檢視。

1. 在資料檢視中，選取「**[!UICONTROL 元件]**」索引標籤。

1. 在左側邊欄中，選取「**[!UICONTROL 建立派生欄位]**」。

1. 在「**[!UICONTROL 建立衍生欄位]**」對話框中，從下拉式選單中選取「**[!UICONTROL 函數範本]**」。

   ![建立衍生欄位函數範本](assets/derived-field-create.png)

1. 拖曳&#x200B;**[!UICONTROL 行銷管道]**&#x200B;範本至空白畫布上。

1. 自訂每個行銷管道的邏輯，確保管道符合您在 Adob&#x200B;&#x200B;e Analytics 環境中用來識別每個管道的邏輯。

   您可以修改輸出管道名稱或新增邏輯，以識別您組織特有的其他管道。

1. 在右欄指定行銷管道的名稱和說明。

1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

   您新的洐生欄位將會加入「派生欄位 > 容器」中，並作為資料檢視左側邊欄中的結構描述一部分。

{{upgrade-final-step}}
