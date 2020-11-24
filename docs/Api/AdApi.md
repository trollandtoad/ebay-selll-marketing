# eBay\Sell\Marketing\AdApi

All URIs are relative to https://api.ebay.com/sell/marketing/v1.

Method | HTTP request | Description
------------- | ------------- | -------------
[**bulkCreateAdsByInventoryReference()**](AdApi.md#bulkCreateAdsByInventoryReference) | **POST** /ad_campaign/{campaign_id}/bulk_create_ads_by_inventory_reference | 
[**bulkCreateAdsByListingId()**](AdApi.md#bulkCreateAdsByListingId) | **POST** /ad_campaign/{campaign_id}/bulk_create_ads_by_listing_id | 
[**bulkDeleteAdsByInventoryReference()**](AdApi.md#bulkDeleteAdsByInventoryReference) | **POST** /ad_campaign/{campaign_id}/bulk_delete_ads_by_inventory_reference | 
[**bulkDeleteAdsByListingId()**](AdApi.md#bulkDeleteAdsByListingId) | **POST** /ad_campaign/{campaign_id}/bulk_delete_ads_by_listing_id | 
[**bulkUpdateAdsBidByInventoryReference()**](AdApi.md#bulkUpdateAdsBidByInventoryReference) | **POST** /ad_campaign/{campaign_id}/bulk_update_ads_bid_by_inventory_reference | 
[**bulkUpdateAdsBidByListingId()**](AdApi.md#bulkUpdateAdsBidByListingId) | **POST** /ad_campaign/{campaign_id}/bulk_update_ads_bid_by_listing_id | 
[**createAdByListingId()**](AdApi.md#createAdByListingId) | **POST** /ad_campaign/{campaign_id}/ad | 
[**createAdsByInventoryReference()**](AdApi.md#createAdsByInventoryReference) | **POST** /ad_campaign/{campaign_id}/create_ads_by_inventory_reference | 
[**deleteAd()**](AdApi.md#deleteAd) | **DELETE** /ad_campaign/{campaign_id}/ad/{ad_id} | 
[**deleteAdsByInventoryReference()**](AdApi.md#deleteAdsByInventoryReference) | **POST** /ad_campaign/{campaign_id}/delete_ads_by_inventory_reference | 
[**getAd()**](AdApi.md#getAd) | **GET** /ad_campaign/{campaign_id}/ad/{ad_id} | 
[**getAds()**](AdApi.md#getAds) | **GET** /ad_campaign/{campaign_id}/ad | 
[**getAdsByInventoryReference()**](AdApi.md#getAdsByInventoryReference) | **GET** /ad_campaign/{campaign_id}/get_ads_by_inventory_reference | 
[**updateBid()**](AdApi.md#updateBid) | **POST** /ad_campaign/{campaign_id}/ad/{ad_id}/update_bid | 


## `bulkCreateAdsByInventoryReference()`

```php
bulkCreateAdsByInventoryReference($campaign_id, $bulk_create_ads_by_inventory_reference_request): \eBay\Sell\Marketing\Model\BulkCreateAdsByInventoryReferenceResponse
```



This method adds multiple listings that are managed with the Inventory API to an existing Promoted Listings campaign. For each listing specified in the request, this method: Creates an ad for the listing. Sets the bid percentage (also known as the ad rate) for the ad. Associates the ad with the specified campaign. To create an ad for a listing, specify its inventoryReferenceId and inventoryReferenceType, plus the bidPercentage for the ad in the payload of the request. Specify the campaign to associate the ads to with using the campaign_id path parameter. In the Inventory API, an inventory reference ID is either a seller-defined SKU value or an inventoryItemGroupKey (a seller-defined ID for a multiple-variation listing). You can specify a maximum of 500 items per call and each campaign can have ads for a maximum of 50,000 items. Be aware when using this call that each variation in a multiple-variation listing creates an individual ad. Use createCampaign to create a new campaign and use getCampaigns to get a list of existing campaigns.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Marketing\Api\AdApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$campaign_id = 'campaign_id_example'; // string | A unique eBay-assigned ID for an ad campaign that's generated when a campaign is created. Get a seller's campaign IDs by calling getCampaigns.
$bulk_create_ads_by_inventory_reference_request = new \eBay\Sell\Marketing\Model\BulkCreateAdsByInventoryReferenceRequest(); // \eBay\Sell\Marketing\Model\BulkCreateAdsByInventoryReferenceRequest | The container for the bulk request to create ads for eBay inventory reference IDs. eBay inventory reference IDs are seller-defined IDs used by theInventory API.

try {
    $result = $apiInstance->bulkCreateAdsByInventoryReference($campaign_id, $bulk_create_ads_by_inventory_reference_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AdApi->bulkCreateAdsByInventoryReference: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **campaign_id** | **string**| A unique eBay-assigned ID for an ad campaign that&#39;s generated when a campaign is created. Get a seller&#39;s campaign IDs by calling getCampaigns. |
 **bulk_create_ads_by_inventory_reference_request** | [**\eBay\Sell\Marketing\Model\BulkCreateAdsByInventoryReferenceRequest**](../Model/BulkCreateAdsByInventoryReferenceRequest.md)| The container for the bulk request to create ads for eBay inventory reference IDs. eBay inventory reference IDs are seller-defined IDs used by theInventory API. |

### Return type

[**\eBay\Sell\Marketing\Model\BulkCreateAdsByInventoryReferenceResponse**](../Model/BulkCreateAdsByInventoryReferenceResponse.md)

### Authorization

[api_auth](../../README.md#api_auth), [api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `bulkCreateAdsByListingId()`

```php
bulkCreateAdsByListingId($campaign_id, $bulk_create_ad_request): \eBay\Sell\Marketing\Model\BulkAdResponse
```



This method adds multiple listings to an existing Promoted Listings campaign using listingId values generated by either the Trading API or Inventory API. For each listing ID specified in the request, this method: Creates an ad for the listing. Sets the bid percentage (also known as the ad rate) for the ad. Associates the ad with the specified campaign. To create an ad for a listing, specify its listingId, plus the bidPercentage for the ad in the payload of the request. Specify the campaign to associate the ads with using the campaign_id path parameter. Listing IDs are generated by eBay when a seller creates listings with the Trading API. You can specify a maximum of 500 listings per call and each campaign can have ads for a maximum of 50,000 items. Be aware when using this call that each variation in a multiple-variation listing creates an individual ad. Use createCampaign to create a new campaign and use getCampaigns to get a list of existing campaigns.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Marketing\Api\AdApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$campaign_id = 'campaign_id_example'; // string | A unique eBay-assigned ID for an ad campaign that's generated when a campaign is created. Get a seller's campaign IDs by calling getCampaigns.
$bulk_create_ad_request = new \eBay\Sell\Marketing\Model\BulkCreateAdRequest(); // \eBay\Sell\Marketing\Model\BulkCreateAdRequest | The container for the bulk request to create ads for eBay listing IDs. eBay listing IDs are generated by the Trading API and Inventory API when the listing is created on eBay.

try {
    $result = $apiInstance->bulkCreateAdsByListingId($campaign_id, $bulk_create_ad_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AdApi->bulkCreateAdsByListingId: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **campaign_id** | **string**| A unique eBay-assigned ID for an ad campaign that&#39;s generated when a campaign is created. Get a seller&#39;s campaign IDs by calling getCampaigns. |
 **bulk_create_ad_request** | [**\eBay\Sell\Marketing\Model\BulkCreateAdRequest**](../Model/BulkCreateAdRequest.md)| The container for the bulk request to create ads for eBay listing IDs. eBay listing IDs are generated by the Trading API and Inventory API when the listing is created on eBay. |

### Return type

[**\eBay\Sell\Marketing\Model\BulkAdResponse**](../Model/BulkAdResponse.md)

### Authorization

[api_auth](../../README.md#api_auth), [api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `bulkDeleteAdsByInventoryReference()`

```php
bulkDeleteAdsByInventoryReference($campaign_id, $bulk_delete_ads_by_inventory_reference_request): \eBay\Sell\Marketing\Model\BulkDeleteAdsByInventoryReferenceResponse
```



This method works with listings created with the Inventory API. The method deletes a set of ads, as specified by a list of inventory reference IDs, from the specified campaign. Inventory reference IDs are seller-defined IDs that are used with the Inventory API. Pass the campaign_id as a path parameter and populate the payload with a list of inventoryReferenceId and inventoryReferenceType pairs that you want to delete. Get the campaign IDs for a seller by calling getCampaigns and call getAds to get a list of the seller's inventory reference IDs.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Marketing\Api\AdApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$campaign_id = 'campaign_id_example'; // string | A unique eBay-assigned ID for an ad campaign that's generated when a campaign is created. Get a seller's campaign IDs by calling getCampaigns.
$bulk_delete_ads_by_inventory_reference_request = new \eBay\Sell\Marketing\Model\BulkDeleteAdsByInventoryReferenceRequest(); // \eBay\Sell\Marketing\Model\BulkDeleteAdsByInventoryReferenceRequest | This request object defines the fields for a bulkDeleteAdsByInventoryReference request.

try {
    $result = $apiInstance->bulkDeleteAdsByInventoryReference($campaign_id, $bulk_delete_ads_by_inventory_reference_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AdApi->bulkDeleteAdsByInventoryReference: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **campaign_id** | **string**| A unique eBay-assigned ID for an ad campaign that&#39;s generated when a campaign is created. Get a seller&#39;s campaign IDs by calling getCampaigns. |
 **bulk_delete_ads_by_inventory_reference_request** | [**\eBay\Sell\Marketing\Model\BulkDeleteAdsByInventoryReferenceRequest**](../Model/BulkDeleteAdsByInventoryReferenceRequest.md)| This request object defines the fields for a bulkDeleteAdsByInventoryReference request. |

### Return type

[**\eBay\Sell\Marketing\Model\BulkDeleteAdsByInventoryReferenceResponse**](../Model/BulkDeleteAdsByInventoryReferenceResponse.md)

### Authorization

[api_auth](../../README.md#api_auth), [api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `bulkDeleteAdsByListingId()`

```php
bulkDeleteAdsByListingId($campaign_id, $bulk_delete_ad_request): \eBay\Sell\Marketing\Model\BulkDeleteAdResponse
```



This method works with listing IDs created with either the Trading API or the Inventory API. The method deletes a set of ads, as specified by a list of listingID values from a Promoted Listings campaign. A listing ID value is generated by eBay when a seller creates a listing with either the Trading API and Inventory API. Pass the campaign_id as a path parameter and populate the payload with the set of listing IDs that you want to delete. Get the campaign IDs for a seller by calling getCampaigns and call getAds to get a list of the seller's inventory reference IDs.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Marketing\Api\AdApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$campaign_id = 'campaign_id_example'; // string | A unique eBay-assigned ID for an ad campaign that's generated when a campaign is created. Get a seller's campaign IDs by calling getCampaigns.
$bulk_delete_ad_request = new \eBay\Sell\Marketing\Model\BulkDeleteAdRequest(); // \eBay\Sell\Marketing\Model\BulkDeleteAdRequest | This request object defines the fields for the bulkDeleteAdsByListingId request.

try {
    $result = $apiInstance->bulkDeleteAdsByListingId($campaign_id, $bulk_delete_ad_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AdApi->bulkDeleteAdsByListingId: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **campaign_id** | **string**| A unique eBay-assigned ID for an ad campaign that&#39;s generated when a campaign is created. Get a seller&#39;s campaign IDs by calling getCampaigns. |
 **bulk_delete_ad_request** | [**\eBay\Sell\Marketing\Model\BulkDeleteAdRequest**](../Model/BulkDeleteAdRequest.md)| This request object defines the fields for the bulkDeleteAdsByListingId request. |

### Return type

[**\eBay\Sell\Marketing\Model\BulkDeleteAdResponse**](../Model/BulkDeleteAdResponse.md)

### Authorization

[api_auth](../../README.md#api_auth), [api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `bulkUpdateAdsBidByInventoryReference()`

```php
bulkUpdateAdsBidByInventoryReference($campaign_id, $bulk_create_ads_by_inventory_reference_request): \eBay\Sell\Marketing\Model\BulkCreateAdsByInventoryReferenceResponse
```



This method works with listings that are managed with the Inventory API. The method updates the bidPercentage values for a set of ads associated with the specified campaign. Specify the campaign_id as a path parameter and supply a list of inventoryReferenceId and inventoryReferenceType pairs with the updated bidPercentage values in the request body. In the Inventory API, an inventory reference ID is either a seller-defined SKU value or an inventoryItemGroupKey (a seller-defined ID for a multiple-variation listing). Get the campaign IDs for a seller by calling getCampaigns and call getAds to get a list of the seller's inventory reference IDs.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Marketing\Api\AdApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$campaign_id = 'campaign_id_example'; // string | A unique eBay-assigned ID for an ad campaign that's generated when a campaign is created. Get a seller's campaign IDs by calling getCampaigns.
$bulk_create_ads_by_inventory_reference_request = new \eBay\Sell\Marketing\Model\BulkCreateAdsByInventoryReferenceRequest(); // \eBay\Sell\Marketing\Model\BulkCreateAdsByInventoryReferenceRequest | This request object defines the fields for the BulkCreateAdsByInventoryReference request.

try {
    $result = $apiInstance->bulkUpdateAdsBidByInventoryReference($campaign_id, $bulk_create_ads_by_inventory_reference_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AdApi->bulkUpdateAdsBidByInventoryReference: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **campaign_id** | **string**| A unique eBay-assigned ID for an ad campaign that&#39;s generated when a campaign is created. Get a seller&#39;s campaign IDs by calling getCampaigns. |
 **bulk_create_ads_by_inventory_reference_request** | [**\eBay\Sell\Marketing\Model\BulkCreateAdsByInventoryReferenceRequest**](../Model/BulkCreateAdsByInventoryReferenceRequest.md)| This request object defines the fields for the BulkCreateAdsByInventoryReference request. |

### Return type

[**\eBay\Sell\Marketing\Model\BulkCreateAdsByInventoryReferenceResponse**](../Model/BulkCreateAdsByInventoryReferenceResponse.md)

### Authorization

[api_auth](../../README.md#api_auth), [api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `bulkUpdateAdsBidByListingId()`

```php
bulkUpdateAdsBidByListingId($campaign_id, $bulk_create_ad_request): \eBay\Sell\Marketing\Model\BulkAdResponse
```



This method works with listings created with either the Trading API or the Inventory API. The method updates the bidPercentage values for a set of ads associated with the specified campaign. Specify the campaign_id as a path parameter and supply a set of listing IDs with their associated updated bidPercentage values in the request body. An eBay listing ID is generated when a listing is created with the Trading API. Get the campaign IDs for a seller by calling getCampaigns and call getAds to get a list of the seller's inventory reference IDs.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Marketing\Api\AdApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$campaign_id = 'campaign_id_example'; // string | A unique eBay-assigned ID for an ad campaign that's generated when a campaign is created. Get a seller's campaign IDs by calling getCampaigns.
$bulk_create_ad_request = new \eBay\Sell\Marketing\Model\BulkCreateAdRequest(); // \eBay\Sell\Marketing\Model\BulkCreateAdRequest | This request object defines the fields for the BulkCreateAdsByListingId request.

try {
    $result = $apiInstance->bulkUpdateAdsBidByListingId($campaign_id, $bulk_create_ad_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AdApi->bulkUpdateAdsBidByListingId: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **campaign_id** | **string**| A unique eBay-assigned ID for an ad campaign that&#39;s generated when a campaign is created. Get a seller&#39;s campaign IDs by calling getCampaigns. |
 **bulk_create_ad_request** | [**\eBay\Sell\Marketing\Model\BulkCreateAdRequest**](../Model/BulkCreateAdRequest.md)| This request object defines the fields for the BulkCreateAdsByListingId request. |

### Return type

[**\eBay\Sell\Marketing\Model\BulkAdResponse**](../Model/BulkAdResponse.md)

### Authorization

[api_auth](../../README.md#api_auth), [api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createAdByListingId()`

```php
createAdByListingId($campaign_id, $create_ad_request): object
```



This method works with listings created with either the Trading API or the Inventory API. The method: Creates an ad for the specified listing ID. Sets the bid percentage (also known as the &quot;ad rate&quot;) for the ad. Associates the ad with the specified campaign. To create an ad for a listing, specify its listingId, plus the bidPercentage for the ad in the payload of the request. Specify the campaign to associate the ad with using the campaign_id path parameter. Listing IDs are generated by eBay when a seller creates listings with the Trading API or Inventory API. Each campaign can have ads for a maximum of 50,000 items, and each item in a multiple-variation listing is considered as an single item. Use createCampaign to create a new campaign and use getCampaigns to get a list of existing campaigns.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Marketing\Api\AdApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$campaign_id = 'campaign_id_example'; // string | A unique eBay-assigned ID for an ad campaign that's generated when a campaign is created. Get a seller's campaign IDs by calling getCampaigns.
$create_ad_request = new \eBay\Sell\Marketing\Model\CreateAdRequest(); // \eBay\Sell\Marketing\Model\CreateAdRequest | This request object defines the fields used in the createAdByListingId request.

try {
    $result = $apiInstance->createAdByListingId($campaign_id, $create_ad_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AdApi->createAdByListingId: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **campaign_id** | **string**| A unique eBay-assigned ID for an ad campaign that&#39;s generated when a campaign is created. Get a seller&#39;s campaign IDs by calling getCampaigns. |
 **create_ad_request** | [**\eBay\Sell\Marketing\Model\CreateAdRequest**](../Model/CreateAdRequest.md)| This request object defines the fields used in the createAdByListingId request. |

### Return type

**object**

### Authorization

[api_auth](../../README.md#api_auth), [api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createAdsByInventoryReference()`

```php
createAdsByInventoryReference($campaign_id, $create_ads_by_inventory_reference_request): \eBay\Sell\Marketing\Model\AdReferences
```



This method works with listings that are managed with the Inventory API. The method: Creates an ad for the specified listing. Sets the bid percentage (also known as the &quot;ad rate&quot;) for the ad. Associates the ad with the specified campaign. To create an ad for a listing, specify its inventoryReferenceId and inventoryReferenceType, plus the bidPercentage for the ad in the payload of the request. Specify the campaign to associate the ad with using the campaign_id path parameter. In the Inventory API, an inventory reference ID is either a seller-defined SKU value or an inventoryItemGroupKey (a seller-defined ID for a multiple-variation listing). Each campaign can have ads for a maximum of 50,000 items, and each item in a multiple-variation listing is considered as an individual item. Use createCampaign to create a new campaign and use getCampaigns to get a list of existing campaigns.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Marketing\Api\AdApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$campaign_id = 'campaign_id_example'; // string | A unique eBay-assigned ID for an ad campaign that's generated when a campaign is created. Get a seller's campaign IDs by calling getCampaigns.
$create_ads_by_inventory_reference_request = new \eBay\Sell\Marketing\Model\CreateAdsByInventoryReferenceRequest(); // \eBay\Sell\Marketing\Model\CreateAdsByInventoryReferenceRequest | This request object defines the fields used in the createAdsByInventoryReference request.

try {
    $result = $apiInstance->createAdsByInventoryReference($campaign_id, $create_ads_by_inventory_reference_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AdApi->createAdsByInventoryReference: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **campaign_id** | **string**| A unique eBay-assigned ID for an ad campaign that&#39;s generated when a campaign is created. Get a seller&#39;s campaign IDs by calling getCampaigns. |
 **create_ads_by_inventory_reference_request** | [**\eBay\Sell\Marketing\Model\CreateAdsByInventoryReferenceRequest**](../Model/CreateAdsByInventoryReferenceRequest.md)| This request object defines the fields used in the createAdsByInventoryReference request. |

### Return type

[**\eBay\Sell\Marketing\Model\AdReferences**](../Model/AdReferences.md)

### Authorization

[api_auth](../../README.md#api_auth), [api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteAd()`

```php
deleteAd($ad_id, $campaign_id)
```



This method removes the specified ad from the specified campaign. Pass the ID of the ad to delete with the ID of the campaign associated with the ad as path parameters to the call. Call getCampaigns to get the current list of the seller's campaign IDs.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Marketing\Api\AdApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$ad_id = 'ad_id_example'; // string | Identifier of an ad. This ID was generated when the ad was created.
$campaign_id = 'campaign_id_example'; // string | A unique eBay-assigned ID for an ad campaign that's generated when a campaign is created. Get a seller's campaign IDs by calling getCampaigns.

try {
    $apiInstance->deleteAd($ad_id, $campaign_id);
} catch (Exception $e) {
    echo 'Exception when calling AdApi->deleteAd: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **ad_id** | **string**| Identifier of an ad. This ID was generated when the ad was created. |
 **campaign_id** | **string**| A unique eBay-assigned ID for an ad campaign that&#39;s generated when a campaign is created. Get a seller&#39;s campaign IDs by calling getCampaigns. |

### Return type

void (empty response body)

### Authorization

[api_auth](../../README.md#api_auth), [api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteAdsByInventoryReference()`

```php
deleteAdsByInventoryReference($campaign_id, $delete_ads_by_inventory_reference_request): \eBay\Sell\Marketing\Model\AdIds
```



This method works with listings that are managed with the Inventory API. The method deletes ads using a list of seller-defined inventory reference IDs, used with the Inventory API, that are associated with the specified campaign ID. Specify the campaign ID (as a path parameter) and a list of inventoryReferenceId and inventoryReferenceType pairs to be deleted. Call getCampaigns to get a list of the seller's current campaign IDs.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Marketing\Api\AdApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$campaign_id = 'campaign_id_example'; // string | A unique eBay-assigned ID for an ad campaign that's generated when a campaign is created. Get a seller's campaign IDs by calling getCampaigns.
$delete_ads_by_inventory_reference_request = new \eBay\Sell\Marketing\Model\DeleteAdsByInventoryReferenceRequest(); // \eBay\Sell\Marketing\Model\DeleteAdsByInventoryReferenceRequest | This request object defines the fields for the deleteAdsByInventoryReference request.

try {
    $result = $apiInstance->deleteAdsByInventoryReference($campaign_id, $delete_ads_by_inventory_reference_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AdApi->deleteAdsByInventoryReference: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **campaign_id** | **string**| A unique eBay-assigned ID for an ad campaign that&#39;s generated when a campaign is created. Get a seller&#39;s campaign IDs by calling getCampaigns. |
 **delete_ads_by_inventory_reference_request** | [**\eBay\Sell\Marketing\Model\DeleteAdsByInventoryReferenceRequest**](../Model/DeleteAdsByInventoryReferenceRequest.md)| This request object defines the fields for the deleteAdsByInventoryReference request. |

### Return type

[**\eBay\Sell\Marketing\Model\AdIds**](../Model/AdIds.md)

### Authorization

[api_auth](../../README.md#api_auth), [api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getAd()`

```php
getAd($ad_id, $campaign_id): \eBay\Sell\Marketing\Model\Ad
```



This method retrieves the specified ad from the specified campaign. In the request, supply the campaign_id and ad_id as path parameters. Call getCampaigns to retrieve a list of the seller's current campaign IDs and call getAds to retrieve their current ad IDs.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Marketing\Api\AdApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$ad_id = 'ad_id_example'; // string | Identifier of an ad. This ID was generated when the ad was created.
$campaign_id = 'campaign_id_example'; // string | A unique eBay-assigned ID for an ad campaign that's generated when a campaign is created. Get a seller's campaign IDs by calling getCampaigns.

try {
    $result = $apiInstance->getAd($ad_id, $campaign_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AdApi->getAd: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **ad_id** | **string**| Identifier of an ad. This ID was generated when the ad was created. |
 **campaign_id** | **string**| A unique eBay-assigned ID for an ad campaign that&#39;s generated when a campaign is created. Get a seller&#39;s campaign IDs by calling getCampaigns. |

### Return type

[**\eBay\Sell\Marketing\Model\Ad**](../Model/Ad.md)

### Authorization

[api_auth](../../README.md#api_auth), [api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getAds()`

```php
getAds($campaign_id, $limit, $listing_ids, $offset): \eBay\Sell\Marketing\Model\AdPagedCollection
```



This method retrieves Promoted Listings ads that are associated with listings created with either the Trading API or the Inventory API. The method retrieves ads related to the specified campaign. Specify the Promoted Listings campaign to target with the campaign_id path parameter. Because of the large number of possible results, you can use query parameters to paginate the result set by specifying a limit, which dictates how many ads to return on each page of the response. You can also specify how many ads to skip in the result set before returning the first result using the offset path parameter. Call getCampaigns to retrieve the current campaign IDs for the seller.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Marketing\Api\AdApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$campaign_id = 'campaign_id_example'; // string | A unique eBay-assigned ID for an ad campaign that's generated when a campaign is created. Get a seller's campaign IDs by calling getCampaigns.
$limit = 'limit_example'; // string | Specifies the maximum number of ads to return on a page in the paginated response. Default: 10 Maximum: 500
$listing_ids = 'listing_ids_example'; // string | A comma separated list of listing IDs. The response includes only active ads (ads associated with a RUNNING campaign). The results do not include listing IDs that are excluded by other conditions.
$offset = 'offset_example'; // string | Specifies the number of ads to skip in the result set before returning the first ad in the paginated response. Combine offset with the limit query parameter to control the items returned in the response. For example, if you supply an offset of 0 and a limit of 10, the first page of the response contains the first 10 items from the complete list of items retrieved by the call. If offset is 10 and limit is 20, the first page of the response contains items 11-30 from the complete result set. Default: 0

try {
    $result = $apiInstance->getAds($campaign_id, $limit, $listing_ids, $offset);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AdApi->getAds: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **campaign_id** | **string**| A unique eBay-assigned ID for an ad campaign that&#39;s generated when a campaign is created. Get a seller&#39;s campaign IDs by calling getCampaigns. |
 **limit** | **string**| Specifies the maximum number of ads to return on a page in the paginated response. Default: 10 Maximum: 500 | [optional]
 **listing_ids** | **string**| A comma separated list of listing IDs. The response includes only active ads (ads associated with a RUNNING campaign). The results do not include listing IDs that are excluded by other conditions. | [optional]
 **offset** | **string**| Specifies the number of ads to skip in the result set before returning the first ad in the paginated response. Combine offset with the limit query parameter to control the items returned in the response. For example, if you supply an offset of 0 and a limit of 10, the first page of the response contains the first 10 items from the complete list of items retrieved by the call. If offset is 10 and limit is 20, the first page of the response contains items 11-30 from the complete result set. Default: 0 | [optional]

### Return type

[**\eBay\Sell\Marketing\Model\AdPagedCollection**](../Model/AdPagedCollection.md)

### Authorization

[api_auth](../../README.md#api_auth), [api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getAdsByInventoryReference()`

```php
getAdsByInventoryReference($campaign_id, $inventory_reference_id, $inventory_reference_type): \eBay\Sell\Marketing\Model\Ads
```



This method retrieves Promoted Listings ads associated with listings that are managed with the Inventory API from the specified campaign. Supply the campaign_id as a path parameter and use query parameters to specify the inventory_reference_id and inventory_reference_type pairs. In the Inventory API, an inventory reference ID is either a seller-defined SKU value or an inventoryItemGroupKey (a seller-defined ID for an inventory item group, which is an entity that's used in the Inventory API to create a multiple-variation listing). To indicate a listing managed by the Inventory API, you must always specify both an inventory_reference_id and the associated inventory_reference_type. Call getCampaigns to retrieve all of the seller's the current campaign IDs.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Marketing\Api\AdApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$campaign_id = 'campaign_id_example'; // string | A unique eBay-assigned ID for an ad campaign that's generated when a campaign is created. Get a seller's campaign IDs by calling getCampaigns.
$inventory_reference_id = 'inventory_reference_id_example'; // string | The inventory reference ID associated with the ad you want returned. A seller's inventory reference ID is the ID of either a listing or the ID of an inventory item group (the parent of a multi-variation listing, such as a shirt that is available in multiple sizes and colors). You must always supply in both an inventory_reference_id and an inventory_reference_type.
$inventory_reference_type = 'inventory_reference_type_example'; // string | The type of the inventory reference ID. Set this value to either INVENTORY_ITEM (a single listing) or INVENTORY_ITEM_GROUP (a multi-variation listing). You must always pass in both an inventory_reference_id and an inventory_reference_type.

try {
    $result = $apiInstance->getAdsByInventoryReference($campaign_id, $inventory_reference_id, $inventory_reference_type);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AdApi->getAdsByInventoryReference: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **campaign_id** | **string**| A unique eBay-assigned ID for an ad campaign that&#39;s generated when a campaign is created. Get a seller&#39;s campaign IDs by calling getCampaigns. |
 **inventory_reference_id** | **string**| The inventory reference ID associated with the ad you want returned. A seller&#39;s inventory reference ID is the ID of either a listing or the ID of an inventory item group (the parent of a multi-variation listing, such as a shirt that is available in multiple sizes and colors). You must always supply in both an inventory_reference_id and an inventory_reference_type. |
 **inventory_reference_type** | **string**| The type of the inventory reference ID. Set this value to either INVENTORY_ITEM (a single listing) or INVENTORY_ITEM_GROUP (a multi-variation listing). You must always pass in both an inventory_reference_id and an inventory_reference_type. |

### Return type

[**\eBay\Sell\Marketing\Model\Ads**](../Model/Ads.md)

### Authorization

[api_auth](../../README.md#api_auth), [api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateBid()`

```php
updateBid($ad_id, $campaign_id, $update_bid_percentage_request)
```



This method updates the bid percentage (also known as the &quot;ad rate&quot;) for the specified ad in the specified campaign. In the request, supply the campaign_id and ad_id as path parameters, and supply the new bidPercentage value in the payload of the call. Call getCampaigns to retrieve a seller's current campaign IDs and call getAds to get their ad IDs.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Marketing\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Marketing\Api\AdApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$ad_id = 'ad_id_example'; // string | A unique eBay-assigned ID for an ad that's generated when an ad is created.
$campaign_id = 'campaign_id_example'; // string | A unique eBay-assigned ID for an ad campaign that's generated when a campaign is created. Get a seller's campaign IDs by calling getCampaigns.
$update_bid_percentage_request = new \eBay\Sell\Marketing\Model\UpdateBidPercentageRequest(); // \eBay\Sell\Marketing\Model\UpdateBidPercentageRequest | This type defines the fields for the updateBid request.

try {
    $apiInstance->updateBid($ad_id, $campaign_id, $update_bid_percentage_request);
} catch (Exception $e) {
    echo 'Exception when calling AdApi->updateBid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **ad_id** | **string**| A unique eBay-assigned ID for an ad that&#39;s generated when an ad is created. |
 **campaign_id** | **string**| A unique eBay-assigned ID for an ad campaign that&#39;s generated when a campaign is created. Get a seller&#39;s campaign IDs by calling getCampaigns. |
 **update_bid_percentage_request** | [**\eBay\Sell\Marketing\Model\UpdateBidPercentageRequest**](../Model/UpdateBidPercentageRequest.md)| This type defines the fields for the updateBid request. |

### Return type

void (empty response body)

### Authorization

[api_auth](../../README.md#api_auth), [api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
