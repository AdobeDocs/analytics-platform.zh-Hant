---
title: 歸因常見問題集
description: 取得歸因相關常見問題的解答。
feature: Attribution
exl-id: 3153d8c9-4ca8-4189-8a2f-511a87e8ac17
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 88%

---

# 歸因常見問題集

>[!NOTE]
>
>您正在檢視 Customer Journey Analytics 中 Analysis Workspace 的相關文件，其功能集與傳統 Adobe Analytics 中的 [Analysis Workspace 略有不同](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant)。[了解更多...](/help/getting-started/cja-aa.md)

**使用歸因時，「無」條列項目代表什麼？**

「無」條列項目是一種全包的項目，代表的是在回顧期間中沒有任何接觸點時發生的所有轉換。請嘗試在報表期間中加入較長的時間範圍。

**我在使用歸因模型時，為何有時會在報表中看到報表期間之外的日期？**

這些額外日期是因訪客報表回顧期間所導致。如需詳細資訊，請參閱 Analytics KB 中的[出現在報表期間之外的資料](https://helpx.adobe.com/tw/analytics/kb/data-appearing-outside-reporting-window.html)。Adobe 預計將在後續版本中篩除這些額外資料列。

**我應該在什麼時機使用「造訪」或「訪客」歸因回顧？**

歸因回顧的選擇取決於您的使用情形。如果轉換需要的時間通常會高於單次造訪，建議使用訪客回顧。建立具有較長訪問時間定義的資料視圖也是一個潛在解決方案。

**使用歸因時，prop 和 eVar 有何差異？**

系統會在報表執行階段重新計算歸因，因此就歸因模型來說，prop 或 eVar (或任何其他維度) 之間並沒有區別。Prop 會持續使用任何回顧期間或歸因模型，而 eVar 配置/到期設定則會受到系統忽略。

**系統不支援哪些維度和量度？**

歸因面板支援所有維度。不支援的量度包括：

* 不重複訪客
* 瀏覽
* 發生次數
* 頁面檢視
* A4T 量度
* 逗留時間量度
* 彈回數
* 跳出率
* 登入點
* 退出點
* 找不到頁面
* 搜尋
* 單頁存取次數
* 單次存取

**屬性如何與篩選器一起使用？**

屬性始終在篩選器之前運行，全局篩選器在應用任何其他報表篩選器之前運行。
