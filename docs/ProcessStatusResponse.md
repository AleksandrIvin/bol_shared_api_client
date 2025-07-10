# ProcessStatusResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**process_statuses** | [**List[ProcessStatus]**](ProcessStatus.md) |  | 

## Example

```python
from bol_shared_api_client.models.process_status_response import ProcessStatusResponse

# TODO update the JSON string below
json = "{}"
# create an instance of ProcessStatusResponse from a JSON string
process_status_response_instance = ProcessStatusResponse.from_json(json)
# print the JSON string representation of the object
print(ProcessStatusResponse.to_json())

# convert the object into a dict
process_status_response_dict = process_status_response_instance.to_dict()
# create an instance of ProcessStatusResponse from a dict
process_status_response_from_dict = ProcessStatusResponse.from_dict(process_status_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


