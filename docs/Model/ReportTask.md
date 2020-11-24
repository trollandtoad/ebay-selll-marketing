# # ReportTask

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**campaign_ids** | **string[]** | A list of campaign IDs to be included in the report. A campaign ID is a unique eBay-assigned identifier of the campaign that&#39;s generated when the campaign is created. Call getCampaigns to return the current campaign IDs for a seller. Note: Currently, you can specify only one campaign ID. | [optional]
**date_from** | **string** | The date defining the start of the timespan covered by the report, in ISO 8601 UTC format. Promoted Listings reports are aggregated on a daily basis where each day begins and ends at midnight, Mountain Standard Time (MST). This time is calculated by subtracting seven hours from the Coordinated Universal Time (UTC). | [optional]
**date_to** | **string** | The date defining the end of the timespan covered by the report, in ISO 8601 UTC format. Promoted Listings reports are aggregated on a daily basis where each day begins and ends at midnight, Mountain Standard Time (MST). | [optional]
**dimensions** | [**\eBay\Sell\Marketing\Model\Dimension[]**](Dimension.md) | A list containing the dimension in the report. | [optional]
**inventory_references** | [**\eBay\Sell\Marketing\Model\InventoryReference[]**](InventoryReference.md) | If supplied in the request, this field returns a list of the seller&#39;s inventory reference IDs included in the report. Each item is referenced by a pair of and inventoryReferenceType values, where an inventory reference ID can be either a seller-defined SKU value or an inventoryItemGroupKey. An inventoryItemGroupKey is seller-defined ID for an inventory item group (a multiple-variation listing), and is created and used by the Inventory API. | [optional]
**listing_ids** | **string[]** | If supplied in the request, this field returns a list of the listing IDs included in the report. A listing ID is an eBay-assigned ID that&#39;s generated when a listing is created. | [optional]
**marketplace_id** | **string** | The ID of the eBay marketplace used by the report task. For implementation help, refer to &lt;a href&#x3D;&#39;https://developer.ebay.com/api-docs/sell/marketing/types/ba:MarketplaceIdEnum&#39;&gt;eBay API documentation&lt;/a&gt; | [optional]
**metric_keys** | **string[]** | A list of metrics for the report task. | [optional]
**report_expiration_date** | **string** | The date after which the report is no longer be available. Reports are available for 30 days and you cannot download a report after it has expired. Format (UTC): yyyy-MM-ddThh:mm:ss.sssZ | [optional]
**report_format** | **string** | Indicates the format of the report. Currently, only TSV_GZIP is supported. For implementation help, refer to &lt;a href&#x3D;&#39;https://developer.ebay.com/api-docs/sell/marketing/types/plr:ReportFormatEnum&#39;&gt;eBay API documentation&lt;/a&gt; | [optional]
**report_href** | **string** | The URL of the generated report, which can be used to download the report once it has been generated. | [optional]
**report_id** | **string** | A unique eBay-assigned ID for the report. | [optional]
**report_name** | **string** | An eBay-assigned name for the report that&#39;s created by the createReportTask call. This name is unique for the seller. | [optional]
**report_task_completion_date** | **string** | The date the report task completed the report generation. Format (UTC): yyyy-MM-ddThh:mm:ss.sssZ | [optional]
**report_task_creation_date** | **string** | The date the report task was created. Format (UTC): yyyy-MM-ddThh:mm:ss.sssZ | [optional]
**report_task_expected_completion_date** | **string** | The date the report task is expected to complete the report generation. Format (UTC): yyyy-MM-ddThh:mm:ss.sssZ | [optional]
**report_task_id** | **string** | The unique eBay-assigned ID of the report task. This value is generated when the report task is created with a call to createReportTask. | [optional]
**report_task_status** | **string** | Indicates the current state of the report task. For implementation help, refer to &lt;a href&#x3D;&#39;https://developer.ebay.com/api-docs/sell/marketing/types/plr:TaskStatusEnum&#39;&gt;eBay API documentation&lt;/a&gt; | [optional]
**report_task_status_message** | **string** | A status message with additional information about the report task. | [optional]
**report_type** | **string** | Indicates type of report associated with the report task. For implementation help, refer to &lt;a href&#x3D;&#39;https://developer.ebay.com/api-docs/sell/marketing/types/plr:ReportTypeEnum&#39;&gt;eBay API documentation&lt;/a&gt; | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
