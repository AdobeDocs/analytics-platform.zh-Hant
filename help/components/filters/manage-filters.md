---
title: 篩選器管理器
description: 瞭解如何在 Customer Journey Analytics 中管理篩選器
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: e84010b9ea9e6385574e8b1a04f7eccbba3ebc90
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 22%

---

# 篩選器管理器

篩選器管理器提供許多策劃篩選器的方式，例如共用、標籤、核准、複製、刪除和標示為我的最愛。

篩選器管理器會顯示您所擁有以及已經與您共用的篩選器。 管理員層級的使用者可以查看組織中的所有篩選器。此概觀會介紹「篩選器」管理員的使用者介面和功能。

![](assets/filter-manager-ui.png)

## 存取篩選器管理器

1. 在Customer Journey Analytics中，選取&#x200B;**[!UICONTROL 元件]**&#x200B;索引標籤，然後選取&#x200B;**[!UICONTROL 篩選器]**。

## 篩選器管理器中的可用動作

在「篩選器管理器」中，您可以：

* [過濾篩選器清單](/help/components/filters/filters-filter.md)

* [將篩選器標示為我的最愛](/help/components/filters/filters-favorite.md)

* [核准篩選器](/help/components/filters/filters-approve.md)

* [標記篩選器](/help/components/filters/filters-tag.md)

* [共用篩選器](/help/components/filters/filters-share.md)

* 將篩選器匯出至CSV檔案。

* [複製篩選器](/help/components/filters/filters-copy.md)

* 刪除篩選器

## 設定欄

您可以設定顯示的欄，以設定「篩選器管理器」中每個篩選器的顯示資訊。

若要在「篩選器管理器」中設定可見欄：

1. 在Customer Journey Analytics中，選取&#x200B;**[!UICONTROL 元件]**&#x200B;索引標籤，然後選取&#x200B;**[!UICONTROL 檔案管理員]**。

1. 在篩選器管理員中，選取&#x200B;**自訂欄**&#x200B;圖示![自訂欄圖示](assets/customize-columns-icon.png)，然後選取您要顯示在篩選器管理員中的欄。

   可使用下列欄:

   | 欄標題 | 說明 |
   |---|---|
   | 標題和說明 | 這些值會在篩選產生器中提供。 若要編輯標題和說明，請選取標題連結以開啟篩選產生器。 |
   | 我的最愛 | 在每個篩選器旁顯示星號圖示，讓您標示篩選器為我的最愛。 如需詳細資訊，請參閱[將篩選器標示為我的最愛](/help/components/filters/filters-favorite.md)。 |
   | 資料視圖 | 此欄指出上次儲存篩選器的資料檢視。 |
   | 所有者 | 指出篩選器的擁有者。如果您不是管理員，就只能看見自己所擁有或已和您共用的篩選器。 |
   | 標記 (未在欄選擇器中勾選，因此此欄不會出現) | 由您或共用篩選器給您的人員對篩選器套用的標記。 |
   | 共用對象 | 列出您共用篩選器的目標個人或群組 (僅限管理員使用) 或「全部」(僅限管理員使用)。 <p>當您共用篩選器或與您共用時，篩選器名稱旁會顯示共用圖示。</p> |
   | 修改日期 | 顯示上次修改篩選器的日期。 |
   | 使用於 | 顯示篩選目前使用的元件數目。 <p>例如，如果篩選器用於40個專案和2個警示，則此欄的值顯示為&#x200B;[!UICONTROL **42個元件**]。</p> <p>選取此資料欄中的值，以檢視使用篩選器的資料劃分(例如，[!UICONTROL **專案(40)**]、[!UICONTROL **警報(2)**])。</p><p>篩選器可用於下列任何元件型別：</p> <ul><li>計算量度</li><li>專案</li><li>已排程的專案</li></ul><p>此資訊可協助您判斷元件是否對貴組織中的使用者有價值、元件使用位置以及元件是否需要刪除或修改。</p><p>檢視此欄時請考慮以下事項：</p><ul><li>此資訊不包括API、Report Builder或Data Warehouse的使用情況。</li><li>預設不會顯示&#x200B;**]資料行中使用的[!UICONTROL **。 [設定資料行](#configure-columns)以顯示它。</li><li>如果此欄中沒有指定元件的資料，但具有&#x200B;[!UICONTROL **上次使用**]&#x200B;日期，則表示該元件可能已用於分析而未儲存。</li><li>此資訊僅供系統管理員使用。</li></ul><p>您可以搭配此資訊使用[資料字典](/help/components/data-dictionary/data-dictionary-overview.md)，協助您追蹤並更清楚瞭解組織中如何使用元件。</p> |
   | 上次使用 | 顯示上次在下列任何元件型別中使用篩選器的日期： <ul><li>計算量度</li><li>專案</li><li>已排程的專案</li><li>篩選器</li></ul> <p>此資訊可協助您判斷元件是否對貴組織中的使用者有價值，或是否應將其刪除。</p><p>檢視此欄時請考慮以下事項：</p><ul><li>此資訊不包括API、Report Builder或Data Warehouse的使用情況。</li><li>對於某些元件，如果元件是在2023年9月之前最後一次使用，則此欄可能不包含資料。</li><li>此資訊僅供系統管理員使用。</li></ul><p>您可以搭配此資訊使用[資料字典](/help/components/data-dictionary/data-dictionary-overview.md)，協助您追蹤並更清楚瞭解組織中如何使用元件。 |

   {style="table-layout:auto"}
