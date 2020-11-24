# # CreateAdsByInventoryReferenceResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ads** | [**\eBay\Sell\Marketing\Model\AdReference[]**](AdReference.md) | A list of ad IDs (based on their inventory reference IDs) and the URIs that point to them. | [optional]
**errors** | [**\eBay\Sell\Marketing\Model\Error[]**](Error.md) | An array of errors or warnings associated with the create-ads request. | [optional]
**inventory_reference_id** | **string** | An ID that identifies an a single-item listing or multiple-variation listing that is managed with the Inventory API. The inventory reference ID is a seller-defined value that can be either an SKU for a single-item listing or an inventoryItemGroupKey for a multiple-value listing. | [optional]
**inventory_reference_type** | **string** | Indicates the type of item the inventoryReferenceId references. The item can be either an INVENTORY_ITEM or INVENTORY_ITEM_GROUP. For implementation help, refer to &lt;a href&#x3D;&#39;https://developer.ebay.com/api-docs/sell/marketing/types/pls:InventoryReferenceTypeEnum&#39;&gt;eBay API documentation&lt;/a&gt; | [optional]
**status_code** | **int** | An HTTP status code that indicates the response-status of the request. Check this code to see if the ads were successful created. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
