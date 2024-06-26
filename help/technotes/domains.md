---
title: Customer Journey Analytics使用的網域
description: 如果貴組織的防火牆封鎖來自 Adobe 的 IP 位址，請使用此清單來更新您的防火牆設定。
role: Admin
source-git-commit: 43bda939a5464c5f65b0a050ccfdb5ba17f7d34b
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 20%

---

# Customer Journey Analytics使用的網域

有些防火牆設定會封鎖Customer Journey Analytics賴以取得其產品介面的網域。 您可以使用此網域清單來變更組織的網路設定，以允許從組織內部存取產品。 Adobe建議允許這些網域通過貴組織的防火牆，以獲得最佳體驗。

| 技術 | 網域 |
| --- | --- |
| Customer Journey Analytics網域 | `adobe.com`、`adobe.net`、`adobe.io` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`、`esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Microsoft® Azure Blob儲存體 | `awaascicdprodva7.blob.core.windows.net` |
| Microsoft® Azure CDN | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## Adobe Experience Cloud 網域

除了上述網域外，Adobe Experience Cloud還仰賴數個網域進行資料收集和匯出報表。 另請參閱 [Adobe Experience Cloud使用的網域](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains) 用於此網域清單。

>[!MORELIKETHIS]
>
>[Customer Journey Analytics使用的IP位址](ip-addresses.md)
>
>[Adobe Experience Cloud使用的網域](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains)