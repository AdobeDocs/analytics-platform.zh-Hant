---
title: 如何在 CJA 中配置 Report Builder 的設定
description: 說明如何設定離線模式、語言、截止日期以及疑難排解設定。
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
exl-id: 32423cb4-1a4c-4ea3-ad4b-9520aff9ae4b
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 100%

---

# Report Builder 設定

使用&#x200B;**設定**&#x200B;窗格配置應用程式層級的設定，例如，UI 顯示的語言或是否在離線模式中運作。這些設定會即刻套用，而且所有未來工作階段都適用相同設定，直到變更為止。

若要變更 Report Builder 設定

1. 按一下&#x200B;**設定**&#x200B;圖示。

1. 變更為「啟用離線模式」，選取語言或啟用「疑難排解紀錄設定」。

1. 按一下&#x200B;**「套用」**。

   ![](./assets/image38.png)

## 離線模式

在離線模式建立和編輯資料區塊時，不會擷取資料。相反地，會使用模擬資料，因此您可以快速建立和編輯資料區塊，無需等候請求才執行。當您重新連上線時，*重新整理資料區塊*&#x200B;命令或是&#x200B;*重新整理所有資料區塊*&#x200B;命令會重新整理您使用實際資料建立的資料區塊。

如欲啟用離線模式

1. 按一下&#x200B;**設定**&#x200B;圖示。

1. 選取&#x200B;**啟用離線模式**。

1. 在&#x200B;**將量度資料顯示為**&#x200B;欄位輸入正整數。

1. 按一下&#x200B;**「套用」**。

## 語言

您可以為 Report Builder UI 選擇語言。所有受支援的 Adobe Analytics 語言都可供選擇。

若要選取在 Report Builder UI 中使用的語言

1. 按一下「設定」。

1. 從&#x200B;**語言**&#x200B;下拉式選單中選取語言。

   ![](./assets/image39.png)

1. 按一下&#x200B;**套用。**

## 疑難排解

使用「疑難排解」設定，將所有用戶端/伺服器資料紀錄在本機檔案中。使用此選項來協助解決支援申請單。

若要啟用「疑難排解」選項，請選取&#x200B;**將 Report Builder 請求紀錄在本機檔案中**。
