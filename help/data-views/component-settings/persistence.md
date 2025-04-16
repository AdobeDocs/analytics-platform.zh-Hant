---
title: 持續性元件設定
description: 決定是否會在不同事件中儲存維度值或是如何儲存。
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 9c1a8c51aa3e23412e5b04d3ab1571a9d1c7612e
workflow-type: tm+mt
source-wordcount: '1053'
ht-degree: 79%

---


# [!UICONTROL 持續性]元件設定 {#persistence-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_persistence"
>title="持續性"
>abstract="設定套用至維度的預設配置模式。配置會在報告中的篩選器之前套用。如要了解更多資訊，請參閱[配置設定](/help/data-views/component-settings/persistence.md#allocation-settings)、[過期設定](/help/data-views/component-settings/persistence.md#expiration-settings)、[繫結維度](/help/data-views/component-settings/persistence.md#binding-dimension) 和[繫結量度](/help/data-views/component-settings/persistence.md#binding-metric)。"

<!-- markdownlint-enable MD034 -->



[!UICONTROL 持續性]是指定維度值能夠歸因於其設定事件以外的量度。 它使用配置和過期時間的組合。

![醒目顯示「持續性」選項的資料檢視視窗](../assets/persistence.png)

* **配置**&#x200B;可讓您決定當一個欄中可以同時保留多個維度專案時要保留的值。

  >[!NOTE]
  >
  >如果您對報告的量度設定[使用非預設歸因模型](/help/data-views/component-settings/attribution.md)，歸因模型會忽略您針對相同報告的維度設定的配置。
  >
  >然而，當進行的[完整表格匯出](/help/analysis-workspace/export/export-cloud.md)包含多個維度時，歸因會保留套用於每個維度的配置模型。

* **期限**&#x200B;可讓您確定維度項目在其設定的事件之後持續多長時間。

[!UICONTROL 持續性]僅在維度上可用，並且可追溯至套用到的資料。它是發生在套用篩選或其他分析作業之前的立即資料轉換。

| 設定 | 說明 |
| --- | --- |
| [!UICONTROL 設定持續性] | 啟用維度的持續性。如果未啟用持續性，則維度僅與同一事件中存在的量度相關。此設定預設為停用。 |
| [!UICONTROL 配置] | 可讓您指定用於維度持續性的配置模式。選項有:<ul><li>**[!UICONTROL 最近]**：維度中的值會持續存在，直到被後續值覆寫為止</li><li> **[!UICONTROL 原始]**：此維度的第一個值會持續存在，且不會被後續值覆寫</li><li>**[!UICONTROL 全部]**：此維度的所有值會同時保留</li><li>**[!UICONTROL 第一個已知]**：已使用此維度的第一個值，並將套用至之前和之後的所有事件。</li><li>**[!UICONTROL 最後一個已知]**：此維度的最後一個值已使用，並將套用至之前和之後的所有事件。</li></ul> |
| [!UICONTROL 期限] | 可讓您指定維度的持續性視窗。選項有: <ul><li>**[!UICONTROL 工作階段]** （預設）</li><li>**[!UICONTROL 人員]**</li><li>**[!UICONTROL 自訂時間]**</li><li>**[!UICONTROL 量度]**</li></ul>。您可能需要能夠使購買的維度到期 (例如內部搜尋詞或其他銷售使用案例)。您可以設定的最長期限為 90 天。如果您選取「[!UICONTROL 全部]」配置，則只有[!UICONTROL 工作階段]或[!UICONTROL 人員]期限可用。 |

{style="table-layout:auto"}

## [!UICONTROL 配置]設定

有關可用配置設定的詳細資料。

* **[!UICONTROL 最近]**：儲存最近 (依時間戳記) 存在於維度中的值。維度期限內出現的任何後續值都會取代之前的保存值。如果在[「沒有值選項」](no-value-options.md)下在此維度上啟用了「將沒有值視為一個值」，則空值會覆寫以前保存的值。例如，考慮包含[!UICONTROL 最近]的配置和[!UICONTROL 工作階段]期限的下表：

  | 維度 | 點擊 1 | 點擊 2 | 點擊 3 | 點擊 4 | 點擊 5 |
  | --- | --- | --- | --- | --- | --- |
  | 資料集的值 |  | C | B |  | A |
  | 最近配置 |  | C | B | B | A |

* **[!UICONTROL 原始]**：在期限內儲存存在於維度中的原始值 (依時間戳記)。 如果此維度具有值，則在後續事件中看到不同的值時不會覆寫該維度。例如，考慮包含[!UICONTROL 原始]配置和[!UICONTROL 工作階段]期限的下表：

  | 維度 | 點擊 1 | 點擊 2 | 點擊 3 | 點擊 4 | 點擊 5 |
  | --- | --- | --- | --- | --- | --- |
  | 資料集的值 |  | C | B |  | A |
  | 原始配置 |  | C | C | C | C |

* **[!UICONTROL 全部]**：作用類似於量度的[!UICONTROL 參與率]歸因模式。 平等地保留所有值，因此每個值都可以完全歸功於報告中的量度。例如，考慮包含[!UICONTROL 全部]配置和[!UICONTROL 工作階段]期限的下表：

  | 維度 | 點擊 1 | 點擊 2 | 點擊 3 | 點擊 4 | 點擊 5 |
  | --- | --- | --- | --- | --- | --- |
  | 資料集的值 | A | B | C |  | A |
  | 全部配置 | A | A、B | A、B、C | A、B、C | A、B、C |

* **[!UICONTROL 最先已知]**&#x200B;和&#x200B;**[!UICONTROL 最後已知]**：(2022 年 1 月 19 日) 這兩種配置模式滿足「登入」和「退出」維度。它們採取指定持續性範圍 (工作階段、人員或具回顧的自訂時段) 內某維度的第一個或最後一個觀察值，並將它套用至指定範圍內的全部事件。範例：

  | 維度 | 點擊 1 | 點擊 2 | 點擊 3 | 點擊 4 | 點擊 5 |
  | --- | --- | --- | --- | --- | --- |
  | 時間戳記 (分鐘) | 1 | 2 | 3 | 6 | 7 |
  | 原始值 |  | C | B |  | A |
  | 最先已知 | C | C | C | C | C |
  | 最後已知 | A | A | A | A | A |


## [!UICONTROL 期限]設定

有關可用期限設定的詳細資料。

* **工作階段**：在指定的工作階段後過期。預設期限窗口。
* **人員報告期間**：在報告期間結束時到期。
* **全域帳戶報告期間** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}：在報告期間結束時到期。
* **帳戶報告期間** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}：在報告期間結束時到期。
* **機會報告期間** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}：在報告期間結束時到期。
* **購買群組報表期間** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}：報表期間結束時到期。
* **自訂時間**：在指定的時段 (最長 90 天) 後到期。這個期限選項僅適用於「原始」和「最近」配置模式。 在使用以時間為準的期限時，將會考量您的報告期間 (最長 90 天) 開始前的值。
* **量度**：在事件中看到此量度時，維度中的保存值會立即過期。您可以使用量度當做此維度的過期點。 這個期限選項僅適用於「原始」和「最近」配置設定。


## [!UICONTROL 繫結維度]

讓您將維度值的持續性繫結至另一維度中維度值的下拉式清單。有效的下拉式清單選項含有在資料檢視中所含的其他維度。

如需有關如何有效使用繫結維度的範例，請參閱「[使用 Customer Journey Analytics 中的繫結維度和量度](../../use-cases/data-views/binding-dimensions-metrics.md)」。


>[!BEGINSHADEBOX]

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [繫結維度](https://video.tv.adobe.com/v/342694/?quality=12&learn=on){target="_blank"}的示範影片。

>[!ENDSHADEBOX]


## [!UICONTROL 繫結量度]

讓您選擇做為繫結觸發器量度的下拉式清單。有效選項包含在資料檢視中的量度。

此項設定只會在繫結維度在物件陣列中小於元件時出現。繫結量度存在於事件中時，維度值會從事件水準維度複製到繫結維度的下層結構描述。

如需有關如何有效使用繫結維度的更多資訊，請參閱「[使用 Customer Journey Analytics 中的繫結維度和量度](../../use-cases/data-views/binding-dimensions-metrics.md)」。
