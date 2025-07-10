# BulkProcessStatusRequest


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**process_status_queries** | [**List[ProcessStatusId]**](ProcessStatusId.md) |  | 

## Example

```python
from bol_shared_api_client.models.bulk_process_status_request import BulkProcessStatusRequest

# TODO update the JSON string below
json = "{}"
# create an instance of BulkProcessStatusRequest from a JSON string
bulk_process_status_request_instance = BulkProcessStatusRequest.from_json(json)
# print the JSON string representation of the object
print(BulkProcessStatusRequest.to_json())

# convert the object into a dict
bulk_process_status_request_dict = bulk_process_status_request_instance.to_dict()
# create an instance of BulkProcessStatusRequest from a dict
bulk_process_status_request_from_dict = BulkProcessStatusRequest.from_dict(bulk_process_status_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


