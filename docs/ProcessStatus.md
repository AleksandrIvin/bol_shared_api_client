# ProcessStatus


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**process_status_id** | **str** | The process status id. | [optional] 
**entity_id** | **str** | The id of the object being processed. For example, in case of a shipment process id, you will receive the id of the order item being processed. | [optional] 
**event_type** | **str** | Name of the requested action that is being processed. | 
**description** | **str** | Describes the action that is being processed. | 
**status** | **str** | Status of the action being processed. | 
**error_message** | **str** | Shows error message if applicable. | [optional] 
**create_timestamp** | **datetime** | Time of creation of the response. | 
**links** | [**List[Link]**](Link.md) | Lists available actions applicable to this endpoint. | 

## Example

```python
from bol_shared_api_client.models.process_status import ProcessStatus

# TODO update the JSON string below
json = "{}"
# create an instance of ProcessStatus from a JSON string
process_status_instance = ProcessStatus.from_json(json)
# print the JSON string representation of the object
print(ProcessStatus.to_json())

# convert the object into a dict
process_status_dict = process_status_instance.to_dict()
# create an instance of ProcessStatus from a dict
process_status_from_dict = ProcessStatus.from_dict(process_status_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


