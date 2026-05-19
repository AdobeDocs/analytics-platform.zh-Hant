---
title: Customer Journey Analytics使用的網域
description: 如果貴組織的防火牆封鎖來自 Adobe 的 IP 位址，請使用此清單來更新您的防火牆設定。
role: Admin
exl-id: 0c3e7b2e-cb48-4e14-ae18-65258ebce1b4
autotag-review: '2026-05-19T09:27:11.172Z'
TQID: 'https://experienceleague.adobe.com/y3FgZsfqtozN8IaJlBvmfybUIH3s7fiiw2Rc4iNLyGI'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: d76b9e53-27fb-4597-933f-419cc0dd46dbid: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2: id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 163
ht-degree: 16%

---

# Customer Journey Analytics使用的網域

有些防火牆設定會封鎖Customer Journey Analytics賴以取得產品介面的網域。 您可以使用此網域清單來變更組織的網路設定，以允許從組織內部存取產品。 Adobe建議允許這些網域通過貴組織的防火牆，以獲得最佳體驗。

| 技術 | 網域 |
| --- | --- |
| Customer Journey Analytics網域 | `adobe.com`、`adobe.net`、`adobe.io` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`、`esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| ® Azure Blob儲存 | `awaascicdprodva7.blob.core.windows.net` |
| ® AZURE CDN | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## CX Enterprise網域

除了上述網域外， CX企業版也需仰賴數個網域來收集資料和匯出報表。 如需此網域清單，請參閱[CX Enterprise使用的網域](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains)。

>[!MORELIKETHIS]
>
>Customer Journey Analytics使用的[個IP位址](ip-addresses.md)
>
>CX Enterprise使用的[網域](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains)
