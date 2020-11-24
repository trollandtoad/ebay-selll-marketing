# # Error

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**category** | **string** | The category type for this error or warning. This field can have one of three values: Application: Indicates an exception or error occurred in the application code or at runtime. Examples include catching an exception in a service&#39;s business logic, system failures, or request errors from a dependency. Business: Used when your service or a dependent service refused to continue processing on the resource because of a business rule violation such as &amp;quot;Seller does not ship items to Antarctica&amp;quot; or &amp;quot;Buyer ineligible to purchase an alcoholic item&amp;quot;. Business errors are not syntactical input errors. Request: Used when there is anything wrong with the request, such as authentication, syntactical errors, rate limiting or missing headers, bad HTTP header values, and so on. | [optional]
**domain** | **string** | The name of the primary system where the error occurred. This is relevant for application errors. | [optional]
**error_id** | **int** | A positive integer that uniquely identifies the specific error condition that occurred. Your application can use error codes as identifiers in your customized error-handling algorithms. | [optional]
**input_ref_ids** | **string[]** | An array of reference IDs that identify the specific request elements most closely associated to the error or warning, if any. For JSON, use JSONPath notation. | [optional]
**long_message** | **string** | A detailed description of the condition that caused the error or warning and information on what to do to correct the problem. The string is normally 100-200 characters in length, but is not required to be such. | [optional]
**message** | **string** | A short description of the condition that caused the error or warning. This value is at most 50 characters long and, if applicable, is localized in the end user&#39;s requested locale. | [optional]
**output_ref_ids** | **string[]** | An array of reference IDs that identify the specific response elements most closely associated to the error or warning, if any. The path format is the same as inputRefId. | [optional]
**parameters** | [**\eBay\Sell\Marketing\Model\ErrorParameter[]**](ErrorParameter.md) | An array that contains contextual information about the error or warning. The list often includes the parameter or input fields that triggered the warning or error condition. | [optional]
**subdomain** | **string** | The name of the subdomain in which the error or warning occurred. For example, checkout is a subdomain in the buying domain. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
