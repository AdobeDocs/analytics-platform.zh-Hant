---
title: 警告
description: Customer Journey Analytics中各種BI工具中BI擴充功能的注意事項
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: cb0102923f10f39becd40cc4187d2e11fb8c4e2f
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 0%

---

# 警告


使用Customer Journey Analytics BI擴充功能時，每一種支援的BI工具都有一些需注意的事項。

+++ BI 工具

>[!BEGINTABS]

>[!TAB Power BI案頭版]

* Power BI Desktop進階日期範圍篩選是專屬功能。  對於結束日期，您需要選取要報告的一天之後的日期。 例如，**[!UICONTROL 位於]** `1/1/2023` **[!UICONTROL 或之後，]**&#x200B;之前`1/2/2023`。
* 建立連線時，Power BI案頭預設為&#x200B;**[!UICONTROL 匯入]**。 請確定您使用&#x200B;**[!UICONTROL 直接查詢]**。
* Power BI Desktop透過Power Query公開資料轉換。  Power Query主要用於匯入型別連線，因此許多您套用的轉換（如日期或字串函式）會擲回錯誤，指出您需要切換到匯入型別連線。  如果您需要在查詢時轉換資料，應使用衍生的維度和量度，因此Power BI不需要自行轉換。
* Power BI Desktop不瞭解如何處理日期 — 時間型別欄，所以不支援&#x200B;**[!UICONTROL daterange *X *]**&#x200B;維度，例如&#x200B;**[!UICONTROL daterangehour &#x200B;]**&#x200B;和&#x200B;**[!UICONTROL daterangeminute &#x200B;]**。
* Power BI Desktop預設會嘗試使用更多查詢服務工作階段建立多個連線。  前往專案的Power BI設定並停用平行查詢。
* Power BI Desktop會執行所有排序和限制使用者端作業。 Power BI Desktop對於前&#x200B;*X*&#x200B;個包含繫結值的篩選也有不同的語意。 因此，您無法建立與Analysis Workspace中相同的排序和限制。
* 舊版Power BI Desktop 2024年10月發行版本中斷PostgreSQL資料來源。 請確定您使用本文中提及的版本。

>[!TAB Tableau案頭]

* Tableau案頭日期範圍篩選不適用。 對於結束日期，您需要選取要報告的一天之後的日期。
* 根據預設，當您新增日期或日期時間維度（例如&#x200B;**[!UICONTROL Daterangemonth]**）至工作表的列時，Tableau Desktop會將&#x200B;**[!UICONTROL YEAR()]**&#x200B;函式中的欄位換行。  若要取得您想要的結果，您必須選取該維度，然後從下拉式選單中選取您要使用的日期函式。  例如，當您嘗試使用&#x200B;**[!UICONTROL Daterangemonth]**&#x200B;時，將&#x200B;**[!UICONTROL 年]**&#x200B;變更為&#x200B;**[!UICONTROL 月]**。
* 在Tableau Desktop中，將結果限制在前&#x200B;*X*&#x200B;是不明顯的。 您可以明確限制結果，或使用計算欄位和&#x200B;**[!UICONTROL INDEX()]**&#x200B;函式。  將Top *X*&#x200B;篩選器新增至維度，會使用不支援的內部聯結產生複雜的SQL。

>[!TAB 觀察者]

* Looker具有每個節點的最大連線數目設定，此設定必須介於5到100之間。  您無法將此值設為1。  此設定表示Looker連線一律使用至少5個可用的查詢服務工作階段。
* Looker可讓您以Customer Journey Analytics資料檢視為基礎，以檢視建立專案。 Looker接著會使用LookerML，根據資料檢視中可用的維度和量度建立模型。  此專案檢視不會自動更新以符合來源。  如果您變更或新增CJA資料檢視維度、量度、計算量度或區段，這些變更不會自動顯示在Looker中。  您必須手動更新專案檢視或建立新專案。
* 查閱者在日期或日期時間欄位（例如&#x200B;**[!UICONTROL Daterange Date]**&#x200B;或&#x200B;**[!UICONTROL Daterangeday Date]**）的使用者體驗令人困惑。
* 查閱者的日期範圍是排除而非包含。  **[!UICONTROL until （之前）]**&#x200B;為灰色，因此您可能會遺漏該外觀。  結束日期前，您必須選取要報告日期的前一天。
* Looker不會自動將您的量度視為量度。  當您選取量度時，依預設，Looker會嘗試將量度視為查詢中的維度。  若要將量度視為量度，您需要建立如上所述的自訂欄位。 作為捷徑，您可以選取&#x200B;**[!UICONTROL ⋮]**、選取&#x200B;**[!UICONTROL 彙總]**，然後選取&#x200B;**[!UICONTROL 總計]**。

>[!TAB Jupyter Notebook]

* Jupyter Notebook的主要注意事項是此工具不像其他BI工具那樣是拖放式使用者介面。 您可以建立良好的視覺效果，但您必須撰寫程式碼才能完成此操作。

>[!TAB RStudio]

* R dplyr適用於一般結構描述，因此需要&#x200B;**[!UICONTROL FLATTEN]**&#x200B;選項。
* RStudio的主要注意事項是此工具不像其他BI工具那樣是拖放式使用者介面。 您可以建立良好的視覺效果，但您必須撰寫程式碼才能完成此操作。

>[!ENDTABS]

+++
