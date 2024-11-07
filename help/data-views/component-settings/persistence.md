---
title: 持續性元件設定
description: 決定是否會在不同事件中儲存維度值或是如何儲存。
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: d65171873f68835de0628b95158f01713eaacb6b
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 81%

---


# [!UICONTROL 持續性]元件設定 {#persistence-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_dimension_persistence"
>title="持續性"
>abstract="設定套用至維度的預設配置模式。配置會在報告中的篩選器之前套用。如要了解更多資訊，請參閱[配置設定](/help/data-views/component-settings/persistence.md#allocation-settings)、[過期設定](/help/data-views/component-settings/persistence.md#expiration-settings)、[繫結維度](/help/data-views/component-settings/persistence.md#binding-dimension)和繫結量度。"

<!-- markdownlint-enable MD034 -->



[!UICONTROL 持續性]是給定維度值在其設定的事件之外與量度相關的能力。它使用配置和過期時間的組合。

![醒目提示持續性選項的資料檢視視視窗](../assets/persistence.png)

* **配置**&#x200B;可讓您確定當一個列中可以同時保留多個維度項時保留哪個值。

  >[!NOTE]
  >
  >如果您在報表的量度上設定了[非預設歸因模型](/help/data-views/component-settings/attribution.md)，則歸因模型會忽略您在相同報表的維度上設定的配置。
  >
  >但是，執行包含多個維度的[完整資料表匯出](/help/analysis-workspace/export/export-cloud.md)時，歸因會保留套用至每個維度的配置模型。

* **到期日**&#x200B;可讓您確定維度項目在其設定的事件之後持續多長時間。

[!UICONTROL 持續性]僅在維度上可用，並且可追溯至套用到的資料。它是發生在套用篩選或其他分析作業之前的立即資料轉換。

| 設定 | 說明 |
| --- | --- |
| [!UICONTROL 設定持續性] | 啟用維度的持續性。如果未啟用持續性，則維度僅與同一事件中存在的量度相關。此設定預設為停用。 |
| [!UICONTROL 配置] | 可讓您指定用於維度持續性的配置模式。選項包括：「[!UICONTROL 最近]」、「[!UICONTROL 原始]」、「[!UICONTROL 例項]」、「[!UICONTROL 全部]」。2021 年 10 月 28 日起，一個最多 90 天的回顧期間會新增至[!UICONTROL 分配]設定中。 |
| [!UICONTROL 有效期] | 可讓您指定維度的持續性視窗。選項包括：「[!UICONTROL 工作階段]」(預設)、「[!UICONTROL 人員]」、「[!UICONTROL 自訂時間]」、「[!UICONTROL 量度]」。您可能需要能夠使購買的維度到期 (例如內部搜尋詞或其他銷售使用案例)。您可以設定的最長到期時間為 90 天。如果您選取「[!UICONTROL 全部]」配置，則只有[!UICONTROL 工作階段]或[!UICONTROL 人員]到期可用。 |

{style="table-layout:auto"}

## [!UICONTROL 配置]設定

有關可用配置設定的詳細資料。

* **[!UICONTROL 最近]**：儲存最近 (依時間戳記) 存在於維度中的值。維度到期期間內出現的任何後續值都會取代之前的保存值。如果在[「沒有值選項」](no-value-options.md)下在此維度上啟用了「將沒有值視為一個值」，則空值會覆寫以前保存的值。例如，考慮包含[!UICONTROL 最近]的配置和[!UICONTROL 工作階段]到期的下表：

  | 維度 | 點擊 1 | 點擊 2 | 點擊 3 | 點擊 4 | 點擊 5 |
  | --- | --- | --- | --- | --- | --- |
  | 資料集的值 |  | C | B |  | A |
  | 最近配置 |  | C | B | B | A |

* **[!UICONTROL 原始]**：在有效期內儲存存在於維度中的原始值 (依時間戳記)。 如果此維度具有值，則在後續事件中看到不同的值時不會覆寫該維度。例如，考慮包含[!UICONTROL 原始]配置和[!UICONTROL 工作階段]到期的下表：

  | 維度 | 點擊 1 | 點擊 2 | 點擊 3 | 點擊 4 | 點擊 5 |
  | --- | --- | --- | --- | --- | --- |
  | 資料集的值 |  | C | B |  | A |
  | 原始配置 |  | C | C | C | C |

* **[!UICONTROL 全部]**：作用類似於量度的[!UICONTROL 參與率]歸因模式。 平等地保留所有值，因此每個值都可以完全歸功於報告中的量度。例如，考慮包含[!UICONTROL 全部]配置和[!UICONTROL 工作階段]到期的下表：

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

## [!UICONTROL 到期]設定

有關可用到期設定的詳細資料。

* **工作階段**：在指定的工作階段後過期。預設到期窗口。
* **人員**：在您的報告期間結束時到期。
* **自訂時間**：在指定的時段 (最長 90 天) 後到期。這個到期選項僅適用於「原始」和「最近」配置模式。 在使用以時間為準的有效期時，將會考量您的報告期間 (最長 90 天) 開始前的值。
* **量度**：在事件中看到此量度時，請讓維度中的儲存值立即過期。 您可以使用量度當做此維度的到期點。 這個到期選項僅適用於「原始」和「最近」配置設定。

## [!UICONTROL 繫結維度]

一個下拉式清單，可讓您將維度值的持續性繫結到另一個維度中的維度值。 有效選項包含在資料檢視中的其他維度。

如需有關如何有效使用繫結維度的範例，請參閱[在Customer Journey Analytics](../../use-cases/data-views/binding-dimensions-metrics.md)中使用繫結維度和量度。

>[!VIDEO](https://video.tv.adobe.com/v/342694/?quality=12)

## [!UICONTROL 繫結量度]

下拉式清單可讓您選擇做為繫結觸發器的量度。 有效選項包含在資料檢視中的量度。

此項設定只會在繫結維度在物件陣列中小於元件時出現。繫結量度存在於事件中時，維度值會從事件水準維度複製到繫結維度的下層結構描述。

如需有關如何有效使用繫結維度的詳細資訊，請參閱[在Customer Journey Analytics](../../use-cases/data-views/binding-dimensions-metrics.md)中使用繫結維度和量度下的第二個範例。
