---
source-git-commit: f97439676c61acf1b6ba8818ef1d06542402e675
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 9%

---
# AAID、ECID、ACUSTOMID和分析源連接器

Adobe Analytics資料包含多個標識欄位。 在Matlab中對3個重要的身份域給予了特殊處理 [分析源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant):

* **AAID** 是Adobe Analytics的主設備標識符，並保證在通過分析源連接器的每個事件上都存在。 AAID有時稱為「舊式分析ID」或「s\_vi cookie id」，儘管即使s\_vicookie不存在，也會建立AAID。 AAID由 **_post\_visid\_high/post\_visid\_low_** 列 [Adobe Analytics資料源](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=zh-Hant#columns%2C-descriptions%2C-and-data-types)。 在分析源連接器中，AAID將轉換為 **HEX(post_visid_high)+ &quot;-&quot; + HEX(host_visid_low)**。 給定事件上的AAID欄位包含單個標識，該標識可能是中所述的幾種不同類型之一 [分析ID的操作順序](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html?lang=en%5B%5D)。 (在整個報告套件中， AAID可能包含各種事件的類型。 每個命中項的類型在 **_[帖子\_]visid\_type_** 分析資料源中的列。) 另請參閱： [資料列引用](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=zh-Hant)。
* **ECID** (Experience CloudID)，有時也稱為MCID(Marketing CloudID)，是一個單獨的設備標識符欄位，當使用MCID實現Adobe Analytics時，該欄位在Adobe Analytics填充 [Experience Cloud身份服務](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=zh-Hant)。 ECID由 **_麥克維斯_** Adobe Analytics資料源。 如果事件上存在ECID，則AAID可能基於ECID，具體取決於分析 [寬限期](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html?lang=zh-Hant) 已配置。 另請參閱： [分析和Experience CloudID請求](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html?lang=en)。
* **穴蛛** 是一個單獨的標識符欄位，它根據在分析實現中使用s.VisitorID變數在Adobe Analytics填充。 AACUSTOMID由 **_cust_visid_** Adobe Analytics資料源。 如果存在AACUSTOMID,AAID將基於AACUSTOMID。 （AACUSTOMID比上述操作順序所定義的所有其它標識符要好。）

分析源連接器以XDM形式將這些標識傳遞給AEP，如下所示：

* endUserID。\_experience.aaid.id
* endUserID。\_experience.mcid.id
* endUserID。\_experience.aacustomid.id

這些欄位未標籤為標識。 相反，相同的身份被複製到XDM **_標識映射_** 按鍵值對顯示：

* { &quot;key&quot;:&quot;AAID&quot;、&quot;value&quot;: [ { &quot;id&quot;:&quot;**_\&lt;identity>_**&quot;,&quot;primary&quot;: **_\&lt;true or=&quot;&quot; false=&quot;&quot;>_**} ] }
* { &quot;key&quot;:&quot;ECID&quot;、&quot;value&quot;: [ { &quot;id&quot;:&quot;**_\&lt;identity>_**&quot;,&quot;primary&quot;: **_\&lt;true or=&quot;&quot; false=&quot;&quot;>_** } ] }
* { &quot;key&quot;:&quot;Aacustomid&quot;, &quot;value&quot;: [ { &quot;id&quot;:&quot;**_\&lt;identity>_**&quot;,&quot;primary&quot;: **假** } ] }

在identityMap中：

* 如果存在ECID，則將其標籤為事件的主標識。 請注意，在此情況下，AAID可能基於上述討論中的ECID。
否則，AAID將標籤為事件的主標識。
* AACUSTOMID從未標籤為事件的主ID。 但是，如果存在AACUSTOMID，則AAID基於AACUSTOMID，如上述討論所述。

就CJA而言，只有最終用戶決定將主ID用作人員ID時，主ID的定義才重要。 然而，這樣做並非強制性的。 用戶可以選擇其他標識列作為「人員ID」。

