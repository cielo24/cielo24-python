# cielo24.JobApi

All URIs are relative to *https://api.cielo24.com/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_media_file**](JobApi.md#add_media_file) | **POST** /job/add_media | 
[**add_media_url**](JobApi.md#add_media_url) | **GET** /job/add_media | 
[**authorize_job**](JobApi.md#authorize_job) | **POST** /job/authorize | 
[**new_job**](JobApi.md#new_job) | **POST** /job/new | 
[**perform_transcription**](JobApi.md#perform_transcription) | **POST** /job/perform_transcription | 


# **add_media_file**
> AddMediaResponse add_media_file(job_id, content_length, body)



Add a piece of media to an existing job using a local file. No content-type should be included in the HTTP header. The media should be uploaded as raw binary, no encoding (base64, hex, etc) is required. Chunk-transfer encoding is NOT supported. File size is limited to 10 gb

### Example

* Api Key Authentication (ApiKeyAuth):

```python
import time
import cielo24
from cielo24.api import job_api
from cielo24.model.add_media_response import AddMediaResponse
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
    api_instance = job_api.JobApi(api_client)
    job_id = "0fbd6015910e42dca25a863c4925d77c" # str | 
    content_length = 1 # int | 
    body = open('/path/to/file', 'rb') # file_type | 
    is_duplicate = "false" # str |  (optional) if omitted the server will use the default value of "false"

    # example passing only required values which don't have defaults set
    try:
        api_response = api_instance.add_media_file(job_id, content_length, body)
        pprint(api_response)
    except cielo24.ApiException as e:
        print("Exception when calling JobApi->add_media_file: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        api_response = api_instance.add_media_file(job_id, content_length, body, is_duplicate=is_duplicate)
        pprint(api_response)
    except cielo24.ApiException as e:
        print("Exception when calling JobApi->add_media_file: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **job_id** | **str**|  |
 **content_length** | **int**|  |
 **body** | **file_type**|  |
 **v** | **int**|  | defaults to 1
 **is_duplicate** | **str**|  | [optional] if omitted the server will use the default value of "false"

### Return type

[**AddMediaResponse**](AddMediaResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: video/mp4
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Success |  -  |
**400** | An error occurred |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **add_media_url**
> AddMediaResponse add_media_url(job_id, media_url)



Add a piece of media to an existing job using a public media url. A job may only have a single piece of media associated with it, attempting to add additional media will return an error code.

### Example

* Api Key Authentication (ApiKeyAuth):

```python
import time
import cielo24
from cielo24.api import job_api
from cielo24.model.add_media_response import AddMediaResponse
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
    api_instance = job_api.JobApi(api_client)
    job_id = "0fbd6015910e42dca25a863c4925d77c" # str | 
    media_url = "http://www.domain.com/video.mp4" # str | 
    is_duplicate = "false" # str |  (optional) if omitted the server will use the default value of "false"

    # example passing only required values which don't have defaults set
    try:
        api_response = api_instance.add_media_url(job_id, media_url)
        pprint(api_response)
    except cielo24.ApiException as e:
        print("Exception when calling JobApi->add_media_url: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        api_response = api_instance.add_media_url(job_id, media_url, is_duplicate=is_duplicate)
        pprint(api_response)
    except cielo24.ApiException as e:
        print("Exception when calling JobApi->add_media_url: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **job_id** | **str**|  |
 **media_url** | **str**|  |
 **v** | **int**|  | defaults to 1
 **is_duplicate** | **str**|  | [optional] if omitted the server will use the default value of "false"

### Return type

[**AddMediaResponse**](AddMediaResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Success |  -  |
**400** | An error occurred |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **authorize_job**
> authorize_job(job_id)



Authorize an existing job. If your account has the \"customer authorization\" feature enabled (it is not enabled by default) jobs you create will be held in the \"Authorizing\" state until you call this method. Calling this method on a job that is not the \"Authorizing\" state has no effect and will return success. Please contact support@cielo24.com to enable the \"customer authorization\" feature.

### Example

* Api Key Authentication (ApiKeyAuth):

```python
import time
import cielo24
from cielo24.api import job_api
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
    api_instance = job_api.JobApi(api_client)
    job_id = "0fbd6015910e42dca25a863c4925d77c" # str | 

    # example passing only required values which don't have defaults set
    try:
        api_instance.authorize_job(job_id)
    except cielo24.ApiException as e:
        print("Exception when calling JobApi->authorize_job: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **job_id** | **str**|  |
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
**200** | Success |  -  |
**400** | An error occurred |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **new_job**
> NewJobResponse new_job(new_job_body)



Create a new job. A job is a container into which you can upload media and request that transcription be performed. Creating a job is prerequisite for virtually all other methods.

### Example

* Api Key Authentication (ApiKeyAuth):

```python
import time
import cielo24
from cielo24.api import job_api
from cielo24.model.new_job_body import NewJobBody
from cielo24.model.new_job_response import NewJobResponse
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
    api_instance = job_api.JobApi(api_client)
    new_job_body = NewJobBody(
        job_name="job_name_example",
        language="en (Any RFC 5646 language code)",
        external_id="12345",
        username="my_sub_account",
        requestor="test_requestor",
        reference="test_reference",
        expected_speakers=40,
        is_duplicate="false",
    ) # NewJobBody | 

    # example passing only required values which don't have defaults set
    try:
        api_response = api_instance.new_job(new_job_body)
        pprint(api_response)
    except cielo24.ApiException as e:
        print("Exception when calling JobApi->new_job: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **new_job_body** | [**NewJobBody**](NewJobBody.md)|  |
 **v** | **int**|  | defaults to 1

### Return type

[**NewJobResponse**](NewJobResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Success |  -  |
**400** | An error occurred |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **perform_transcription**
> PerformTranscriptionResponse perform_transcription(perform_transcription_body)



Request that transcription be performed on the specified job. A callback URL, if specified, will be called when the transcription is complete. See [callback documentation](https://cielo24.readthedocs.io/en/latest/basics.html#callbacks-label) for details.

### Example

* Api Key Authentication (ApiKeyAuth):

```python
import time
import cielo24
from cielo24.api import job_api
from cielo24.model.perform_transcription_response import PerformTranscriptionResponse
from cielo24.model.perform_transcription_body import PerformTranscriptionBody
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
    api_instance = job_api.JobApi(api_client)
    perform_transcription_body = PerformTranscriptionBody(
        job_id="0fbd6015910e42dca25a863c4925d77c",
        transcription_fidelity="MECHANICAL",
        priority="STANDARD",
        callback_url="http://www.domain.com/path",
        options="{"notes": "test"}",
        target_language="en (Any RFC 5646 language code)",
        turnaround_hours=36,
    ) # PerformTranscriptionBody | 

    # example passing only required values which don't have defaults set
    try:
        api_response = api_instance.perform_transcription(perform_transcription_body)
        pprint(api_response)
    except cielo24.ApiException as e:
        print("Exception when calling JobApi->perform_transcription: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **perform_transcription_body** | [**PerformTranscriptionBody**](PerformTranscriptionBody.md)|  |
 **v** | **int**|  | defaults to 1

### Return type

[**PerformTranscriptionResponse**](PerformTranscriptionResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Success |  -  |
**400** | An error occurred |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

