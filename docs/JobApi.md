# cielo24.JobApi

All URIs are relative to *https://api.cielo24.com/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_media_file**](JobApi.md#add_media_file) | **POST** /job/add_media | 
[**add_media_url**](JobApi.md#add_media_url) | **GET** /job/add_media | 
[**authorize_job**](JobApi.md#authorize_job) | **POST** /job/authorize | 
[**get_caption**](JobApi.md#get_caption) | **GET** /job/get_caption | 
[**job_info**](JobApi.md#job_info) | **GET** /job/info | 
[**new_job**](JobApi.md#new_job) | **POST** /job/new | 
[**perform_transcription**](JobApi.md#perform_transcription) | **POST** /job/perform_transcription | 
[**perform_translation**](JobApi.md#perform_translation) | **POST** /job/translate | 


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

# **get_caption**
> str get_caption(job_id, caption_format)



Get the caption file for a job. The job must have completed transcription before a caption can be downloaded.

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
    caption_format = "SRT" # str | 
    build_url = "false" # str | Rather than returning the file, return a permanent URL to the file. (optional) if omitted the server will use the default value of "false"
    caption_words_min = 3 # int | Minimum number of words allowed in a caption. (optional) if omitted the server will use the default value of 1
    caption_by_sentence = "false" # str | When true, puts each sentence into its own caption. When false, more than one sentence may appear in a single caption. (optional) if omitted the server will use the default value of "true"
    characters_per_caption_line = 30 # int | Maximum number of characters to be displayed on each caption line. (optional) if omitted the server will use the default value of 42
    dfxp_header = "<head></head>" # str | Allows you to specify a custom header for your DFXP caption file. The header should be the entire contents of the header including the opening and closing tags. Ignored if caption_format does not equal DFXP. (optional) if omitted the server will use the default value of ""
    disallow_dangling = "true" # str | Will prevent captions from having the last word in a sentence start a new line. Last words will ALWAYS be kept on the same line, even if it breaks the characters_per_caption_line option. (optional) if omitted the server will use the default value of "false"
    display_effects_speaker_as = "Sounds" # str | Determines what speaker name should used for sound effects. (optional) if omitted the server will use the default value of "Effects"
    display_speaker_id = "number" # str | Determines the way speakers are identified in the captions. Choose \"no\" to not display speaker identities at all: \">> example\" Choose \"number\" to display only the speaker number: \">> Speaker 1: example\" Choose \"name\" to display the speaker name: \">> John Doe: example\". If you choose \"name\", the speaker number will be displayed if the name is not available. (optional) if omitted the server will use the default value of "name"
    iwp_name = "MECHANICAL" # str | The named version of element list to generate the transcript from. If not specified, the transcript will be generated from the latest version. (optional) if omitted the server will use the default value of ""
    elementlist_version = "2014-07-31T12:35:52.324389" # str | The version of element list to generate the captions from. If not specified, the caption will be generated from the latest version. (ISO 8601 Date String) (optional) if omitted the server will use the default value of ""
    emit_speaker_change_tokens_as = "-->" # str | Determine what characters to use to denote speaker changes. (optional) if omitted the server will use the default value of ">>"
    force_case = "lower" # str | Force the contents of the captions to be all UPPER or lower case. If blank, the case of the captions is not changed. (optional) if omitted the server will use the default value of ""
    include_dfxp_metadata = "false" # str | When true, and the caption format requested is DFXP, the jobs name, ID and language will be added to the DFXP metadata header. When false, these data are omitted from the header. Ignored if caption_format does not equal DFXP. (optional) if omitted the server will use the default value of "true"
    layout_target_caption_length_ms = 4000 # int | Captions generated will, on average, be this duration. However, they may vary significantly based on other parameters you set. (optional) if omitted the server will use the default value of 5000
    line_break_on_sentence = "true" # str | Inserts a line break in between sentences that are in the same caption. (optional) if omitted the server will use the default value of "false"
    line_ending_format = "OSX" # str | Determine the end of line (EOL) character to use for the captions. (optional) if omitted the server will use the default value of "UNIX"
    lines_per_caption = 3 # int | Number of lines to be displayed for each caption. (optional) if omitted the server will use the default value of 2
    mask_profanity = "true" # str | Replace profanity with asterisks. (optional) if omitted the server will use the default value of "false"
    maximum_caption_duration = 10000 # int | No captions longer than this (in milliseconds) will be produced. If not specified, there is no maximum. (optional)
    merge_gap_interval = 1500 # int | Captions with a gap between them that is smaller than this (in milliseconds) will have their start and/or end times changed so there is no time gap between the captions. (optional) if omitted the server will use the default value of 1000
    minimum_caption_length_ms = 1500 # int | Extends the duration of short captions to the this minimum length. Additional time is taken from later caption blocks to meet this minimum time. (optional)
    minimum_gap_between_captions_ms = 100 # int | Adds a minimum time between captions such as there will always be some time between captions where no text is displayed. When captions are very close together, time will be removed from the caption duration to make the gap. (optional)
    qt_seamless = "true" # str | Does not put time gaps of any kind between caption blocks. Ignored if caption_format does not equal QT. (optional) if omitted the server will use the default value of "false"
    remove_disfluencies = "false" # str | Remove verbal disfluencies from the generated transcript. Common disfluencies such as \"um\" and \"ah\" are removed while maintaining appropriate punctuation. (optional) if omitted the server will use the default value of "true"
    remove_sounds_list = ["MUSIC","LAUGH"] # [str] | A list of sounds to not show in the caption. This is a JSON style list, and should look like [\"MUSIC\", \"LAUGH\"]. Ignored if remove_sound_references is true. (optional) if omitted the server will use the default value of []
    remove_sound_references = "false" # str | Remove ALL non-verbal sound and noise references from the generated transcript. Sounds and unidentified noises are depicted in the caption as [SOUND], [COUGH] and [NOISE]. If this parameter is set, these identifiers are omitted from the caption. (optional) if omitted the server will use the default value of "true"
    replace_slang = "true" # str | Replace common slang terms from the generated transcript. Common replacements are \"want to\" for \"wanna\", \"going to\" for \"gonna\", etc. (optional) if omitted the server will use the default value of "false"
    silence_max_ms = 1000 # int | If there is a interval of silence in the middle of a sentence longer than this, then the caption will be split. (optional) if omitted the server will use the default value of 2000
    single_speaker_per_caption = "false" # str | When true, puts each speaker into its own caption. When false, more than one speaker may appear in a single caption. (optional) if omitted the server will use the default value of "true"
    sound_boundaries = ["(",")"] # [str] | Specifies the characters to surround sound references with. The default will generate sound references that look like this: [MUSIC]. (optional) if omitted the server will use the default value of ["[","]"]
    sound_threshold = 5000 # int | Sound references that are longer than this threshold will be made their own caption entirely, and will not have any text included with them. If not set, Sound references will be included back to back with text no matter the duration of the sound. (optional)
    sound_tokens_by_caption = "true" # str | If true, all sound references will always be in their own caption. If false, more than one sound reference may appear in a single caption. (optional) if omitted the server will use the default value of "false"
    sound_tokens_by_line = "true" # str | If true, all sound references will always be in their own line. If false, more than one sound reference may appear in a single line. (optional) if omitted the server will use the default value of "false"
    sound_tokens_by_caption_list = [] # [str] | If non-empty, the specified sound references will always be in their own caption. If empty, more than one sound reference may appear in a single caption. Ignored if sound_tokens_by_caption is true. (optional) if omitted the server will use the default value of ["BLANK_AUDIO","MUSIC"]
    sound_tokens_by_line_list = ["NOISE"] # [str] | If non-empty, the specified sound references will always be in their own line. If empty, more than one sound reference may appear in a single line. Ignored if sound_tokens_by_line is true. (optional) if omitted the server will use the default value of ["BLANK_AUDIO","MUSIC"]
    speaker_on_new_line = "false" # str | If true, a speaker change will cause a new caption to be made. If false, multiple speakers may appear in a single caption. (optional) if omitted the server will use the default value of "true"
    srt_format = "{caption_number:d}\n{start_hour:02d}:{start_minute:02d}:{start_second:02d},{start_millisecond:03d} -->{end_hour:02d}:{end_minute:02d}:{end_second:02d},{end_millisecond:03d}\n{caption_text}\n\n" # str | If the caption format is SRT, determines what the caption blocks will look like. The default, prints caption blocks that look like this:    1:   00:00:06,060 --> 00:00:16,060   This is the caption text.  You can alter the caption block by re-arranging or removing the substitution string values, shown enclosed in braces \"{}\" in the default value below. Substitution strings may used more than once if desired. Any text that is not a substitution string will be displayed as written. To add new lines, include a \\n. Note, you may need to escape the \\n with an extra backslash when encoding the request.  (optional) if omitted the server will use the default value of "{caption_number:d}\n{start_hour:02d}:{start_minute:02d}:{start_second:02d},{start_millisecond:03d} -->{end_hour:02d}:{end_minute:02d}:{end_second:02d},{end_millisecond:03d}\n{caption_text}\n\n"
    strip_square_brackets = "true" # str | Removes all square brackets like '[' or ']' from captions. By default square brackets surround sound references like '[MUSIC]', but they may exist as part of the caption text as well. (optional) if omitted the server will use the default value of "false"
    utf8_mark = "true" # str | Adds a utf8 bytemark to the beginning of the caption. This should only be used if the system you are loading the caption files into needs a byte marker. The vast majority of systems do not. (optional) if omitted the server will use the default value of "false"
    replace_english_spelling = "B" # str | Replaces English spelling with location accurate spelling. i.e. Color --> Colour  A: American  B: British  Z: British ize  U: Australian  C: Canadian  (optional) if omitted the server will use the default value of "A"

    # example passing only required values which don't have defaults set
    try:
        api_response = api_instance.get_caption(job_id, caption_format)
        pprint(api_response)
    except cielo24.ApiException as e:
        print("Exception when calling JobApi->get_caption: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        api_response = api_instance.get_caption(job_id, caption_format, build_url=build_url, caption_words_min=caption_words_min, caption_by_sentence=caption_by_sentence, characters_per_caption_line=characters_per_caption_line, dfxp_header=dfxp_header, disallow_dangling=disallow_dangling, display_effects_speaker_as=display_effects_speaker_as, display_speaker_id=display_speaker_id, iwp_name=iwp_name, elementlist_version=elementlist_version, emit_speaker_change_tokens_as=emit_speaker_change_tokens_as, force_case=force_case, include_dfxp_metadata=include_dfxp_metadata, layout_target_caption_length_ms=layout_target_caption_length_ms, line_break_on_sentence=line_break_on_sentence, line_ending_format=line_ending_format, lines_per_caption=lines_per_caption, mask_profanity=mask_profanity, maximum_caption_duration=maximum_caption_duration, merge_gap_interval=merge_gap_interval, minimum_caption_length_ms=minimum_caption_length_ms, minimum_gap_between_captions_ms=minimum_gap_between_captions_ms, qt_seamless=qt_seamless, remove_disfluencies=remove_disfluencies, remove_sounds_list=remove_sounds_list, remove_sound_references=remove_sound_references, replace_slang=replace_slang, silence_max_ms=silence_max_ms, single_speaker_per_caption=single_speaker_per_caption, sound_boundaries=sound_boundaries, sound_threshold=sound_threshold, sound_tokens_by_caption=sound_tokens_by_caption, sound_tokens_by_line=sound_tokens_by_line, sound_tokens_by_caption_list=sound_tokens_by_caption_list, sound_tokens_by_line_list=sound_tokens_by_line_list, speaker_on_new_line=speaker_on_new_line, srt_format=srt_format, strip_square_brackets=strip_square_brackets, utf8_mark=utf8_mark, replace_english_spelling=replace_english_spelling)
        pprint(api_response)
    except cielo24.ApiException as e:
        print("Exception when calling JobApi->get_caption: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **job_id** | **str**|  |
 **caption_format** | **str**|  |
 **v** | **int**|  | defaults to 1
 **build_url** | **str**| Rather than returning the file, return a permanent URL to the file. | [optional] if omitted the server will use the default value of "false"
 **caption_words_min** | **int**| Minimum number of words allowed in a caption. | [optional] if omitted the server will use the default value of 1
 **caption_by_sentence** | **str**| When true, puts each sentence into its own caption. When false, more than one sentence may appear in a single caption. | [optional] if omitted the server will use the default value of "true"
 **characters_per_caption_line** | **int**| Maximum number of characters to be displayed on each caption line. | [optional] if omitted the server will use the default value of 42
 **dfxp_header** | **str**| Allows you to specify a custom header for your DFXP caption file. The header should be the entire contents of the header including the opening and closing tags. Ignored if caption_format does not equal DFXP. | [optional] if omitted the server will use the default value of ""
 **disallow_dangling** | **str**| Will prevent captions from having the last word in a sentence start a new line. Last words will ALWAYS be kept on the same line, even if it breaks the characters_per_caption_line option. | [optional] if omitted the server will use the default value of "false"
 **display_effects_speaker_as** | **str**| Determines what speaker name should used for sound effects. | [optional] if omitted the server will use the default value of "Effects"
 **display_speaker_id** | **str**| Determines the way speakers are identified in the captions. Choose \&quot;no\&quot; to not display speaker identities at all: \&quot;&gt;&gt; example\&quot; Choose \&quot;number\&quot; to display only the speaker number: \&quot;&gt;&gt; Speaker 1: example\&quot; Choose \&quot;name\&quot; to display the speaker name: \&quot;&gt;&gt; John Doe: example\&quot;. If you choose \&quot;name\&quot;, the speaker number will be displayed if the name is not available. | [optional] if omitted the server will use the default value of "name"
 **iwp_name** | **str**| The named version of element list to generate the transcript from. If not specified, the transcript will be generated from the latest version. | [optional] if omitted the server will use the default value of ""
 **elementlist_version** | **str**| The version of element list to generate the captions from. If not specified, the caption will be generated from the latest version. (ISO 8601 Date String) | [optional] if omitted the server will use the default value of ""
 **emit_speaker_change_tokens_as** | **str**| Determine what characters to use to denote speaker changes. | [optional] if omitted the server will use the default value of ">>"
 **force_case** | **str**| Force the contents of the captions to be all UPPER or lower case. If blank, the case of the captions is not changed. | [optional] if omitted the server will use the default value of ""
 **include_dfxp_metadata** | **str**| When true, and the caption format requested is DFXP, the jobs name, ID and language will be added to the DFXP metadata header. When false, these data are omitted from the header. Ignored if caption_format does not equal DFXP. | [optional] if omitted the server will use the default value of "true"
 **layout_target_caption_length_ms** | **int**| Captions generated will, on average, be this duration. However, they may vary significantly based on other parameters you set. | [optional] if omitted the server will use the default value of 5000
 **line_break_on_sentence** | **str**| Inserts a line break in between sentences that are in the same caption. | [optional] if omitted the server will use the default value of "false"
 **line_ending_format** | **str**| Determine the end of line (EOL) character to use for the captions. | [optional] if omitted the server will use the default value of "UNIX"
 **lines_per_caption** | **int**| Number of lines to be displayed for each caption. | [optional] if omitted the server will use the default value of 2
 **mask_profanity** | **str**| Replace profanity with asterisks. | [optional] if omitted the server will use the default value of "false"
 **maximum_caption_duration** | **int**| No captions longer than this (in milliseconds) will be produced. If not specified, there is no maximum. | [optional]
 **merge_gap_interval** | **int**| Captions with a gap between them that is smaller than this (in milliseconds) will have their start and/or end times changed so there is no time gap between the captions. | [optional] if omitted the server will use the default value of 1000
 **minimum_caption_length_ms** | **int**| Extends the duration of short captions to the this minimum length. Additional time is taken from later caption blocks to meet this minimum time. | [optional]
 **minimum_gap_between_captions_ms** | **int**| Adds a minimum time between captions such as there will always be some time between captions where no text is displayed. When captions are very close together, time will be removed from the caption duration to make the gap. | [optional]
 **qt_seamless** | **str**| Does not put time gaps of any kind between caption blocks. Ignored if caption_format does not equal QT. | [optional] if omitted the server will use the default value of "false"
 **remove_disfluencies** | **str**| Remove verbal disfluencies from the generated transcript. Common disfluencies such as \&quot;um\&quot; and \&quot;ah\&quot; are removed while maintaining appropriate punctuation. | [optional] if omitted the server will use the default value of "true"
 **remove_sounds_list** | **[str]**| A list of sounds to not show in the caption. This is a JSON style list, and should look like [\&quot;MUSIC\&quot;, \&quot;LAUGH\&quot;]. Ignored if remove_sound_references is true. | [optional] if omitted the server will use the default value of []
 **remove_sound_references** | **str**| Remove ALL non-verbal sound and noise references from the generated transcript. Sounds and unidentified noises are depicted in the caption as [SOUND], [COUGH] and [NOISE]. If this parameter is set, these identifiers are omitted from the caption. | [optional] if omitted the server will use the default value of "true"
 **replace_slang** | **str**| Replace common slang terms from the generated transcript. Common replacements are \&quot;want to\&quot; for \&quot;wanna\&quot;, \&quot;going to\&quot; for \&quot;gonna\&quot;, etc. | [optional] if omitted the server will use the default value of "false"
 **silence_max_ms** | **int**| If there is a interval of silence in the middle of a sentence longer than this, then the caption will be split. | [optional] if omitted the server will use the default value of 2000
 **single_speaker_per_caption** | **str**| When true, puts each speaker into its own caption. When false, more than one speaker may appear in a single caption. | [optional] if omitted the server will use the default value of "true"
 **sound_boundaries** | **[str]**| Specifies the characters to surround sound references with. The default will generate sound references that look like this: [MUSIC]. | [optional] if omitted the server will use the default value of ["[","]"]
 **sound_threshold** | **int**| Sound references that are longer than this threshold will be made their own caption entirely, and will not have any text included with them. If not set, Sound references will be included back to back with text no matter the duration of the sound. | [optional]
 **sound_tokens_by_caption** | **str**| If true, all sound references will always be in their own caption. If false, more than one sound reference may appear in a single caption. | [optional] if omitted the server will use the default value of "false"
 **sound_tokens_by_line** | **str**| If true, all sound references will always be in their own line. If false, more than one sound reference may appear in a single line. | [optional] if omitted the server will use the default value of "false"
 **sound_tokens_by_caption_list** | **[str]**| If non-empty, the specified sound references will always be in their own caption. If empty, more than one sound reference may appear in a single caption. Ignored if sound_tokens_by_caption is true. | [optional] if omitted the server will use the default value of ["BLANK_AUDIO","MUSIC"]
 **sound_tokens_by_line_list** | **[str]**| If non-empty, the specified sound references will always be in their own line. If empty, more than one sound reference may appear in a single line. Ignored if sound_tokens_by_line is true. | [optional] if omitted the server will use the default value of ["BLANK_AUDIO","MUSIC"]
 **speaker_on_new_line** | **str**| If true, a speaker change will cause a new caption to be made. If false, multiple speakers may appear in a single caption. | [optional] if omitted the server will use the default value of "true"
 **srt_format** | **str**| If the caption format is SRT, determines what the caption blocks will look like. The default, prints caption blocks that look like this:    1:   00:00:06,060 --&gt; 00:00:16,060   This is the caption text.  You can alter the caption block by re-arranging or removing the substitution string values, shown enclosed in braces \&quot;{}\&quot; in the default value below. Substitution strings may used more than once if desired. Any text that is not a substitution string will be displayed as written. To add new lines, include a \\n. Note, you may need to escape the \\n with an extra backslash when encoding the request.  | [optional] if omitted the server will use the default value of "{caption_number:d}\n{start_hour:02d}:{start_minute:02d}:{start_second:02d},{start_millisecond:03d} -->{end_hour:02d}:{end_minute:02d}:{end_second:02d},{end_millisecond:03d}\n{caption_text}\n\n"
 **strip_square_brackets** | **str**| Removes all square brackets like &#39;[&#39; or &#39;]&#39; from captions. By default square brackets surround sound references like &#39;[MUSIC]&#39;, but they may exist as part of the caption text as well. | [optional] if omitted the server will use the default value of "false"
 **utf8_mark** | **str**| Adds a utf8 bytemark to the beginning of the caption. This should only be used if the system you are loading the caption files into needs a byte marker. The vast majority of systems do not. | [optional] if omitted the server will use the default value of "false"
 **replace_english_spelling** | **str**| Replaces English spelling with location accurate spelling. i.e. Color --&gt; Colour  A: American  B: British  Z: British ize  U: Australian  C: Canadian  | [optional] if omitted the server will use the default value of "A"

### Return type

**str**

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: text/plain, application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Success |  -  |
**400** | An error occurred |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **job_info**
> JobInfoResponse job_info(job_id)



### Example

* Api Key Authentication (ApiKeyAuth):

```python
import time
import cielo24
from cielo24.api import job_api
from cielo24.model.job_info_response import JobInfoResponse
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
        api_response = api_instance.job_info(job_id)
        pprint(api_response)
    except cielo24.ApiException as e:
        print("Exception when calling JobApi->job_info: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **job_id** | **str**|  |
 **v** | **int**|  | defaults to 1

### Return type

[**JobInfoResponse**](JobInfoResponse.md)

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

# **perform_translation**
> PerformTranslationResponse perform_translation(job_id, target_languages)



Request that orders a new Translation language for a video that has been previously Transcribed and/or Translated. The New Job ID and job target language will be returned upon completion.

### Example

* Api Key Authentication (ApiKeyAuth):

```python
import time
import cielo24
from cielo24.api import job_api
from cielo24.model.error_response import ErrorResponse
from cielo24.model.perform_translation_response import PerformTranslationResponse
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
    target_languages = "fr,de" # str | The language(s) being ordered (Any RFC 5646 language code) separated by comma (,)
    approve_uplevel = "true" # str |  (optional)

    # example passing only required values which don't have defaults set
    try:
        api_response = api_instance.perform_translation(job_id, target_languages)
        pprint(api_response)
    except cielo24.ApiException as e:
        print("Exception when calling JobApi->perform_translation: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        api_response = api_instance.perform_translation(job_id, target_languages, approve_uplevel=approve_uplevel)
        pprint(api_response)
    except cielo24.ApiException as e:
        print("Exception when calling JobApi->perform_translation: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **job_id** | **str**|  |
 **target_languages** | **str**| The language(s) being ordered (Any RFC 5646 language code) separated by comma (,) |
 **v** | **int**|  | defaults to 1
 **approve_uplevel** | **str**|  | [optional]

### Return type

[**PerformTranslationResponse**](PerformTranslationResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Success |  -  |
**400** | An error occurred |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

