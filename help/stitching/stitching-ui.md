---
title: 拼接
description: 瞭解如何建立和管理拼接資料集
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hidefromtoc: true
exl-id: 8820a093-e573-45f9-bcd2-0933e21c231b
role: Admin
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 1%

---

# 建立和管理拼接資料集

{{select-package}}

拼接讓管理員可以拼接Customer Journey Analytics中可用資料集的身分。 拼接資料集可提高設定檔表示的準確性，最終獲得更好的分析和報告。

拼接程式可讓您在資料集中定義現有的&#x200B;**永久ID**。 接著，將指定之重播視窗（每日、每週）的永久性識別碼與該資料集可用的最準確&#x200B;**人員ID** （人員或驗證識別碼）拼接。 個人識別碼的範例為電子郵件、電話號碼、CRM ID或儲存在圖表中的其他身分。 如需彙整的詳細資訊，請參閱[概觀](overview.md)。

## 建立

若要啟動彙整作業，請建立一個或多個彙整的資料集。 若要建立拼接資料集：

1. 在頂端列選取&#x200B;**[!UICONTROL **&#x200B;資料管理&#x200B;**]**&#x200B;中的&#x200B;**[!UICONTROL **&#x200B;拼接&#x200B;**]**。

2. 在[!UICONTROL 拼接資料集]畫面中，選取&#x200B;**[!UICONTROL **&#x200B;建立拼接資料集&#x200B;**]**。

   系統會以對話方塊提示您，說明您的責任。

3. 如果您接受這些職責，請選取&#x200B;**[!UICONTROL **&#x200B;繼續&#x200B;**]**。

   >[!NOTE]
   >
   >    如果您選取「**[!UICONTROL **&#x200B;取消&#x200B;**]**」，將無法建立拼接資料集。

4. 在[!UICONTROL 拼接資料集>未命名的拼接資料集]畫面中：

   1. 定義&#x200B;**[!UICONTROL **&#x200B;資料集名稱&#x200B;**]**&#x200B;和（選擇性） **[!UICONTROL **&#x200B;描述&#x200B;**]**，

   2. 從儲存事件資料集的&#x200B;**[!UICONTROL **&#x200B;沙箱&#x200B;**]**&#x200B;清單中選取沙箱。

      ![初始建立畫面](./assets/create-initial.png)

   3. 選取&#x200B;**[!UICONTROL **&#x200B;選取來源資料集&#x200B;**]**&#x200B;按鈕。

      在[!UICONTROL 選取一個資料集以拼接]快顯視窗：

      ![選取一個資料集](./assets/select-one-dataset.png)

      - 選取資料集，然後選取&#x200B;**[!UICONTROL **&#x200B;選取&#x200B;**]**&#x200B;以繼續。

   4. 從&#x200B;**[!UICONTROL **&#x200B;永久ID **]**&#x200B;清單中選取永續性識別碼。

   5. 從&#x200B;**[!UICONTROL **&#x200B;暫時性識別碼&#x200B;**]**&#x200B;清單中選取個人識別碼。

      您會注意到，預覽面板似乎會計算過去七天的飽和率（每個指定識別碼在事件數內有值的次數）。 完成計算後，面板會以顏色視覺化，顯示是否滿足拼接的最低條件（綠色）或未滿足（紅色）。

      ![建立具有穩定速率的拼接資料集](./assets/create-before-experimenting.png)

      最低條件為：

      - 持續性識別碼飽和度：比率>= 95%

      - 個人識別碼飽和度：比率>= 5%

        如果滿足最小條件，則可實驗樣本值。

      - 選取&#x200B;**[!UICONTROL **&#x200B;建立示範拼接ID的&#x200B;**]**。

        在[!UICONTROL 使用範例值]的實驗對話方塊中，會顯示具有[!UICONTROL 時間戳記]、[!UICONTROL 永久ID]、[!UICONTROL 暫時ID]、[!UICONTROL 彙整ID （即時）]、[!UICONTROL 彙整ID （1天重播）]和[!UICONTROL 彙整ID （7天重播）]的範例值的資料表。

            ！[實驗範例值](./assets/experiment-sample-values.png)
            
            1。  輸入**[!UICONTROL **永久ID**]**的值。
            
            2。  選取**[!UICONTROL **重新整理彙整ID**]**，檢視彙整程式對資料集資料的影響。
            
            3。  完成範例值的實驗時，選取**[!UICONTROL **關閉**]**。
        

        返回[!UICONTROL 拼接資料集> _資料集名稱_]&#x200B;畫面：

   6. 從&#x200B;**[!UICONTROL **&#x200B;重播視窗&#x200B;**]**&#x200B;清單中選取重述歷史資料的頻率和期間選項。

      您可以選取預設值&#x200B;**[!UICONTROL ** Previous day， daily **]**&#x200B;或&#x200B;**[!UICONTROL ** Previous 7 days， weekly **]**。

   7. 從&#x200B;**[!UICONTROL **&#x200B;平均每日事件數&#x200B;**]**&#x200B;清單中選取一個值。

   8. 在`0`回填月數`12`中輸入值（介於&#x200B;**[!UICONTROL **&#x200B;到&#x200B;**]**&#x200B;之間）。

   9. 選取&#x200B;**[!UICONTROL **&#x200B;儲存&#x200B;**]**&#x200B;以儲存您拼接的資料集並啟動拼接。

## 檢視狀態

您可以在[!UICONTROL 拼接資料集]清單中檢視拼接狀態。

- 在頂端列選取&#x200B;**[!UICONTROL **&#x200B;資料管理&#x200B;**]**&#x200B;中的&#x200B;**[!UICONTROL **&#x200B;拼接&#x200B;**]**。

  您會看到拼接資料集清單，每個資料集都識別為[!UICONTROL 沙箱]、[!UICONTROL Source資料集]、[!UICONTROL 狀態]、[!UICONTROL 回填狀態]、[!UICONTROL 所有者]以及[!UICONTROL 建立日期]。

  ![拼接資料集概觀](./assets/overview-stitched-datasetts.png)

  [!UICONTROL 狀態]可能的值為：

  | 值 | 說明 |
  |-----|-----|
  | **[!UICONTROL **&#x200B;已排入佇列&#x200B;**]** | 已收到請求，很快就會處理。 |
  | **[!UICONTROL **&#x200B;正在建立&#x200B;**]** | 正在建立資源和新拼接的資料集。 |
  | **[!UICONTROL **&#x200B;拼接進行中&#x200B;**]** | 資源和拼接的資料集存在，拼接正在進行中 |
  | **[!UICONTROL **&#x200B;錯誤&#x200B;**]** | 銜接時發生問題。 可能是結構描述在來源資料集和拼接資料集之間變更、每日數量太大或…… （_**此處需要更多資訊……**_） |

  >[!INFO]
  >
  >    每當狀態變更時，都會傳送通知，其中訊息&#x200B;**[!UICONTROL **&#x200B;資料集&#x200B;_的Stitched資料集_&#x200B;名稱已變更為狀態&#x200B;_的狀態&#x200B;_**]**名稱。


  [!UICONTROL 回填狀態]可以有下列值： 0%、25%、50%、75%或100%。

  您可以選取資訊圖示，以顯示快顯視窗，其中包含所選拼接資料集的詳細資訊。


## 刪除

>[!NOTE]
>
>您只能刪除狀態為[!UICONTROL 拼接進行中]、[!UICONTROL 錯誤]或[!UICONTROL 已排入佇列]的資料集。


若要刪除單一拼接資料集：

- 選取拼接資料集的&#x200B;**[!UICONTROL **...**]**，並從功能表選取&#x200B;**[!UICONTROL **&#x200B;刪除&#x200B;**]**。

  ![刪除拼接的資料集](./assets/delete-stitched-dataset.png)

若要刪除多個拼接資料：

- 使用每個列出資料集開頭的核取方塊，選取多個拼接資料集。

- 從其中一個選取的拼接資料集中選取&#x200B;**[!UICONTROL **...**]**，然後從功能表中選取&#x200B;**[!UICONTROL **&#x200B;刪除&#x200B;**]**。
