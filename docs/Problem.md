# Problem

Describes a problem that occurred interacting with the API.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | **str** | Type URI for this problem. Fixed value: https://api.bol.com/problems. | 
**title** | **str** | Title describing the nature of the problem. | 
**status** | **int** | HTTP status returned from the endpoint causing the problem. | 
**detail** | **str** | Detailed error message describing in additional detail what caused the service to return this problem. | 
**host** | **str** | Host identifier describing the server instance that reported the problem. | [optional] 
**instance** | **str** | Full URI path of the resource that reported the problem. | [optional] 
**violations** | [**List[Violation]**](Violation.md) |  | 

## Example

```python
from bol_shared_api_client.models.problem import Problem

# TODO update the JSON string below
json = "{}"
# create an instance of Problem from a JSON string
problem_instance = Problem.from_json(json)
# print the JSON string representation of the object
print(Problem.to_json())

# convert the object into a dict
problem_dict = problem_instance.to_dict()
# create an instance of Problem from a dict
problem_from_dict = Problem.from_dict(problem_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


