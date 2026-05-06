---
title: Data Mirror考量事項
description: 瞭解當您想要在Data Warehouse原生解決方案和Customer Journey Analytics之間同步資料時，需要考慮的其他事項。
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
hide: true
source-git-commit: 19351a7155eda77d1768b486c7e39dcf7cdba935
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 1%

---

# Experience Platform Data Mirror考量事項

本文介紹設定Data Mirror資料集時應考量的因素。

## 新增資料行至來源資料表

在啟用CDC的資料映象資料集中，將新欄新增到來源表格時，該變更可能會觸發所有現有列的更新。 這些更新會透過CDC以變更形式處理，CDC會：

* 從成本的角度來看，其行為可能像是完整表格重寫。
* 可以大幅增加擷取量，尤其是任何未來的&#x200B;*變更乘數*&#x200B;定價（例如，合併作業可能會以較高的費率收費）。

來源表格中資料行的建議策略：

* 請確認一開始已定義大部分相關欄（如果不是全部的話）。
* 對應您一開始可能認為需要的每個欄。

此策略：

* 避免之後昂貴的結構描述演化（新增欄時的大量更新）。
* 保持變更磁碟區比稍後新增或修改資料行時更可預測。
* 由於資料倉儲可能會將所有欄解譯為更新，因此外部資料庫端可能會產生一些額外的計算成本。

若要處理外部資料倉儲表格中的新欄，請執行下列步驟：

1. 使用新增的欄建立新結構描述。
1. 設定將資料匯入的新來源聯結器。
1. 正確載入回填。
1. 日後使用CDC變更。

此方法可將對雙方的影響降至最低。

## Privacy Service

由於隱私權請求與資料的結構不同，因此非關聯式結構描述目前處理隱私權請求的方式必須相同，才會發生隱私權請求。

在資料集中鏡射的資料來自以關聯式結構為基礎的外部資料，這些資料會成為Adobe生態系統的一部分，而且可以透過多種方式共用。 例如，透過對象發佈。

因此，隱私權請求不應僅限於映象的資料集，也應涉及外部資料庫中來源資料的更新。

## 衛生行為

衛生服務在&#x200B;*主要身分*&#x200B;上運作，但映象的外部資料庫中的資料表有&#x200B;*主要金鑰*，而非主要身分。

主要身分和主要金鑰之間差異的後果是，衛生刪除無法直接針對關聯式表格執行。 因此，您必須：

* 在資料倉儲解決方案中，刪除其來源表格中的資料，並確保刪除作業透過CDC （或手動變更欄）進行。
* 針對任何包含身分資訊的下游XDM型資料集（例如：Customer Journey Analytics檢視、Real-Time Customer Data Platform資料集、Adobe Journey Optimizer特定資料集等），將衛生和隱私權請求提交至Adobe。

主要身分和主要金鑰之間的差異引入了共同責任模式：

* 出現身分時，Adobe會處理衛生。
* 作為客戶，您有責任將來源資料庫中自己的衛生程式與提交給Adobe的衛生請求進行對應。

## 治理差異

在XDM [結構描述](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/schema/composition)和基礎概念（例如[欄位群組](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/schema/composition#field-group)）中，欄位群組中定義的[欄位](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/schema/composition#field)會將其標籤傳播到使用該欄位群組的所有資料集。 例如，欄位群組`identities`中的電子郵件欄位`emailID`在所有使用欄位群組`identities`的資料集中標籤為相同。

在關聯式結構描述中，欄名稱是獨立的。 資料表`customers`中名為`email`的資料行與資料表`prospects`中名為`email`的資料行獨立且不同。 此行為表示標籤（例如DULE使用標籤、原則）必須個別套用至映象資料集中的欄位。 根據上述範例，您需要將標籤同時套用至`customers`資料集中的`email`欄位和`prospects`資料集中的`email`欄位。

治理差異的影響如下：

* 更多手動控管和設定功能適合客戶使用。
* 您可能需要明確的指引，因此您不會認為透過欄位群組進行一次性標籤足以進行適當治理。
