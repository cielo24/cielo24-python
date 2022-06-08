# cielo24
The cielo24 Web Services Platform API allows developers to easily integrate transcription, captioning and keyword extraction into their applications without having to use a manual web portal.

This Python package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: 1.0.0
- Package version: 1.0.0
- Build package: org.openapitools.codegen.languages.PythonClientCodegen

## Requirements.

Python >=3.6

## Installation & Usage
### pip install

If the python package is hosted on a repository, you can install directly using:

```sh
pip install git+https://github.com/GIT_USER_ID/GIT_REPO_ID.git
```
(you may need to run `pip` with root permission: `sudo pip install git+https://github.com/GIT_USER_ID/GIT_REPO_ID.git`)

Then import the package:
```python
import cielo24
```

### Setuptools

Install via [Setuptools](http://pypi.python.org/pypi/setuptools).

```sh
python setup.py install --user
```
(or `sudo python setup.py install` to install the package for all users)

Then import the package:
```python
import cielo24
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```python

import time
import cielo24
from pprint import pprint
from cielo24.api import account_api
from cielo24.model.error_response import ErrorResponse
from cielo24.model.login_body import LoginBody
from cielo24.model.login_response import LoginResponse
from cielo24.model.verify_key_response import VerifyKeyResponse
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
    v = 1 # int |  (default to 1)

    try:
        api_instance.get_settings(v)
    except cielo24.ApiException as e:
        print("Exception when calling AccountApi->get_settings: %s\n" % e)
```

## Documentation for API Endpoints

All URIs are relative to *https://api.cielo24.com/api*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AccountApi* | [**get_settings**](docs/AccountApi.md#get_settings) | **GET** /account/get_settings | 
*AccountApi* | [**login**](docs/AccountApi.md#login) | **POST** /account/login | 
*AccountApi* | [**logout**](docs/AccountApi.md#logout) | **POST** /account/logout | 
*AccountApi* | [**verify_key**](docs/AccountApi.md#verify_key) | **GET** /account/verify_key | 
*JobApi* | [**add_media_file**](docs/JobApi.md#add_media_file) | **POST** /job/add_media | 
*JobApi* | [**add_media_url**](docs/JobApi.md#add_media_url) | **GET** /job/add_media | 
*JobApi* | [**authorize_job**](docs/JobApi.md#authorize_job) | **POST** /job/authorize | 
*JobApi* | [**new_job**](docs/JobApi.md#new_job) | **POST** /job/new | 
*JobApi* | [**perform_transcription**](docs/JobApi.md#perform_transcription) | **POST** /job/perform_transcription | 


## Documentation For Models

 - [AddMediaResponse](docs/AddMediaResponse.md)
 - [ErrorResponse](docs/ErrorResponse.md)
 - [IWPEnum](docs/IWPEnum.md)
 - [JobOptions](docs/JobOptions.md)
 - [LoginBody](docs/LoginBody.md)
 - [LoginResponse](docs/LoginResponse.md)
 - [NewJobBody](docs/NewJobBody.md)
 - [NewJobResponse](docs/NewJobResponse.md)
 - [PerformTranscriptionBody](docs/PerformTranscriptionBody.md)
 - [PerformTranscriptionResponse](docs/PerformTranscriptionResponse.md)
 - [VerifyKeyResponse](docs/VerifyKeyResponse.md)


## Documentation For Authorization


## ApiKeyAuth

- **Type**: API key
- **API key parameter name**: api_token
- **Location**: URL query string


## Author

devs@cielo24.com


## Notes for Large OpenAPI documents
If the OpenAPI document is large, imports in cielo24.apis and cielo24.models may fail with a
RecursionError indicating the maximum recursion limit has been exceeded. In that case, there are a couple of solutions:

Solution 1:
Use specific imports for apis and models like:
- `from cielo24.api.default_api import DefaultApi`
- `from cielo24.model.pet import Pet`

Solution 2:
Before importing the package, adjust the maximum recursion limit as shown below:
```
import sys
sys.setrecursionlimit(1500)
import cielo24
from cielo24.apis import *
from cielo24.models import *
```

