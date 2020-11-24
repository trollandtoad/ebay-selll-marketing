# # CampaignCriterion

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**auto_select_future_inventory** | **bool** | Reserved for future use. | [optional]
**criterion_type** | **string** | This enum defines the criterion (selection rule) types. Currently, the only criterion type supported is INVENTORY_PARTITION, and you must specify this value if you manage your items with the Inventory API and you want to include items based on their inventory reference IDs. Leave this field blank if you want to create campaign ads based on listing IDs. For implementation help, refer to &lt;a href&#x3D;&#39;https://developer.ebay.com/api-docs/sell/marketing/types/pls:CriterionTypeEnum&#39;&gt;eBay API documentation&lt;/a&gt; | [optional]
**selection_rules** | [**\eBay\Sell\Marketing\Model\SelectionRule[]**](SelectionRule.md) | Set of rules that selects the listings to include in the campaign. The following rules apply to the selection rules: Each set of selection rules are ORed with each other. Individual rules within a selection rule set are ANDed with each other. If a rule has a list of values (such a list of category IDs), the item need match only one of the values of the rule in order to be included in the campaign. Note: If an item matches multiple sets of rules or multiple rules within a selection rule set, the item is considered only once.Maximum number of rules: 10 | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
