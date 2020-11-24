# eBay\Sell\Marketing\PromotionReportApi

All URIs are relative to https://api.ebay.com/sell/marketing/v1.

Method | HTTP request | Description
------------- | ------------- | -------------
[**getPromotionReports()**](PromotionReportApi.md#getPromotionReports) | **GET** /promotion_report | 


## `getPromotionReports()`

```php
getPromotionReports($marketplace_id, $limit, $offset, $promotion_status, $promotion_type, $q): \eBay\Sell\Marketing\Model\PromotionsReportPagedCollection
```



This method generates a report that lists the seller's running, paused, and ended promotions for the specified eBay marketplace. The result set can be filtered by the promotion status and the number of results to return. You can also supply keywords to limit the report to promotions that contain the specified keywords. Specify the eBay marketplace for which you want the report run using the marketplace_id query parameter. Supply additional query parameters to control the report as needed.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Marketing\Api\PromotionReportApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$marketplace_id = 'marketplace_id_example'; // string | The eBay marketplace ID of the site for which you want the promotions report. Valid values: EBAY_AU = Australia EBAY_DE = Germany EBAY_ES = Spain EBAY_FR = France EBAY_GB = Great Britain EBAY_IT = Italy EBAY_US = United States
$limit = 'limit_example'; // string | Specifies the maximum number of promotions returned on a page from the result set. Default: 200 Maximum: 200
$offset = 'offset_example'; // string | Specifies the number of promotions to skip in the result set before returning the first promotion in the paginated response. Combine offset with the limit query parameter to control the items returned in the response. For example, if you supply an offset of 0 and a limit of 10, the first page of the response contains the first 10 items from the complete list of items retrieved by the call. If offset is 10 and limit is 20, the first page of the response contains items 11-30 from the complete result set. Default: 0
$promotion_status = 'promotion_status_example'; // string | Limits the results to the promotions that are in the state specified by this query parameter. Valid values: DRAFT SCHEDULED RUNNING PAUSED ENDEDMaximum number of values supported: 1
$promotion_type = 'promotion_type_example'; // string | Filters the returned promotions in the report based on their campaign promotion type. Specify one of the following values to indicate the promotion type you want returned in the report: MARKDOWN_SALE &ndash; A markdown promotion set with createItemPriceMarkdownPromotion. ORDER_DISCOUNT &ndash; A threshold promotion set with createItemPromotion. VOLUME_DISCOUNT &ndash; A volume pricing promotion set with createItemPromotion.
$q = 'q_example'; // string | A string consisting of one or more keywords. eBay filters the response by returning only the promotions that contain the supplied keywords in the promotion title. Example: &quot;iPhone&quot; or &quot;Harry Potter.&quot; Commas that separate keywords are ignored. For example, a keyword string of &quot;iPhone, iPad&quot; equals &quot;iPhone iPad&quot;, and each results in a response that contains promotions with both &quot;iPhone&quot; and &quot;iPad&quot; in the title.

try {
    $result = $apiInstance->getPromotionReports($marketplace_id, $limit, $offset, $promotion_status, $promotion_type, $q);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PromotionReportApi->getPromotionReports: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **marketplace_id** | **string**| The eBay marketplace ID of the site for which you want the promotions report. Valid values: EBAY_AU &#x3D; Australia EBAY_DE &#x3D; Germany EBAY_ES &#x3D; Spain EBAY_FR &#x3D; France EBAY_GB &#x3D; Great Britain EBAY_IT &#x3D; Italy EBAY_US &#x3D; United States |
 **limit** | **string**| Specifies the maximum number of promotions returned on a page from the result set. Default: 200 Maximum: 200 | [optional]
 **offset** | **string**| Specifies the number of promotions to skip in the result set before returning the first promotion in the paginated response. Combine offset with the limit query parameter to control the items returned in the response. For example, if you supply an offset of 0 and a limit of 10, the first page of the response contains the first 10 items from the complete list of items retrieved by the call. If offset is 10 and limit is 20, the first page of the response contains items 11-30 from the complete result set. Default: 0 | [optional]
 **promotion_status** | **string**| Limits the results to the promotions that are in the state specified by this query parameter. Valid values: DRAFT SCHEDULED RUNNING PAUSED ENDEDMaximum number of values supported: 1 | [optional]
 **promotion_type** | **string**| Filters the returned promotions in the report based on their campaign promotion type. Specify one of the following values to indicate the promotion type you want returned in the report: MARKDOWN_SALE &amp;ndash; A markdown promotion set with createItemPriceMarkdownPromotion. ORDER_DISCOUNT &amp;ndash; A threshold promotion set with createItemPromotion. VOLUME_DISCOUNT &amp;ndash; A volume pricing promotion set with createItemPromotion. | [optional]
 **q** | **string**| A string consisting of one or more keywords. eBay filters the response by returning only the promotions that contain the supplied keywords in the promotion title. Example: &amp;quot;iPhone&amp;quot; or &amp;quot;Harry Potter.&amp;quot; Commas that separate keywords are ignored. For example, a keyword string of &amp;quot;iPhone, iPad&amp;quot; equals &amp;quot;iPhone iPad&amp;quot;, and each results in a response that contains promotions with both &amp;quot;iPhone&amp;quot; and &amp;quot;iPad&amp;quot; in the title. | [optional]

### Return type

[**\eBay\Sell\Marketing\Model\PromotionsReportPagedCollection**](../Model/PromotionsReportPagedCollection.md)

### Authorization

[api_auth](../../README.md#api_auth), [api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
