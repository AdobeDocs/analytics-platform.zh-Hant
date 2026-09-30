---
title: 使用快取結果，以更快在Analysis Workspace中載入
description: 在Analysis Workspace中啟用專案設定，以便快取查詢結果12小時，讓專案立即載入。 隨時重新整理以檢視最新資料。
feature: Workspace Basics
hide: true
exl-id: 6d7b9d34-ec7e-45ec-98cc-0fd4cbfd43d3
role: User
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: a8b1c240-f315-46e3-b813-f545c4279dd1
    internal-label: Workspace basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 80ce27bcff09a23e38054e05329a2a261c8f6562
workflow-type: tm+mt
source-wordcount: '939'
ht-degree: 0%
---

# 在Workspace專案中使用快取結果

>[!CONTEXTUALHELP]
>id="project_cached_results"
>title="使用快取結果以加速載入"
>abstract="啟用後，結果會在使用者首次開啟專案或依排程傳送專案後，立即載入12小時。 在這段時間內開啟專案的任何人都會看到相同的結果，即使資料繼續在背景中流動。 若要載入最新結果，請重新整理個別面板或整個專案。"

您可以設定Analysis Workspace專案在12小時的視窗中顯示快取結果，以便在專案初次載入後，讓任何開啟專案的人立即載入結果。

開啟專案的使用者或排程的專案傳送最初可載入專案。

>[!NOTE]
>
>僅快取查詢結果。 基礎事件資料會照常持續流入Customer Journey Analytics。
>
>若要在快取結果過期之前檢視最新資料，您可以[手動重新整理結果](#manually-refresh-results-on-cached-projects)。

## 瞭解專案中的快取結果

### 結果快取時

首次執行專案時，Analysis Workspace會照常執行查詢，並在12小時的期間內快取結果。 當有人開啟專案或專案針對排程傳送執行時，就會發生這種情況。 例如，如果專案排程在早上6:00傳送，結果會快取到晚上6:00。 每個在早上6:00到下午6:00之間開啟專案的人，都會立即看到結果載入，包括第一個開啟專案的人。

12小時後，快取結果就會過期。 專案的下一個查詢，無論使用者是開啟專案還是排程的傳送，都會以正常速度載入並開始新的12小時視窗。

### 快取哪些結果

Analysis Workspace會快取執行的每個查詢，而非專案的所有可能版本。

當有人變更專案中的查詢時（例如從面板下拉式選單選取專案或套用區段），Analysis Workspace會執行新查詢。 新查詢第一次會以正常速度載入。 之後，結果也會經過快取，以便執行相同查詢的人能立即看到結果。

快取新查詢不會覆寫或使已快取的結果失效。 原始專案檢視會隨人員執行的其他變數一起快取。

>[!BEGINSHADEBOX]

**範例情境**

假設全球促銷活動績效專案包含不同地區的區段，並排程在早上6:00傳遞：

| 時間 | 動作 | 載入速度 |
| --- | --- | --- |
| 上午 6:00 | 排程專案傳遞 | 一般（會快取結果以供日後使用） |
| 上午7:06 | 使用者A開啟專案 | 即時 |
| 上午7:06 | 使用者A套用美洲區段 | 一般（會快取結果以供日後使用） |
| 上午8:01 | 使用者B開啟專案 | 即時 |
| 上午8:01 | 使用者B套用美洲區段 | 即時 |
| 上午8:01 | 使用者B套用EMEA區段 | 一般（會快取結果以供日後使用） |

>[!ENDSHADEBOX]

### 誰會看到快取的結果

快取結果預設會顯示給以下人員：

* 擁有專案的存取權

* 可存取專案中使用的資料檢視

* 在先前已快取的專案中使用相同的查詢引數（例如，他們檢視的專案使用與先前快取專案相同的區段或面板下拉式選取專案）

檢視快取的結果時，您可以透過[手動重新整理結果](#manually-refresh-results-on-cached-projects)來檢視最新的資料。

## 啟用專案的快取結果

任何可以更新專案設定的人都可以啟用快取結果。 這包括專案所有者和擁有專案&#x200B;**[!UICONTROL 編輯原始專案]**&#x200B;角色的任何人。 如需有關專案角色的詳細資訊，請參閱[共用特定專案角色](/help/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role)。

在您想要啟用快取結果以便立即載入的Workspace專案中：

1. 移至&#x200B;**[!UICONTROL 專案]** > **[!UICONTROL 專案資訊與設定]**。
1. 選取&#x200B;**[!UICONTROL 使用快取結果以加速載入]**。
1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

## 在專案中顯示快取結果時進行檢視

顯示快取結果時，時間戳記會顯示在專案頂端。 時間戳記會指定是快取所有結果，還是隻快取部分結果：

* **[!UICONTROL 顯示來自] [_日期與時間的結果_]**：專案中的所有面板都會顯示來自所顯示日期與時間的快取結果。
* **[!UICONTROL 顯示來自] [_日期與時間的部分結果_]**：某些面板顯示來自所顯示日期與時間的快取結果，而其他面板則最近才重新整理。

快取專案上的![時間戳記](assets/project-cache-timestamp.png)

面板也會顯示時間戳記，顯示何時快取結果：

* **[!UICONTROL 顯示來自] [_日期與時間_]**&#x200B;的結果：面板顯示來自所顯示日期與時間的快取結果。

  >[!NOTE]
  >
  >此選項在發行的Alpha階段無法使用。

## 手動重新整理快取專案的結果

您可以在12小時視窗內的任何時間手動重新整理專案的結果，以檢視最新資料。 當您重新整理整個專案時，新的12小時視窗會開始，在該視窗中開啟專案的所有人都會看到重新整理的結果。

在您想要檢視最新資料的Workspace專案中，您可以重新整理整個專案或單一面板的結果。

### 重新整理整個專案的結果

若要載入所有面板的最新結果並啟動新的12小時視窗：

1. 選取專案頂端專案時間戳記旁的&#x200B;**[!UICONTROL 重新整理]** ![重新整理](/help/assets/icons/Refresh.svg)圖示。

### 重新整理單一面板的結果

>[!NOTE]
>
>此選項在發行的Alpha階段無法使用。

若只要載入單一面板的最新結果：

1. 選取面板時間戳記旁的專案頂端的&#x200B;**[!UICONTROL 重新整理]** ![重新整理](/help/assets/icons/Refresh.svg)圖示。

