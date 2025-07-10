# Violation

Describes a violation that occurred interacting with the API.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **str** | Describes the origin of the error, for instance a field or query parameter validation error. | 
**reason** | **str** | Detailed description of the validation error that caused the problem. | 

## Example

```python
from bol_shared_api_client.models.violation import Violation

# TODO update the JSON string below
json = "{}"
# create an instance of Violation from a JSON string
violation_instance = Violation.from_json(json)
# print the JSON string representation of the object
print(Violation.to_json())

# convert the object into a dict
violation_dict = violation_instance.to_dict()
# create an instance of Violation from a dict
violation_from_dict = Violation.from_dict(violation_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


