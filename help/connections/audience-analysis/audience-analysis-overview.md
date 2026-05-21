---
title: Audience Analysis概述
description: 瞭解如何在Customer Journey Analytics中從RTCDP分析對象。
solution: Customer Journey Analytics
feature: Audiences
role: Admin
exl-id: 1e962f52-6b56-4671-afea-d58dae67e8a8
autotag-review: '2026-05-19T10:43:44.564Z'
TQID: 'https://experienceleague.adobe.com/Glq5cGUw910uanF1Blgj5E-Fzo1Ycn26VzZvNRwxpLE'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 752
ht-degree: 5%

---

# 對象分析概觀

>[!NOTE]
>
>瞭解對象分析與對象發佈之間的差異：
>
>* **對象分析**：可讓您將Experience Platform設定檔資料集中的對象會籍資料擷取到Customer Journey Analytics連線。
>* **對象發佈**：可讓您建立在Customer Journey Analytics中發現的對象，並將其發佈到Adobe Experience Platform，以用於客戶目標定位和個人化。 如需對象發佈的相關資訊，請參閱[對象發佈概觀](/help/components/audiences/audiences-overview.md)。

對象分析可讓您將對象成員資格資料從Experience Platform設定檔資料集擷取到Customer Journey Analytics連線。 客群會變為可用的新維度，以便在 Analysis Workspace 中使用。

下圖和相關表格高階展示Customer Journey Analytics中的對象分析設定如何讓Experience Platform對象資料可在Analysis Workspace中使用：

![對象分析總覽](assets/audience-analysis-overview.png)

| 數字 | 功能 | 函數 |
|---------|----------|---------|
| 1 | 對象分析設定 | Customer Journey Analytics中用於設定受眾分析的設定介面。 |
| 2 | 沙箱 | 必須包含您想要新增至連線的設定檔資料集。 |
| 3 | 輪廓資料集 | 必須包含您要分析的Experience Platform對象資料。 此設定檔資料集已新增至您選取的連線。 |
| 4 | 合併原則 | 與您要分析之Experience Platform對象相關聯的合併原則。 |
| 5 | 設定檔資料 | 與您選取的合併原則相關聯的設定檔資料。 此資料可在Experience Platform資料集中使用。 |
| 6 | 新查詢資料集 | 為建立的新對象維度提供易記名稱。 <p>系統會自動建立查詢資料集，並將其新增至連線，以及您選取的設定檔資料集。</p> |
| 7 | 連線 | 您要新增所選取設定檔資料集的連線。 |
| 8 | 新受眾維度 | 新的對象維度<!--and metrics?-->代表您選取之設定檔資料集中所包含的Experience Platform對象，且可用於Analysis Workspace中的報告。 系統會自動建立這些維度。 |
| 9 | 資料檢視 | 您選取的與連線相關聯的資料檢視。 在Analysis Workspace中分析Experience Platform受眾資料時，您想要使用這些資料檢視。 這些資料檢視會自動設定用於報表的Experience Platform受眾資料。 |

## 設定客群分析

設定對象分析時，您會選取與您要分析之Experience Platform對象相關聯的沙箱和合併原則。 Customer Journey Analytics會建立新的查詢資料集，然後自動將查詢資料集和設定檔資料集新增到您選擇的連線。

>[!IMPORTANT]
>
>對象資料會每晚重新處理和產生，因此對象資料僅供前一天（「昨天」）的分析使用。
>
>在您建立對象分析設定後的次日，便可在Customer Journey Analytics資料檢視中使用對象。

如需詳細資訊，請參閱[設定對象分析](/help/connections/audience-analysis/audience-analysis-configure.md)。

## 管理對象分析設定

您可以在對象分析設定建立後加以管理。 您可以檢視、編輯和刪除組態。

如需有關管理現有對象分析設定的資訊，請參閱[管理對象分析設定](/help/connections/audience-analysis/audience-analysis-manage.md)。

## 在Customer Journey Analytics中分析受眾資料

有了Customer Journey Analytics提供的受眾資料，您就可以針對受眾成員在不同管道中的行為方式獲得可行的深入分析。

例如，您可以追蹤包含在相同電子郵件促銷活動中的個別客戶的行為。 有了Customer Journey Analytics提供的對象，您可以看到有關每個對象成員的下列資訊：

* 從電子郵件點進至網站，最後導致購買

* 最終進行店內購買的受眾成員

如需詳細資訊，請參閱[在Customer Journey Analytics中分析Experience Platform對象](/help/connections/audience-analysis/analyze-audiences.md)。

## 對象分析角色和許可權需求

對象分析需要下列Customer Journey Analytics角色和Experience Platform許可權：

| 功能 | Customer Journey Analytics角色或許可權需求 | Experience Platform許可權需求 |
|---------|----------|----------|
| [建立對象分析設定](/help/connections/audience-analysis/audience-analysis-configure.md) | 系統管理員 | <ul><li>資料集：讀取許可權</li><li>結構描述：讀取、寫入</li><li>身分名稱空間：讀取</li></ul> |
| [在資料檢視中檢視對象分析維度](/help/connections/audience-analysis/audience-analysis-configure.md#view-audience-dimensions-in-the-data-view) | 指派資料檢視的產品設定檔的產品設定檔管理員 <p>如需詳細資訊，請參閱[存取控制](/help/technotes/access-control.md)。</p> | 不適用 |
| 在Analysis Workspace中使用對象分析維度 | 存取已新增對象分析維度的資料檢視 | 不適用 |

## 對象分析使用案例

如需強調Audience Analysis所提供值的使用案例範例，請參閱[Audience Analysis使用案例](/help/connections/audience-analysis/audience-analysis-use-cases.md)。

## 對象分析限制

在[設定對象分析](/help/connections/audience-analysis/audience-analysis-configure.md)時，請考量下列限制：

* 單一沙箱可支援最多100個對象分析設定。

* 一個連線只能與一個對象分析設定相關聯。
