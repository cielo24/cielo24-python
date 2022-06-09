# cielo24.AccountApi

All URIs are relative to *https://api.cielo24.com/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_settings**](AccountApi.md#get_settings) | **GET** /account/get_settings | 
[**login**](AccountApi.md#login) | **POST** /account/login | 
[**logout**](AccountApi.md#logout) | **POST** /account/logout | 
[**verify_key**](AccountApi.md#verify_key) | **GET** /account/verify_key | 


# **get_settings**
> {str: (bool, date, datetime, dict, float, int, list, str, none_type)} get_settings()



Get Account Settings

### Example

* Api Key Authentication (ApiKeyAuth):

```python
import time
import cielo24
from cielo24.api import account_api
from pprint import pprint
# Defining the host is optional and defaults to https://api.cielo24.com/api
# See configuration.py for a list of all supported configuration parameters.
configuration = cielo24.Configuration(
    host = "https://api.cielo24.com/api"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure API key authorization: ApiKeyAuth
configuration.api_key['ApiKeyAuth'] = 'YOUR_API_KEY'

# Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
# configuration.api_key_prefix['ApiKeyAuth'] = 'Bearer'

# Enter a context with an instance of the API client
with cielo24.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = account_api.AccountApi(api_client)

    # example passing only required values which don't have defaults set
    try:
        api_response = api_instance.get_settings()
        pprint(api_response)
    except cielo24.ApiException as e:
        print("Exception when calling AccountApi->get_settings: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **v** | **int**|  | defaults to 1

### Return type

**{str: (bool, date, datetime, dict, float, int, list, str, none_type)}**

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Test |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **login**
> LoginResponse login(login_body)



Login to the cielo24 API to obtain an API access token for use when calling other methods. Optional arguments may be passed either as HTTP headers or query string parameters. Required arguments must be passed as query string parameters.

### Example


```python
import time
import cielo24
from cielo24.api import account_api
from cielo24.model.login_response import LoginResponse
from cielo24.model.login_body import LoginBody
from cielo24.model.error_response import ErrorResponse
from pprint import pprint
# Defining the host is optional and defaults to https://api.cielo24.com/api
# See configuration.py for a list of all supported configuration parameters.
configuration = cielo24.Configuration(
    host = "https://api.cielo24.com/api"
)


# Enter a context with an instance of the API client
with cielo24.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = account_api.AccountApi(api_client)
    login_body = LoginBody(
        username="username_example",
        password="password_example",
        securekey="securekey_example",
    ) # LoginBody | 

    # example passing only required values which don't have defaults set
    try:
        api_response = api_instance.login(login_body)
        pprint(api_response)
    except cielo24.ApiException as e:
        print("Exception when calling AccountApi->login: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **login_body** | [**LoginBody**](LoginBody.md)|  |
 **v** | **int**|  | defaults to 1

### Return type

[**LoginResponse**](LoginResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Success |  -  |
**400** | An error occurred |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **logout**
> logout()



Logout of the current session, invalidating the API token.

### Example

* Api Key Authentication (ApiKeyAuth):

```python
import time
import cielo24
from cielo24.api import account_api
from cielo24.model.error_response import ErrorResponse
from pprint import pprint
# Defining the host is optional and defaults to https://api.cielo24.com/api
# See configuration.py for a list of all supported configuration parameters.
configuration = cielo24.Configuration(
    host = "https://api.cielo24.com/api"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure API key authorization: ApiKeyAuth
configuration.api_key['ApiKeyAuth'] = 'YOUR_API_KEY'

# Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
# configuration.api_key_prefix['ApiKeyAuth'] = 'Bearer'

# Enter a context with an instance of the API client
with cielo24.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = account_api.AccountApi(api_client)

    # example passing only required values which don't have defaults set
    try:
        api_instance.logout()
    except cielo24.ApiException as e:
        print("Exception when calling AccountApi->logout: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **v** | **int**|  | defaults to 1

### Return type

void (empty response body)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | Success |  -  |
**400** | An error occurred |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **verify_key**
> VerifyKeyResponse verify_key()



Test Auth

### Example

* Api Key Authentication (ApiKeyAuth):

```python
import time
import cielo24
from cielo24.api import account_api
from cielo24.model.verify_key_response import VerifyKeyResponse
from pprint import pprint
# Defining the host is optional and defaults to https://api.cielo24.com/api
# See configuration.py for a list of all supported configuration parameters.
configuration = cielo24.Configuration(
    host = "https://api.cielo24.com/api"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure API key authorization: ApiKeyAuth
configuration.api_key['ApiKeyAuth'] = 'YOUR_API_KEY'

# Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
# configuration.api_key_prefix['ApiKeyAuth'] = 'Bearer'

# Enter a context with an instance of the API client
with cielo24.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = account_api.AccountApi(api_client)

    # example passing only required values which don't have defaults set
    try:
        api_response = api_instance.verify_key()
        pprint(api_response)
    except cielo24.ApiException as e:
        print("Exception when calling AccountApi->verify_key: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **v** | **int**|  | defaults to 1

### Return type

[**VerifyKeyResponse**](VerifyKeyResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Test |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

