# # DiscountSpecification

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**for_each_amount** | [**\eBay\Sell\Marketing\Model\Amount**](Amount.md) |  | [optional]
**for_each_quantity** | **int** | The number of items that must be purchased in order to qualify for the discount. Valid values: &amp;nbsp; 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, &amp;nbsp; 12, 13, 14, 15, 16, 17, 18, 19 &amp;nbsp; 20, 25, 50, 75, 100 | [optional]
**min_amount** | [**\eBay\Sell\Marketing\Model\Amount**](Amount.md) |  | [optional]
**min_quantity** | **int** | The minimum quantity of promoted items that needs to be bought in order to qualify for the promotion&#39;s discount. Valid values: &amp;nbsp; 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, &amp;nbsp; 12, 13, 14, 15, 16, 17, 18, 19 &amp;nbsp; 20, 25, 50, 75, 100 | [optional]
**number_of_discounted_items** | **int** | Use this field to configure &amp;quot;Buy One Get One&amp;quot; (or BOGO) promotions. You must couple this field with forEachQuantity and an amountOffItem or percentOffItem field to configure your BOGO promotion. This field is not valid with order-based promotions. The value of this field represents the number of items to be discounted when other promotion criteria is met. For example, when the buyer adds the number of items identified by the forEachQuantity value to their cart, they are then eligible to receive the stated discount from an additional number of like items (the number of which is identified by this field) when they add those items to their cart. To receive the discount, the buyer must purchase the number of items indicated by forEachQuantity plus the number indicated by this field. Valid values: &amp;nbsp; 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
