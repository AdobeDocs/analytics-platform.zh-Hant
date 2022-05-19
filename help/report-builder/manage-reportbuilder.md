---
title: 如何使用Customer Journey Analytics中的Report Builder管理資料塊
description: 介紹如何在Report Builder中使用管理功能
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 70103020-a4a9-43be-933c-bde5a6d088c8
source-git-commit: e9856269ee07b7119f75b98489b47e1f35f7cf5f
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 1%

---

# 在Report Builder中管理資料塊

您可以使用資料塊管理器查看和管理工作簿中的所有資料塊。 資料塊管理器提供搜索、篩選和排序功能，使您能夠快速查找特定資料塊。 選擇一個或多個資料塊後，可以編輯、刪除或刷新所選資料塊。

![image](./assets/image52.png)

## 查看資料塊

按一下 **管理** 查看工作簿中所有資料塊的清單。


![影像](./assets/image53.png)

資料塊管理器列出工作簿中存在的所有資料塊。 

![影像](./assets/image52.png)

## 對資料塊清單排序

可以按顯示列對資料塊清單進行排序。 例如，您可以按報表套件、篩選器、日期範圍和其他變數對資料塊清單進行排序。

要對資料塊清單進行排序，請按一下列標題。

![影像](./assets/image54.png)

## 搜索資料塊清單

使用「搜索」欄位查找資料塊表中的任何內容。 例如，可以搜索資料塊或報告套件中包含的度量。 您還可以搜索日期範圍、修改日期或上次運行日期列中顯示的日期。

![影像](./assets/image55.png)

## 編輯資料塊

您可以編輯資料視圖、日期範圍或應用於一個或多個資料塊的篩選器。

例如，可以在一個或多個資料塊中用新篩選器替換現有篩選器。

1. 選擇要更新的資料塊。 您可以選擇頂級複選框以選擇所有資料塊，也可以選擇單個資料塊。

   ![影像](./assets/image56.png)

1. 按一下「編輯」表徵圖可顯示「快速編輯」窗口。

   ![影像](./assets/image58.png)

1. 選擇篩選器連結以更新資料視圖、日期範圍或篩選器。

   ![影像](./assets/image59.png)

## 刷新資料塊

按一下刷新表徵圖以刷新清單中的資料塊。

<img src="./assets/refresh-icon.png" width="15%"/>

要驗證是否刷新了資料塊，請查看刷新狀態表徵圖。 綠色圓中的複選標籤 <img src="./assets/refresh-success.png" width="5%"/> 指示資料塊刷新成功。 刷新失敗的資料塊將顯示警告表徵圖 <img src="./assets/refresh-failure.png" width="5%"/>.  這使識別任何資料塊是否有錯誤變得容易。


![影像](./assets/image512.png)

## 刪除資料塊

按一下垃圾桶表徵圖可刪除選定的資料塊。

## 組資料塊

您可以使用 **分組依據** 下拉菜單，或者按一下列標題。 要按列對資料塊排序，請按一下列標題。 要按組對資料塊進行分組，請從 **分組依據** 的下界。 例如，下面的螢幕快照顯示按工作表分組的資料塊。 它顯示按Sheet1和Sheet2分組的資料塊。  這在過濾器替換用例中非常有用。 如果對每個資料塊應用了多個篩選器，則建立包含要替換的所有資料塊的組會很有幫助。 然後，您可以輕鬆地同時選擇和編輯它們。

![影像](./assets/group-data-blocks.png)

## 修改資料塊管理器視圖

可以修改在「資料塊管理器」窗口中可見的列。


按一下列清單 <img src="./assets/image515.png" width="3%"/> 表徵圖，以選擇資料塊管理器中列出的列。 選擇列名以顯示列。 取消選擇列名以從視圖中刪除列。

![揚格](./assets/image516.png)
