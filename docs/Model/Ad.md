# # Ad

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ad_id** | **string** | A unique eBay-assigned ID for the ad that is generated when the ad is created. | [optional]
**bid_percentage** | **string** | The user-defined bid percentage (also known as the ad rate) sets level to which eBay should raise the visibility of the associated listing across the eBay buyer flows. The value is also used to calculate the Promoted Listings fee. Minimum value: 1.0 Maximum value: 100.0 | [optional]
**inventory_reference_id** | **string** | An ID that identifies an a single-item listing or multiple-variation listing that is managed with the Inventory API. The inventory reference ID is a seller-defined value that can be either an SKU for a single-item listing or an inventoryItemGroupKey for a multiple-value listing. An inventoryItemGroupKey is a value that the seller defines to indicate a listing that&#39;s the parent of a inventory item group (a multiple-variation listing, such as a listing for shirt that&#39;s available in multiple sizes and colors). You must always specify both an inventoryRreferenceId and an inventoryReferenceType to indicate an item that&#39;s managed with the Inventory API. | [optional]
**inventory_reference_type** | **string** | Indicates the type of item the inventoryReferenceId references. The item can be either an INVENTORY_ITEM or INVENTORY_ITEM_GROUP. For implementation help, refer to &lt;a href&#x3D;&#39;https://developer.ebay.com/api-docs/sell/marketing/types/pls:InventoryReferenceTypeEnum&#39;&gt;eBay API documentation&lt;/a&gt; | [optional]
**listing_id** | **string** | A unique eBay-assigned ID that is generated when a listing is created via the Trading API. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
