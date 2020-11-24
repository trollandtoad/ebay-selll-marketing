# eBay\Sell\Marketing\AdReportMetadataApi

All URIs are relative to https://api.ebay.com/sell/marketing/v1.

Method | HTTP request | Description
------------- | ------------- | -------------
[**getReportMetadata()**](AdReportMetadataApi.md#getReportMetadata) | **GET** /ad_report_metadata | 
[**getReportMetadataForReportType()**](AdReportMetadataApi.md#getReportMetadataForReportType) | **GET** /ad_report_metadata/{report_type} | 


## `getReportMetadata()`

```php
getReportMetadata(): \eBay\Sell\Marketing\Model\ReportMetadatas
```



This call retrieves information that details the fields used in each of the Promoted Listings reports. Use the returned information to configure the different types of Promoted Listings reports. The request for this method does not use a payload or any URI parameters.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Marketing\Api\AdReportMetadataApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getReportMetadata();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AdReportMetadataApi->getReportMetadata: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\eBay\Sell\Marketing\Model\ReportMetadatas**](../Model/ReportMetadatas.md)

### Authorization

[api_auth](../../README.md#api_auth), [api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getReportMetadataForReportType()`

```php
getReportMetadataForReportType($report_type): \eBay\Sell\Marketing\Model\ReportMetadata
```



This call retrieves metadata that details the fields used by a specific Promoted Listings report type. Use the report_type path parameter to indicate metadata to retrieve. This method does not use a request payload.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Marketing\Api\AdReportMetadataApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$report_type = 'report_type_example'; // string | The name of the report type whose metadata you want to get. For details about each report type, see ReportTypeEnum. Valid values: &nbsp;&nbsp;&nbsp;ACCOUNT_PERFORMANCE_REPORT &nbsp;&nbsp;&nbsp;CAMPAIGN_PERFORMANCE_REPORT &nbsp;&nbsp;&nbsp;CAMPAIGN_PERFORMANCE_SUMMARY_REPORT &nbsp;&nbsp;&nbsp;LISTING_PERFORMANCE_REPORT &nbsp;&nbsp;&nbsp;INVENTORY_PERFORMANCE_REPORT

try {
    $result = $apiInstance->getReportMetadataForReportType($report_type);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AdReportMetadataApi->getReportMetadataForReportType: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **report_type** | **string**| The name of the report type whose metadata you want to get. For details about each report type, see ReportTypeEnum. Valid values: &amp;nbsp;&amp;nbsp;&amp;nbsp;ACCOUNT_PERFORMANCE_REPORT &amp;nbsp;&amp;nbsp;&amp;nbsp;CAMPAIGN_PERFORMANCE_REPORT &amp;nbsp;&amp;nbsp;&amp;nbsp;CAMPAIGN_PERFORMANCE_SUMMARY_REPORT &amp;nbsp;&amp;nbsp;&amp;nbsp;LISTING_PERFORMANCE_REPORT &amp;nbsp;&amp;nbsp;&amp;nbsp;INVENTORY_PERFORMANCE_REPORT |

### Return type

[**\eBay\Sell\Marketing\Model\ReportMetadata**](../Model/ReportMetadata.md)

### Authorization

[api_auth](../../README.md#api_auth), [api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
