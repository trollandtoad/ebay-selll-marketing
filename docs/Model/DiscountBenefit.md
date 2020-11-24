# # DiscountBenefit

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**amount_off_item** | [**\eBay\Sell\Marketing\Model\Amount**](Amount.md) |  | [optional]
**amount_off_order** | [**\eBay\Sell\Marketing\Model\Amount**](Amount.md) |  | [optional]
**percentage_off_item** | **string** | The percentage applied to the sales price that is discounted off the promoted item (or items) when the promotion criteria is met. Valid integer values for percentage off: &amp;nbsp;&amp;nbsp;Min: 5 &amp;nbsp;&amp;nbsp;Max: 80 | [optional]
**percentage_off_order** | **string** | Used for threshold promotions, this is the percentage of the order price that is discounted off the order when the promotion criteria is met. This field is not value for markdown promotions. Valid integer values for ORDER_DISCOUNT promotions: &amp;nbsp;&amp;nbsp;Min: 5 &amp;nbsp;&amp;nbsp;Max: 80 For VOLUME_DISCOUNT promotions: Must be set to 0 for the first discount rule. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
