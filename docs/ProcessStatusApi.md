# bol_shared_api_client.ProcessStatusApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_process_status**](ProcessStatusApi.md#get_process_status) | **GET** /shared/process-status/{process-status-id} | Get the status of an asynchronous process by process status id
[**get_process_status_bulk**](ProcessStatusApi.md#get_process_status_bulk) | **POST** /shared/process-status | Get the status of multiple asynchronous processes by an array of process status ids for a retailer
[**get_process_status_entity_id**](ProcessStatusApi.md#get_process_status_entity_id) | **GET** /shared/process-status | Get the status of an asynchronous process by entity id and event type for a retailer


# **get_process_status**
> ProcessStatus get_process_status(process_status_id)

Get the status of an asynchronous process by process status id

Retrieve a specific process status, which shows information regarding a previously executed PUT/POST/DELETE request. All PUT/POST/DELETE requests on the other endpoints will supply a process status id in the related response. You can use this id to retrieve a status by using the endpoint below. Please note: process status instances are only retained for a limited period of time after completion. Outside of this period, a 404 will be returned for missing process statuses. Please handle this accordingly, by stopping any active polling for these statuses.

### Example

* Bearer Authentication (OAuth2):

```python
import bol_shared_api_client
from bol_shared_api_client.models.process_status import ProcessStatus
from bol_shared_api_client.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = bol_shared_api_client.Configuration(
    host = "http://localhost"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization: OAuth2
configuration = bol_shared_api_client.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with bol_shared_api_client.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = bol_shared_api_client.ProcessStatusApi(api_client)
    process_status_id = 'process_status_id_example' # str | The id of the process status being requested. This id is supplied in every response to a PUT/POST/DELETE request on the other endpoints.

    try:
        # Get the status of an asynchronous process by process status id
        api_response = api_instance.get_process_status(process_status_id)
        print("The response of ProcessStatusApi->get_process_status:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ProcessStatusApi->get_process_status: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **process_status_id** | **str**| The id of the process status being requested. This id is supplied in every response to a PUT/POST/DELETE request on the other endpoints. | 

### Return type

[**ProcessStatus**](ProcessStatus.md)

### Authorization

[OAuth2](../README.md#OAuth2)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.retailer.v10+json, application/vnd.advertiser.v10+json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Ok: Successfully processed the request. |  -  |
**404** | Not found: The requested item could not be found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_process_status_bulk**
> ProcessStatusResponse get_process_status_bulk(bulk_process_status_request)

Get the status of multiple asynchronous processes by an array of process status ids for a retailer

Retrieve a list of process statuses, which shows information regarding previously executed PUT/POST/DELETE requests. No more than 1000 process status id's can be sent in a single request. Please note: process status instances are only retained for a limited period of time after completion. Outside of this period, deleted process statuses will no longer be returned. Please handle this accordingly, by stopping any active polling for these statuses.

### Example

* Bearer Authentication (OAuth2):

```python
import bol_shared_api_client
from bol_shared_api_client.models.bulk_process_status_request import BulkProcessStatusRequest
from bol_shared_api_client.models.process_status_response import ProcessStatusResponse
from bol_shared_api_client.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = bol_shared_api_client.Configuration(
    host = "http://localhost"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization: OAuth2
configuration = bol_shared_api_client.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with bol_shared_api_client.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = bol_shared_api_client.ProcessStatusApi(api_client)
    bulk_process_status_request = bol_shared_api_client.BulkProcessStatusRequest() # BulkProcessStatusRequest | 

    try:
        # Get the status of multiple asynchronous processes by an array of process status ids for a retailer
        api_response = api_instance.get_process_status_bulk(bulk_process_status_request)
        print("The response of ProcessStatusApi->get_process_status_bulk:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ProcessStatusApi->get_process_status_bulk: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **bulk_process_status_request** | [**BulkProcessStatusRequest**](BulkProcessStatusRequest.md)|  | 

### Return type

[**ProcessStatusResponse**](ProcessStatusResponse.md)

### Authorization

[OAuth2](../README.md#OAuth2)

### HTTP request headers

 - **Content-Type**: application/vnd.retailer.v10+json, application/vnd.advertiser.v10+json
 - **Accept**: application/vnd.retailer.v10+json, application/vnd.advertiser.v10+json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Ok: Successfully processed the request. |  -  |
**400** | Bad request: The sent request does not meet the API specification. Please check the error message(s) for more information. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_process_status_entity_id**
> ProcessStatusResponse get_process_status_entity_id(entity_id, event_type, page=page)

Get the status of an asynchronous process by entity id and event type for a retailer

Retrieve a list of process statuses, which shows information regarding previously executed PUT/POST/DELETE requests in descending order. You need to supply an entity id and event type. Please note: process status instances are only retained for a limited period of time after completion. Outside of this period, deleted process statuses will no longer be returned. Please handle this accordingly, by stopping any active polling for these statuses.

### Example

* Bearer Authentication (OAuth2):

```python
import bol_shared_api_client
from bol_shared_api_client.models.process_status_response import ProcessStatusResponse
from bol_shared_api_client.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = bol_shared_api_client.Configuration(
    host = "http://localhost"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization: OAuth2
configuration = bol_shared_api_client.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with bol_shared_api_client.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = bol_shared_api_client.ProcessStatusApi(api_client)
    entity_id = '987654321' # str | The entity id is not unique, so you will need to provide an event type. For example, an entity id can be an order item id, transport id, return number, replenishment id, campaign id, and keyword id.
    event_type = 'CREATE_SHIPMENT' # str | The event type can only be used in combination with the entity id.
    page = 1 # int | The requested page number with a page size of 50 items. (optional) (default to 1)

    try:
        # Get the status of an asynchronous process by entity id and event type for a retailer
        api_response = api_instance.get_process_status_entity_id(entity_id, event_type, page=page)
        print("The response of ProcessStatusApi->get_process_status_entity_id:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ProcessStatusApi->get_process_status_entity_id: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **entity_id** | **str**| The entity id is not unique, so you will need to provide an event type. For example, an entity id can be an order item id, transport id, return number, replenishment id, campaign id, and keyword id. | 
 **event_type** | **str**| The event type can only be used in combination with the entity id. | 
 **page** | **int**| The requested page number with a page size of 50 items. | [optional] [default to 1]

### Return type

[**ProcessStatusResponse**](ProcessStatusResponse.md)

### Authorization

[OAuth2](../README.md#OAuth2)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.retailer.v10+json, application/vnd.advertiser.v10+json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Ok: Successfully processed the request. |  -  |
**400** | Bad request: The sent request does not meet the API specification. Please check the error message(s) for more information. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

