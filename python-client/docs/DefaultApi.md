# feiertage.DefaultApi

All URIs are relative to *https://feiertage-api.de/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_feiertage**](DefaultApi.md#get_feiertage) | **GET** / | Get Feiertage


# **get_feiertage**
> {str: (bool, date, datetime, dict, float, int, list, str, none_type)} get_feiertage(jahr)

Get Feiertage

### Example


```python
import time
from deutschland import feiertage
from deutschland.feiertage.api import default_api
from pprint import pprint
# Defining the host is optional and defaults to https://feiertage-api.de/api
# See configuration.py for a list of all supported configuration parameters.
configuration = feiertage.Configuration(
    host = "https://feiertage-api.de/api"
)


# Enter a context with an instance of the API client
with feiertage.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = default_api.DefaultApi(api_client)
    jahr = "2021" # str | Welches Jahr?
    nur_land = "NATIONAL" # str | Welches Bundesland? (optional)
    nur_daten = 1 # int | Nur Daten oder auch Hinweise? (optional)

    # example passing only required values which don't have defaults set
    try:
        # Get Feiertage
        api_response = api_instance.get_feiertage(jahr)
        pprint(api_response)
    except feiertage.ApiException as e:
        print("Exception when calling DefaultApi->get_feiertage: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Get Feiertage
        api_response = api_instance.get_feiertage(jahr, nur_land=nur_land, nur_daten=nur_daten)
        pprint(api_response)
    except feiertage.ApiException as e:
        print("Exception when calling DefaultApi->get_feiertage: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **jahr** | **str**| Welches Jahr? |
 **nur_land** | **str**| Welches Bundesland? | [optional]
 **nur_daten** | **int**| Nur Daten oder auch Hinweise? | [optional]

### Return type

**{str: (bool, date, datetime, dict, float, int, list, str, none_type)}**

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Feiertage |  -  |
**0** | unexpected error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

