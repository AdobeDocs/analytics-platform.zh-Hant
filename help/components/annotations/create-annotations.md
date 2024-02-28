---
title: 建立註解
description: 如何在 Workspace 中建立註解。
feature: Components
exl-id: 68fef9b3-dc47-4e56-bea6-d1c4c39fb51b
role: User, Admin
source-git-commit: e1815cad331b47b281f61d427ef342ea3b5b5d87
workflow-type: ht
source-wordcount: '701'
ht-degree: 100%

---

# 建立註解

根據預設，只有管理員才能建立註解。使用者有權檢視註解，就像檢視其他 Analytics 元件一樣 (例如篩選器、計算量度等)。

但是，管理員可以透過 [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/analytics-tools.html) 將「[!UICONTROL 註解建立]」權限 (Analytics 工具) 授予使用者。

1. 有幾種方法可以開始建立註解：

| 建立方法 | 詳細資料 |
| --- | --- |
| **前往「[!UICONTROL 元件]」>「[!UICONTROL 註解]」。** | 註解管理員頁面隨即開啟。 按一下[!UICONTROL 建立新註解]，[!UICONTROL 註解產生器]隨即開啟。 |
| **以滑鼠右鍵按一下表格上的點。** | 隨即開啟[!UICONTROL 註解產生器]。 請注意，根據預設，以這種方式建立的註解只會出現在其建立所在的專案中。 但是您可將這些註解提供給所有專案使用。 也請注意，系統已填入日期及任何量度等。<p>![](assets/annotate-table.png) |
| **以滑鼠右鍵按一下[!UICONTROL 折線]圖中的點。** | 隨即開啟[!UICONTROL 註解產生器]。 請注意，根據預設，以這種方式建立的註解只會出現在其建立所在的專案中。 但是您可將這些註解提供給所有專案使用。 也請注意，系統已填入日期及任何量度等。<p>![](assets/annotate-line.png) |
| **在 Workspace 中，前往[!UICONTROL 元件] > [!UICONTROL 建立註解]。** | 隨即開啟[!UICONTROL 註解產生器]。 |
| **使用此快速鍵**&#x200B;來開啟註解產生器：(PC) `ctrl` `shift` + o，(Mac) `shift` + `command` + o | 請注意，使用快速鍵建立註解時，您會為目前日期建立單日註解，而不會預先選取任何範圍 (量度或維度)。 |
| **使用 [Customer Journey Analytics 註解 API](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)** | Customer Journey Analytics 註解 API 可讓您透過 Adobe Developer，以程式設計方式建立、更新或擷取註解。這些 API 使用 Adob&#x200B;&#x200B;e 在產品 UI 中使用的相同資料和方法。 |

{style="table-layout:auto"}

1. 填入[!UICONTROL 註解產生器]元素。

   ![註解詳細資料視窗，顯示下一節中說明的欄位和選項。](assets/ann-builder.png)

   | 元素 | 說明 |
   | --- | --- |
   | [!UICONTROL 標題] | 為註解命名，例如，「紀念日」 |
   | [!UICONTROL 說明] | (選用) 提供註解的說明，例如，「美國的國定假日」。 |
   | [!UICONTROL 標記] | (選用) 透過建立或套用標記來編排註解。 |
   | [!UICONTROL 套用的日期] | 選取需要出席的活動日期或日期範圍，使註解能夠顯示。 |
   | [!UICONTROL 顏色] | 在註解上套用顏色。註解會顯示在所選取顏色的專案中。顏色可用於將註解分類，例如，國定假日、外部活動、追蹤問題等。 |
   | [!UICONTROL 範圍] | (選用) 拖放會觸發註解的量度。接著，拖放任何作為篩選器的維度或篩選器 (即註解將藉以顯示)。如果您不指定範圍，註解將套用至您所有的資料。<ul><li>**[!UICONTROL 出現這些量度的任一項]**：最多拖放 10 個可觸發註解顯示的量度。</li><li>**[!UICONTROL 包含這所有的篩選器]**：最多可拖放 10 個維度或篩選器，在註解顯示時加以篩選。</li></ul><p>使用案例：eVar 阻止了收集特定日期範圍的資料。將 eVar 拖曳至「**[!UICONTROL 出現這些量度的任一項]**」對話框中。否則您的[!UICONTROL 瀏覽]量度不會報告任何資料 - 遵循相同程序。<p>**注意：**&#x200B;任何套用到元件且之後作為計算量度或篩選器定義一部分來使用的註解，都不會自動繼承該註解。必須也將所需的計算量度新增到範圍區段中，才能顯示該註解。但是，對於您希望使用相同資訊來註解的任何篩選器，都應該建立新的註解。<p>例如，您可將註解套用到特定日子的[!UICONTROL 訂單]。 然後您可將計算量度中的[!UICONTROL 訂單]用於相同日期範圍。 新的計算量度不會自動顯示訂單的註解；也必須也將計算量度新增到範圍區段中，才能顯示該註解。 |
   | [!UICONTROL 套用至所有資料視圖] | 預設情況下，註解會套用到原始的資料視圖。勾選此方塊後，您就可以將註解套用至公司的所有資料視圖。 |
   | [!UICONTROL 套用於所有專案] | 預設情況下，註解會套用在目前的專案。若勾選此方框，您即可將註解套用在您擁有的所有專案。請注意，啟動 Annotation Builder 時，這個核取方塊才會出現。 |

   {style="table-layout:auto"}

1. 按一下「**[!UICONTROL 儲存]**」。
