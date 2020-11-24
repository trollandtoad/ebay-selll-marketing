# eBay\Sell\Marketing\PromotionSummaryReportApi

All URIs are relative to https://api.ebay.com/sell/marketing/v1.

Method | HTTP request | Description
------------- | ------------- | -------------
[**getPromotionSummaryReport()**](PromotionSummaryReportApi.md#getPromotionSummaryReport) | **GET** /promotion_summary_report | 


## `getPromotionSummaryReport()`

```php
getPromotionSummaryReport($marketplace_id): \eBay\Sell\Marketing\Model\SummaryReportResponse
```



This method generates a report that summarizes the seller's promotions for the specified eBay marketplace. The report returns information on RUNNING, PAUSED, and ENDED promotions (deleted reports are not returned) and summarizes the seller's campaign performance for all promotions on a given site. For information about summary reports, see Reading the item promotion Summary report.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Marketing\Api\PromotionSummaryReportApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$marketplace_id = 'marketplace_id_example'; // string | The eBay marketplace ID of the site you for which you want a promotion summary report. Valid values: EBAY_AU = Australia EBAY_DE = Germany EBAY_ES = Spain EBAY_FR = France EBAY_GB = Great Britain EBAY_IT = Italy EBAY_US = United States

try {
    $result = $apiInstance->getPromotionSummaryReport($marketplace_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PromotionSummaryReportApi->getPromotionSummaryReport: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **marketplace_id** | **string**| The eBay marketplace ID of the site you for which you want a promotion summary report. Valid values: EBAY_AU &#x3D; Australia EBAY_DE &#x3D; Germany EBAY_ES &#x3D; Spain EBAY_FR &#x3D; France EBAY_GB &#x3D; Great Britain EBAY_IT &#x3D; Italy EBAY_US &#x3D; United States |

### Return type

[**\eBay\Sell\Marketing\Model\SummaryReportResponse**](../Model/SummaryReportResponse.md)

### Authorization

[api_auth](../../README.md#api_auth), [api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
