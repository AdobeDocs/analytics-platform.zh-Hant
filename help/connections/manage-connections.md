---
title: 管理連線
description: 說明如何在Customer Journey Analytics(CJA)中管理與Experience Platform資料集的連線。
mini-toc-levels: 3
source-git-commit: 1daac64168e656ed1145dac4c34d3df52d155e35
workflow-type: tm+mt
source-wordcount: '1445'
ht-degree: 8%

---

# 管理連線

一旦管理員使用者建立了一或多個連線](/help/connections/create-connection.md)，他們就可以在[!UICONTROL 連線]管理器中管理這些連線。 [連線體驗的最新更新在「連線詳細資料」頁面中新增了兩個重要功能，如本頁所述：

* 它可讓您檢查連線資料集和擷取程式&#x200B;**的**&#x200B;狀態。 此狀態檢查可讓您知道資料何時可用，以便前往Analysis Workspace並開始分析。

* 它可讓您&#x200B;**識別因錯誤設定而導致的任何資料差異**。 您缺少行嗎？ 如果是，會遺漏哪些列以及原因？ 您是否在CJA中設定了錯誤連線，且造成資料遺失？

>[!NOTE]
> 2021年8月10日正式推出此功能。

## 連線管理器 {#connections-manager}

連接管理器允許您：

* 查看所有連接，包括所有者、沙箱以及建立和修改它們的時間。
* 檢視連線中的所有資料集。
* 檢查連接的狀態。
* 刪除連線。
* 為連線重新命名。
* 從連線建立資料檢視。

![管理連線](assets/conn-manager.png)

| 設定 | 說明 |
| --- | --- |
| [!UICONTROL 名稱] | 連線的好記名稱。 按一下超連結名稱后，您會進入以下所述的「連線詳細資訊」頁面。 |
| 連線資訊 | 按一下連接名稱旁的資訊表徵圖可查看以下資訊：![查看連接資訊](assets/conn-info.png) |
| 編輯連線 | 按一下連接名稱旁的省略號(...)，然後按一下[!UICONTROL Edit]。![編輯](assets/conn-edit-delete.png) 連線如需詳細資訊，請參閱下方的「編輯連線」。 |
| 刪除連線 | 按一下連接名稱旁的省略號(...)，然後按一下[!UICONTROL Delete]。 下方「刪除連線」標題下的詳細資訊。 |
| 建立資料檢視 | 按一下連接名稱旁的省略號(...)，然後按一下[!UICONTROL 建立資料視圖]。 此動作會根據此連線建立新的資料檢視。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en) |
| [!UICONTROL 資料集] | 屬於連線的資料集。 您可以按一下超連結來檢視連線中的所有資料集。 按一下資料集即會在Adobe Experience Platform的新索引標籤中開啟該資料集。 |
| [!UICONTROL 沙盒] | 此連線從中取得資料集的[Adobe Experience Platform沙箱](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en)。 第一次建立連線時，會選取此沙箱。 無法變更。 |
| [!UICONTROL 擁有者] | 建立連線的人。 |
| [!UICONTROL 匯入資料集] | 可讓您啟用或停用以前稱為「資料串流」的項目。 |
| [!UICONTROL 建立日期] | 首次建立連線的日期。 |
| [!UICONTROL 上次修改] | 上次更新連線的日期。 |

### 刪除連線 {#connections-delete}

只有管理員有權刪除連線。 非管理員不會顯示此動作。

1. 按一下連接名稱旁的省略號(...)。
1. 按一下[!UICONTROL 刪除]。

在[!UICONTROL Customer Journey Analytics]中刪除連接時，將顯示一條錯誤消息，指明：

* 根據已刪除連線建立的任何資料檢視都無法再運作。
* 同樣地，如果有任何 Analysis Workspace 專案需仰賴所刪除連線中的資料檢視，也將停止運作。

[進一](/help/getting-started/cja-deletion.md) 步了解刪除含意。

### 搜尋連線或資料集

您可以使用頂端的搜尋列，在[!UICONTROL 連線]標題下搜尋連線。

### 排序連線

您可以按一下每個欄標題，然後依序排序或依序排序連線。

## 「連接詳細資訊」頁 {#connection-detail}

新的「連接詳細資訊」頁為您提供了連接狀態的非常詳細的視圖。

這可提供以下功能：

* 檢查連線資料集和擷取程式的狀態。
* 識別導致跳過或刪除記錄的配置問題。
* 查看資料何時可用於報告。

以下是說明的介面工具集和設定：

![查看連接詳細資訊](assets/conn-details.png)

| 介面工具集/設定 | 說明 |
| --- | --- |
| 資料集選取器 | 可讓您選取連線中的一或所有資料集。 無法多選資料集。 預設為[!UICONTROL 所有資料集]。 |
| 日曆/日期範圍 | 日期範圍會指出您新增資料至連線的時間。 包含所有標準日曆預設集。 您可以自訂日期範圍，但下拉式清單中不會顯示自訂日期範圍。 |
| [!UICONTROL 記錄可] 用介面工具集 | 代表可用於報告的行總數，**適用於整個連接**。 此計數與任何日曆設定無關。 如果您從資料集選取器選取資料集，或在表格中選取資料集，資料集就會變更。 （請注意，新增資料後，會延遲1到2小時，才會顯示在報表中。） |
|  量度Widget | 針對您選取的資料集和日期範圍，摘要新增/略過/刪除的記錄，以及新增的批次數&#x200B;**。** |
| [!UICONTROL 記錄] 添加的Widget | 指出在選取的時段內，針對您選取的資料集和日期範圍&#x200B;**新增了多少列。**&#x200B;每10分鐘更新一次。 |
| [!UICONTROL 記錄略] 過widget | 針對您選取的資料集和日期範圍&#x200B;**，指出在選取的時段內已略過多少列。**&#x200B;略過記錄的原因包括：遺失時間戳記、遺失人員ID等。 每10分鐘更新一次。 |
| [!UICONTROL 刪除的記] 錄Widget | 指出在所選時段內刪除了多少行， **代表您已選擇的資料集和日期範圍**。 例如，可能有人刪除了Experience Platform中的資料集。 每10分鐘更新一次。 |
| 資料集搜尋方塊 | 您可以依資料集名稱或[!UICONTROL 資料集ID]來搜尋。 |
| [!UICONTROL 資料集] | 顯示屬於連線的資料集。 您可以按一下超連結來檢視連線中的所有資料集。 |
| [!UICONTROL 資料集 ID] | 此ID由Adobe Experience Platform自動產生。 |
| [!UICONTROL 批次] | 指出已新增多少個資料批次至此資料集。 |
| [!UICONTROL 上次新增時間] | 顯示上次新增批次至此資料集的時間戳記。 |
| [!UICONTROL 資料集類型] | 此資料集的資料集類型可以是[!UICONTROL Event]、[!UICONTROL Lookup]或[!UICONTROL Profile]。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#configure-dataset) |
| 結構 | 此連線中資料集所根據的Adobe Experience Platform結構。 |
| **連線層級的右側邊欄** |  |
| [!UICONTROL 重新整理] | 刷新連接，以便反映最近添加的記錄。 |
| [!UICONTROL 刪除] | 刪除此連接。 |
| [!UICONTROL 建立資料檢視] | 根據此連線建立新資料檢視。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en) |
| [!UICONTROL 連線名稱] | 顯示連接的易記名稱。 |
| [!UICONTROL 連接說明] | 顯示更詳細的說明，以理想地描述此連接的用途。 |
| [!UICONTROL 人員 ID] | 顯示Experience Platform中資料集結構中定義的身分。 這是您在建立連線期間選擇的[!UICONTROL 人員ID]。 如果您建立的連線包含具有不同ID的資料集，報表會反映這一點。 若要真正合併資料集，您需要使用相同的[!UICONTROL 人員ID]。 |
| [!UICONTROL 沙盒] | 此連線從中取得資料集的[Adobe Experience Platform沙箱](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en)。第一次建立連線時，會選取此沙箱。 無法變更。 |
| [!UICONTROL 連線 ID] | 此ID是系統在Adobe Experience Platform中產生。 |
| [!UICONTROL IMS 組織 ID] | 與您布建的Experience Cloud公司相關聯的[組織ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en)。 先前稱為「登入公司」。 |
| [!UICONTROL 使用連線的資料檢視] | 列出使用此連接的所有資料視圖。 |
| [!UICONTROL 匯入新資料] | 指出是否應將新批次資料新增至歷史（回填）資料。 |
| **資料集層級的右側邊欄** |  |
| [!UICONTROL 資料集說明] | 說明此連線中每個資料集的參數。 |
| [!UICONTROL 可用的紀錄] | 代表透過日曆選取的特定時段內，此資料集內嵌的總列數。 新增資料後，就不會延遲讓資料顯示在報表中。 (例外情況是，當您建立全新連線時，會出現[延遲](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#3.-getting-data-into-customer-journey-analytics)。 |
| [!UICONTROL 新增的記錄] | 所選時段內新增了多少列。 |
| [!UICONTROL 略過的記錄] | 在選取的時段內，擷取期間已略過多少列。 |
| [!UICONTROL 記錄跳過的錯誤] | 此處會指出記錄被略過的原因。 可能包括遺失時間戳記、遺失人員ID等。 |
| [!UICONTROL 擷取的批次] | 此資料集中新增了多少個資料批次。 |
| [!UICONTROL 上次新增時間] | 上次添加批時。 |
| [!UICONTROL 資料集類型] | [!UICONTROL Event]、[!UICONTROL Lookup]或[!UICONTROL Profile]。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#configure-dataset) |
| [!UICONTROL 結構] | 此資料集所依據的Adobe Experience Platform結構。 |
| [!UICONTROL 資料集 ID] | 此ID是系統在Adobe Experience Platform中產生。 |
| [!UICONTROL 回填資料] | 追蹤回填（歷史）資料的狀態有3種：[!UICONTROL 在隊列]中，[!UICONTROL 正在進行]（已指示進度百分比），和[!UICONTROL 完成]。 |

### 編輯連線

可讓管理員編輯連線。 選擇連接，然後按一下「編輯連接」([!UICONTROL Edit Connection])以訪問此對話框。 您可以在此執行下列動作：

* 開始和停止匯入新資料。 此程式先前稱為「資料串流」。
* 為連線重新命名。
