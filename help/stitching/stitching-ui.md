---
title: 拼接
description: 瞭解如何建立和管理拼接資料集
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hidefromtoc: true
exl-id: 8820a093-e573-45f9-bcd2-0933e21c231b
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 2%

---

# 建立和管理拼接資料集

{{select-package}}

拼接讓管理員可以拼接Customer Journey Analytics中可用資料集的身分。 拼接資料集可提高設定檔表示的準確性，最終獲得更好的分析和報告。

拼接過程允許您定義現有的 **永久ID** 在資料集中。 然後以最準確的方式拼接指定重播期間（每日、每週）的持續識別碼 **暫時ID** （人員或驗證識別碼）可供該資料集使用。 暫時性識別碼的範例為電子郵件、電話號碼、CRM ID或儲存在圖形中的其他身分。 另請參閱 [概觀](overview.md) 以取得關於銜接的詳細資訊。

## 建立

若要啟動彙整作業，請建立一個或多個彙整的資料集。 若要建立拼接資料集：

1. 選取 **[!UICONTROL **&#x200B;拼接&#x200B;**]** 從 **[!UICONTROL **&#x200B;資料管理&#x200B;**]** 在頂端列中。

2. 在 [!UICONTROL 拼接資料集] 熒幕，選取 **[!UICONTROL **&#x200B;建立拼接資料集&#x200B;**]**.

   系統會以對話方塊提示您，說明您的責任。

3. 選取 **[!UICONTROL **&#x200B;繼續&#x200B;**]** 如果您接受這些責任。

   >[!NOTE]
   >
   >    如果您選取 **[!UICONTROL **&#x200B;取消&#x200B;**]**，您無法建立拼接資料集。

4. 在 [!UICONTROL 拼接資料集>未命名的拼接資料集] 畫面：

   1. 定義 **[!UICONTROL **&#x200B;資料集名稱&#x200B;**]** 和（可選） **[!UICONTROL **&#x200B;說明&#x200B;**]**，

   2. 從以下位置選擇沙箱： **[!UICONTROL ** Sandbox **]** 儲存事件資料集的清單。

      ![初始建立畫面](./assets/create-initial.png)

   3. 選取 **[!UICONTROL **&#x200B;選取來源資料集&#x200B;**]** 按鈕。

      在 [!UICONTROL 選取要拼接的資料集] 快顯視窗：

      ![選取一個資料集](./assets/select-one-dataset.png)

      - 選取資料集並選取 **[!UICONTROL **&#x200B;選取&#x200B;**]** 以繼續。

   4. 從中選擇一個持續性識別碼 **[!UICONTROL **&#x200B;永久ID **]** 清單。

   5. 從「 」中選擇暫時性識別碼 **[!UICONTROL **&#x200B;暫時ID **]** 清單。

      您會注意到，預覽面板似乎會計算過去七天的飽和率（每個指定識別碼在事件數內有值的次數）。 完成計算後，面板會以顏色視覺化，顯示是否滿足拼接的最低條件（綠色）或未滿足（紅色）。

      ![使用穩定率建立拼接資料集](./assets/create-before-experimenting.png)

      最低條件為：

      - 持續性識別碼飽和度：比率>= 95%

      - 暫時性識別碼飽和度：速率>= 5%

        如果滿足最小條件，則可實驗樣本值。

      - 選取 **[!UICONTROL **&#x200B;建立示範彙整ID **]**.

        在 [!UICONTROL 使用範例值進行實驗] 對話方塊中，會顯示一個表格，其範例值為 [!UICONTROL timestamp]， [!UICONTROL 永久ID]， [!UICONTROL 暫時ID]， [!UICONTROL 彙整ID （即時）]， [!UICONTROL 彙整ID （1天重播）]、和 [!UICONTROL 彙整ID （7天重播）].

            ![具有樣本值的實驗](./assets/experiment-sample-values.png)
            
            1.  輸入**的值[!UICONTROL **永久ID**]**。
            
            2.  選取**[!UICONTROL **重新整理拼接ID**]**一下以檢視彙整程式對資料集中資料的影響。
            
            3.選取**[!UICONTROL **關閉**]**當您完成範例值的實驗時。
        

        返回 [!UICONTROL 拼接資料集> _資料集名稱_] 畫面：

   6. 選取重述歷史資料的頻率和期間的選項，從 **[!UICONTROL **&#x200B;重新執行視窗&#x200B;**]** 清單。

      您可以在預設值之間選取 **[!UICONTROL **&#x200B;前一天，每天&#x200B;**]** 或 **[!UICONTROL **&#x200B;前7天，每週&#x200B;**]**.

   7. 從中選擇一個值 **[!UICONTROL **&#x200B;每日事件平均數量&#x200B;**]** 清單。

   8. 輸入值(介於 `0` 和 `12`)，在 **[!UICONTROL **&#x200B;要回填的月數&#x200B;**]**.

   9. 選取 **[!UICONTROL **&#x200B;儲存&#x200B;**]** 以儲存您拼接的資料集並啟動拼接。

## 檢視狀態

您可以在下列位置檢視彙整狀態： [!UICONTROL 拼接資料集] 清單。

- 選取 **[!UICONTROL **&#x200B;拼接&#x200B;**]** 從 **[!UICONTROL **&#x200B;資料管理&#x200B;**]** 在頂端列中。

  您會看到拼接資料集清單，每個資料集都以 [!UICONTROL Sandbox]， [!UICONTROL 來源資料集]， [!UICONTROL 狀態]， [!UICONTROL 回填狀態]， [!UICONTROL 所有者]、和 [!UICONTROL 建立日期].

  ![拼接資料集概觀](./assets/overview-stitched-datasetts.png)

  可能的值 [!UICONTROL 狀態] 為：

  | 值 | 解釋 |
  |-----|-----|
  | **[!UICONTROL **&#x200B;已排入佇列&#x200B;**]** | 已收到請求，很快就會處理。 |
  | **[!UICONTROL **&#x200B;正在建立&#x200B;**]** | 正在建立資源和新拼接的資料集。 |
  | **[!UICONTROL **&#x200B;正在拼接&#x200B;**]** | 資源和拼接的資料集存在，拼接正在進行中 |
  | **[!UICONTROL **&#x200B;錯誤&#x200B;**]** | 銜接時發生問題。 可能是結構描述在來源資料集和拼接資料集之間變更，每日數量太大或…… (_**此處需要更多資訊……**_) |

  >[!INFO]
  >
  >    每當狀態變更時，系統都會傳送通知並附上訊息 **[!UICONTROL **&#x200B;拼接的資料集 _資料集名稱_ 已變更為狀態 _狀態名稱&#x200B;_**]**.


  此 [!UICONTROL 回填狀態] 可以有下列值： 0%、25%、50%、75%或100%。

  您可以選取資訊圖示，以顯示快顯視窗，其中包含所選拼接資料集的詳細資訊。


## 刪除

>[!NOTE]
>
>您只能刪除具有狀態的資料集 [!UICONTROL 拼接進行中]， [!UICONTROL 錯誤]，或 [!UICONTROL 已排入佇列].


若要刪除單一拼接資料集：

- 選取 **[!UICONTROL **...**]** 用於拼接的資料集，然後選取 **[!UICONTROL **&#x200B;刪除&#x200B;**]** 功能表中。

  ![刪除拼接的資料集](./assets/delete-stitched-dataset.png)

若要刪除多個拼接資料：

- 使用每個列出資料集開頭的核取方塊，選取多個拼接資料集。

- 選取 **[!UICONTROL **...**]** 從其中一個選取的拼接資料集，然後選取 **[!UICONTROL **&#x200B;刪除&#x200B;**]** 功能表中。
