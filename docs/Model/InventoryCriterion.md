# # InventoryCriterion

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**inventory_criterion_type** | **string** | Indicates how the items to include in the promotion are selected. You can include inventory by ID, using rules, or globally include all your inventory. For implementation help, refer to &lt;a href&#x3D;&#39;https://developer.ebay.com/api-docs/sell/marketing/types/sme:InventoryCriterionEnum&#39;&gt;eBay API documentation&lt;/a&gt; | [optional]
**inventory_items** | [**\eBay\Sell\Marketing\Model\InventoryItem[]**](InventoryItem.md) | An array of containers for the seller&#39;s inventory reference IDs (also known as an &amp;quot;SKU&amp;quot; or &amp;quot;custom label&amp;quot;) to be added to the promotion. Note: The request can have either inventoryItems or listingIds, but not both. Required: All listings in a promotion must offer an electronic payment method. Maximum: 500 parent items Maximum SKU or custom label length: 50 characters Required if InventoryCriterionType is set to INVENTORY_BY_VALUE, you must specify either inventoryItems or listingIds. | [optional]
**listing_ids** | **string[]** | An array of eBay listing IDs to be added to the promotion. Note: The request can have either inventoryItems or listingIds, but not both. Required: All listings in a promotion must offer an electronic payment method. Maximum: 500 parent items Maximum SKU or custom label length: 50 characters Required if InventoryCriterionType is set to INVENTORY_BY_VALUE, you must specify either inventoryItems or listingIds. | [optional]
**rule_criteria** | [**\eBay\Sell\Marketing\Model\RuleCriteria**](RuleCriteria.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
