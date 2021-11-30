---
title: 歸因元件設定
description: 允許您為量度設定預設歸因。
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 100%

---

# 歸因元件設定

歸因可讓您為量度設定預設歸因模型。在 Analysis Workspace 中工作時，您可以覆寫給定量度的歸因模型。

![歸因](../assets/attribution-settings.png)

| 設定 | 說明/使用案例 |
| --- | --- |
| [!UICONTROL 設定歸因] | 使用此量度時啟用預設歸因模型。可以在[!UICONTROL 自由表格]或計算量度中覆寫此預設值。 |
| [!UICONTROL 歸因模型] | 允許您指定要使用的預設[歸因模型](/help/analysis-workspace/attribution/models.md)。預設為 「[!UICONTROL 上次接觸]」。選項包括：「上次接觸」、「首次接觸」、「線性」、「參與率」、「相同接觸」、「U 形」、「J 曲線」、「反 J」、「時間衰減」、「自訂」、「演算法」。有些選項會建立其他需要填寫的欄位，例如「自訂」或「時間衰減」。您可以使用相同欄位建立多個量度，這表示您可以有一個「[!UICONTROL 上次接觸]」收入量度和一個「[!UICONTROL 首次接觸]」收入量度，但是以結構中相同的收入欄位為基礎。 |
| [!UICONTROL 回顧視窗] | 允許您指定量度的預設回顧視窗。選項包括：「[!UICONTROL 人員]」(報告視窗)、「[!UICONTROL 工作階段]」、「[!UICONTROL 自訂]」。 在選取「[!UICONTROL 自訂]」時，我們也會提供您選項來選取任何天數/週數/月數等 (最多 90 天)，如同 [!UICONTROL Attribution IQ]。 您可以使用相同的結構欄位來擁有多個量度，但每個量度都有個別的回顧視窗。 |
