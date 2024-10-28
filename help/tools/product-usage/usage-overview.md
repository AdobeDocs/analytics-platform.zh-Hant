---
title: 產品使用概述
description: 檢視有關貴組織如何使用Customer Journey Analytics的深入分析和報表。
source-git-commit: 7d22c512e8e96963b288567704d2245e64411b10
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 6%

---

# 產品使用概述

{{release-limited-testing}}

產品使用情況讓貴組織能夠檢視有關貴組織如何使用Customer Journey Analytics的分析資料。 它適用於使用Customer Journey Analytics的所有組織。 下列Adobe Experience Platform元件啟用後，系統會自動為您建立和連結。 這些元件均為系統擁有、唯讀，且無法編輯。

* Adobe Experience Platform中的結構描述
* Adobe Experience Platform中的資料集
* Customer Journey Analytics中的連線
* Customer Journey Analytics中的資料檢視

啟用後，所有資料收集和設定都會自動為您設定。 每當使用者在Analysis Workspace中執行動作時，該動作就會受到追蹤並可用於報表。

>[!IMPORTANT]
>
>此功能會計入Adobe Experience Platform中的合約列限制。 在啟用此功能之前，請確定您的組織可以容納此功能產生的資料。

## 可用維度

當您啟用產品使用時，可使用下列維度。 如果您想要變更任何維度設定，請建立系統擁有的資料檢視的復本，並在Analysis Workspace中使用複製的資料檢視。

| 維度 | 說明 |
| --- | --- |
| 動作名稱 | 使用者採取的動作型別。 您可以在資料檢視設定中建立副本，將此維度作為任何需要的量度使用。 |
| 使用的歸因模型 | 元件使用的歸因模型型別。 |
| 元件 | 包含元件型別和元件名稱的衍生欄位。 |
| 元件類型 | 新增、移除或修改的元件型別。 |
| 登入使用者 | 執行此動作的使用者。 |
| 使用的面板 | 新增、移除或修改元件的面板。 |
| 專案名稱 | 專案的易記名稱。 |
| 專案類型 | 專案型別。 |
| 使用者 ID | 觸發事件的使用者ID。 |
| 使用的視覺效果 | 新增、移除或修改的視覺效果。 |

僅開啟或檢視專案時，產品使用情況不會追蹤個別專案元件。 但是，將會追蹤開啟專案的使用者動作。
