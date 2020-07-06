---
description: 同類群組分析的使用案例範例。
keywords: Analysis Workspace
title: 同類群組分析使用案例
topic: Reports and analytics
uuid: 5ec46f84-5702-4bc1-a796-874a3abe87c9
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 75%

---


# [!UICONTROL 世代分析] 使用案例

>[!NOTE]
>
>您正在檢視客戶歷程分析中分析工作區的檔案。 其功能集與傳統Adobe Analytics中 [的「分析工作區」略有不同](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html)。 [更多詳情...](/help/getting-started/cja-aa.md)

Use case examples for [!UICONTROL Cohort Analysis].

## 應用程式參與使用案例

假設您想分析已安裝您應用程式的使用者，在一段時間內參與應用程式的情形。使用者是否安裝應用程式後就不曾使用？還是使用一陣子後不用了？或是一段時間後仍持續使用？

You can create a six-month [!UICONTROL Cohort Analysis]:

**粒度**: 每月，從 2015 年 1 月到 2015 年 6 月。

**包含量度**：應用程式安裝。

**回訪量度**: 作業階段或啟動次數

後續月份的訪客必須有作業階段或至少啟動應用程式，否則不會計算為&#x200B;*`engaged`*。[!UICONTROL Choort Analysis] （同類群組分析）接著會顯示使用模式， *`App Install`* 其中一律發生在第0個月。 您可能發現無論使用者於何時安裝應用程式，使用量都在第 2 個月下降。(對於在 2015 年 1 月安裝應用程式的使用者，第 2 個月是指 2015 年 3 月。對於在 2015 年 2 月安裝應用程式的使用者，第 2 個月是指 2015 年 4 月，以此類推。)這項分析可供您傳送電子郵件或推播訊息給安裝應用程式後進入第二個月期間的所有使用者，提醒他們使用應用程式。

## 訂閱使用案例

您在 Adobe.com 工作並提供免費 Creative Cloud 訂閱。您的目標是讓使用者從免費版本升級至 30 天試用版，最終升級至付費版本。

**粒度**：每月

**包含量度**：下載連結

**回訪量度**：購買付費 Creative Cloud

Using this [!UICONTROL Cohort Analysis], you could see, for example, that anywhere between 8% and 10% of free Creative Cloud users upgrade in the first month after installation, regardless of when they installed. 12-15% 於使用第二個月進行升級。之後升級率顯著下降：4-5% 在第三個月，3-4% 在第四個月，1-2% 在第五個月。

發現您必須在第三個月挽留潛在客戶後，即可設定在第三個月期中針對一組抽樣使用者發送電子郵件促銷活動，對尚未升級的使用者提供 $50 的優惠券。

幾個月後再次執行同類群組分析報表。對於推出促銷活動後形成的同類群組，在第三個月轉換為付費 Creative Cloud 訂閱的比率從 4-5% 提高為 13-14%，針對從該點以後到達第三個月的每個每月同類群組，代表每個同類群組產生數十萬美元的收入。

## 複雜同類群組區段使用案例

一家大型連鎖飯店針對多個客戶群組推出促銷活動，並追蹤其成效。為找出要鎖定的最佳使用者同類群組，他們希望建立非常明確的同類群組。Using the augmented [!UICONTROL Inclusion] and [!UICONTROL Return] Criteria within [!UICONTROL Cohort] Tables, they are able to define just the right cohort groupings with multiple metrics and segments to identify underperforming customers groups in order to target them with promotions and deals to increase bookings.

## 應用程式版本採用使用案例

一家大型保險公司透過其行動應用程式，提升大量客戶參與。然而，隨著他們的應用程式增加了新功能，其客戶是否升級至最新的應用程式版本至關重要。They can analyze and compare all of their app versions side-by-side using [!UICONTROL Custom Dimension] Cohort to see which customers on which app version to target. 此外，他們也可以追蹤保留率和流失率，查看在一段時間中，特定應用程式版本是否讓客戶不想使用該應用程式。他們能透過行動傳訊重新與這些使用者互動，並讓使用者升級至最新版本，以使用他們最新的功能。

## 促銷活動黏著度使用案例

一家跨國媒體公司推出目標式促銷活動，吸引使用者前往其各平台，以提升客戶參與。每個平台的廣告花費皆根據客戶參與度和保留率，因此，成功的促銷活動對於其業務的成功至關重要。They use our new [!UICONTROL Custom Dimension] Cohort feature in [!UICONTROL Cohort] Tables to compare various campaigns side-by-side to identify which campaigns are most effective at acquiring and retaining users to increase engagement. 接著，他們便能找出讓促銷活動成功的關鍵，並將其套用至其他促銷活動，以提升各平台的參與度.

## 產品上市使用案例

一家大型服裝零售業者擁有許多特定客戶區段，為其業務帶來大部分的收入。每個區段皆有針對該區段設計和打造的特定產品。隨著每次產品上市，他們想知道在一段時間中，新產品如何促進各同類群組的銷售量。Using the new [!UICONTROL Latency Table] setting in [!UICONTROL Cohort Analysis], they are able to analyze a given customer segment&#39;s pre-launch and post-launch behavior and revenue. 他們可以透過這項資訊找出哪些產品創造新收入，以及哪些產品無法吸引客戶。

## 個人黏著度 - 最忠實的使用者使用案例

一家大型航空公司的成功和收入大部分來自重複和忠實的客戶。在許多情況下，他們的忠實旅客佔其收入的大部分，而保留這些客戶對他們的長期成功至關重要。找出他們最忠實和一致的客戶通常很困難。However, using the new [!UICONTROL Rolling Calculation] setting in [!UICONTROL Cohort Analysis], they were able to analyze loyal customer segments and find out which travelers were repeat purchasers month-over-month. 接著，他們便可用獎勵和福利來鎖定這些忠實旅客。此外，他們還能將「同類群組」類型從保留率切換至流失率，找出不是每月重複購買者的客戶，並透過促銷活動鎖定這些區段，進而重新與客戶互動，確保其日後仍會是忠實客戶。
