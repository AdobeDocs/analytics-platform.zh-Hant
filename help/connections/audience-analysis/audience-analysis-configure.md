---
title: 設定對象分析
description: 瞭解如何設定對象分析
solution: Customer Journey Analytics
feature: Audiences
role: Admin
exl-id: 0db3f6f7-9d7e-41bf-8eb5-02e439bab10a
source-git-commit: 4f1299595077a1756a6ad0c4f5ef5e0247ab4973
workflow-type: tm+mt
source-wordcount: '1355'
ht-degree: 14%

---

# 設定對象分析 {#configure-audience-analysis}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-analysis-merge-policy"
>title="合併原則"
>abstract="合併原則會將來自多個資料集的設定檔資料合併到統一的客戶設定檔中，用於建立受眾。 如果您看到多個合併原則並且不確定要選擇哪一個，請選取「預設以時間為基礎」。 或洽詢您的資料團隊，以瞭解哪些對象與每個合併原則相關聯。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-analysis-sandbox"
>title="沙箱"
>abstract="選取包含正確Experience Platform設定檔資料集的沙箱。 這些資料集必須包含您要在Analysis Workspace中報告的對象資料。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-person-id"
>title="個人 ID"
>abstract="從結構描述中選取代表人員ID的欄位。 選取範圍僅限於結構描述中標示為身分並擁有身分名稱空間的欄位清單。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-namespace"
>title="使用主要身分識別命名空間"
>abstract="如果您希望Customer Journey Analytics在標示primary=true屬性的「身分對應」中尋找身分，然後使用該身分作為該列的人員ID，請啟用此選項。 此身分識別在 Experience Platform 中是用於資料分割的主索引鍵。<br/>如果您讓此選項保持停用，請從下面的[身分名稱空間]欄位中選取名稱空間。 Customer Journey Analytics會搜尋此名稱空間索引鍵的每一列的「身分對應」，並將該名稱空間底下的身分識別當作該列的人員ID。"

<!-- markdownlint-enable MD034 -->

對象分析可讓您將對象成員資格資料從Experience Platform設定檔資料集擷取到Customer Journey Analytics連線。 對象會成為新的維度，以便在Analysis Workspace中使用。 如需對象分析的詳細概觀資訊，請參閱[對象分析概觀](/help/connections/audience-analysis/audience-analysis-overview.md)。

>[!IMPORTANT]
>
>對象資料會每晚重新處理和產生，因此對象資料僅供前一天（「昨天」）的分析使用。
>
>在您建立對象分析設定後的次日，便可在Customer Journey Analytics資料檢視中使用對象。

## 建立對象分析設定

建立對象分析設定時，您會選取與您要分析之Experience Platform對象相關聯的沙箱和合併原則。 Customer Journey Analytics會建立新的查詢資料集，然後自動將查詢資料集和設定檔資料集新增到您選擇的連線。

只有系統管理員可以建立對象分析設定。

若要建立對象分析設定：

1. 在Customer Journey Analytics中，選取&#x200B;**[!UICONTROL 資料管理]** > **[!UICONTROL 對象分析組態]**。

   ![對象分析首頁面](assets/audience-analysis-empty.png)

1. 選取&#x200B;**[!UICONTROL 建立組態]**。

   ![建立對象分析設定](assets/audience-analysis-create.png)

1. 在&#x200B;**[!UICONTROL 詳細資料]**&#x200B;區段中，指定下列資訊：

   | 欄位 | 說明 |
   |---------|----------|
   | **[!UICONTROL 名稱]** | 指定組態的名稱。 |
   | **[!UICONTROL 沙箱]** | 選取包含您要新增至連線的設定檔資料集的Experience Platform沙箱。 單一沙箱可支援最多100個對象分析設定。 <p>Adobe Experience Platform 提供的[沙箱](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sandbox/home)可將單一 Platform 實例分割成不同的虛擬環境，以利開發及改進數位體驗應用程式。您可將沙箱視為內含資料集的「資料獨立單位」。沙箱可用於控制資料集的存取權限。</p> |

1. 在&#x200B;**[!UICONTROL 設定檔資料集]**&#x200B;區段中，指定下列資訊：

   | 欄位 | 說明 |
   |---------|----------|
   | **[!UICONTROL 合併原則]** | 選取與您要用於客群分析的輪廓資料集對應的合併原則。 <p>合併原則可決定Adobe Experience Platform如何將來自多個資料集的設定檔資料合併到統一的客戶設定檔中，以用於建立受眾。 您選取的合併原則會影響對象中包含哪些設定檔屬性。 每天，系統都會在Experience Platform中產生這些資料的快照。 此快照提供特定時間點的靜態資料檢視，不包含任何事件資料。</p><p>如果您看到多個合併原則且不確定要選擇哪一個，請選取&#x200B;**[!UICONTROL 預設以時間為基礎]**&#x200B;的合併原則。 您也可以洽詢資料團隊，深入瞭解哪些對象與每個合併原則相關聯。</p> |
   | **[!UICONTROL 設定檔資料集]** | 與您選取的合併原則相關聯的設定檔資料集。 此設定檔資料集包含您要分析的Experience Platform對象資料。 此設定檔資料集已新增至您選取的連線。<p>選擇合併原則後，設定檔快照匯出隨即顯示。 例如：`Profile-Snapshot-Export-abbc7093-80f4-4b49-b96e-e743397d763f`。</p><p>如需詳細資訊，請參閱Experience Platform儀表板指南中的[設定檔屬性資料集](https://experienceleague.adobe.com/en/docs/experience-platform/dashboards/query#profile-attribute-datasets)。</p> |

1. 在&#x200B;**[!UICONTROL 連線]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL 選取連線]**。

1. 在[連線]對話方塊中，選取您要新增設定檔資料集的連線旁的核取方塊，然後選取[**[!UICONTROL 使用連線]**]。

   一個連線只能與一個對象分析設定相關聯。

1. 指定下列資訊以設定連線：

   | 欄位 | 說明 |
   |---------|----------|
   | **[!UICONTROL 個人 ID]** | 從結構描述中選取代表人員ID的欄位。<p>選取範圍僅限於結構描述中標示為身分且具備身分名稱空間的欄位清單。 依預設會選取&#x200B;**[!UICONTROL IdentityMap]**，且適用於大部分的組態。 </p><p>如果沒有人員ID可以選擇，表示結構描述中尚未定義一或多個人員ID。 更多詳細資訊，請參閱[在 UI 中定義身分識別欄位](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/ui/fields/identity)。</p> |
   | **[!UICONTROL 使用主要身分名稱空間]** | 此選項顯示您是否為人員ID選取&#x200B;**[!UICONTROL 身分對應]**。 <p>如果您希望Customer Journey Analytics在標示primary=true屬性的「身分對應」中尋找身分，然後使用該身分作為該列的人員ID，請啟用此選項。 此身分識別在 Experience Platform 中是用於資料分割的主索引鍵。此身分識別也是做為 Customer Journey Analytics 個人 ID 的首選 (取決於資料集在 Customer Journey Analytics 連線中的設定方式)。</p> |
   | **[!UICONTROL 身分識別命名空間]** | 此選項顯示您是否為人員ID選取&#x200B;**[!UICONTROL 身分對應]**。 如果您使用「主要ID名稱空間」，則會停用此選項。 <p>身分識別命名空間是 [Experience Platform 身分識別服務](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/identity/features/namespaces)的元件。命名空間是作為身分識別相關內容的指標。如果您指定名稱空間，Customer Journey Analytics會針對此名稱空間索引鍵搜尋每一列的「身分對應」，並使用該名稱空間底下的身分識別，作為該列的人員ID。 由於Customer Journey Analytics無法執行涵蓋所有列的完整資料集掃描來判斷哪些名稱空間存在，因此下拉式選單中會顯示所有可能的名稱空間。 您必須知道資料中指定了哪些命名空間；系統不會自動偵測這些命名空間。</p> |

   <!-- Add this when B2B releases for AuA **[!UICONTROL Account ID]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}|  (only displayed for account-based connections) The Account ID that is used to support account-based reporting for the dataset. -->

1. 在&#x200B;**[!UICONTROL 資料檢視]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL 選取資料檢視]**。

1. 在「資料檢視」對話方塊中，選取一或多個資料檢視旁的核取方塊，以在Analysis Workspace中分析Experience Platform對象資料時使用。 這些資料檢視會自動設定用於報表的Experience Platform受眾資料。

1. 選取&#x200B;**[!UICONTROL 使用資料檢視]**。

1. 選取&#x200B;**[!UICONTROL 建立]**&#x200B;以建立組態。

   >[!IMPORTANT]
   >
   >由於設定檔資料集每天會更新一次，因此您建立對象分析設定後的第二天，即可在Customer Journey Analytics資料檢視中使用對象。


1. 24小時後，[在資料檢視中檢視對象維度](#view-audience-dimensions-in-the-data-view)，以確認您選取的資料檢視中可以使用對象維度。

## 在資料檢視中檢視對象維度

在您[建立對象分析組態](#create-an-audience-analysis-configuration)後，您可以驗證對象維度是否已新增至您在組態期間選取的資料檢視。

若要在資料檢視中檢視對象維度，您必須是資料檢視所指派之產品設定檔的產品設定檔管理員。 如需詳細資訊，請參閱[存取控制](/help/technotes/access-control.md)。

若要在資料檢視中檢視對象分析維度：

1. 在 Customer Journey Analytics 中，選取「**[!UICONTROL 資料管理]**」>「**[!UICONTROL 資料釋圖]**」。

1. 在&#x200B;**[!UICONTROL 維度]**&#x200B;區段中，下列維度現在應該可供使用：

   * **[!UICONTROL 對象名稱]**

   * **[!UICONTROL 對象來源]**

   * **[!UICONTROL 已退出的對象來源]**

   * **[!UICONTROL 退出的對象名稱]**

   請注意，上述每個維度皆已新增至與您在對象分析設定期間選取的合併原則相關聯的設定檔資料集，每個維度皆已新增至建立的新查詢資料集。

   ![資料檢視中可用的對象維度](assets/audience-analysis-dataview-dataset.png)

1. 在Analysis Workspace中使用對象分析維度。

   有權使用Analysis Workspace中資料檢視的使用者現在可以檢視新維度，並在其分析中使用它們。 如需如何在Analysis Workspace中使用對象分析維度的相關資訊，請參閱[在Customer Journey Analytics中分析Experience Platform對象](/help/connections/audience-analysis/analyze-audiences.md)。
