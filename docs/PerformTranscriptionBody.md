# PerformTranscriptionBody


## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**job_id** | **str** | The ID of the job | 
**transcription_fidelity** | **str** | The desired fidelity of the transcription | 
**priority** | **str** | The desired priority of the transcription | 
**callback_url** | **str** | A URL with query string which will be called on completion. If submitting the callback_url as a query string parameter, rather than a value in the POST data, the callback_url should be URL encoded. The callback URL can contain tags that will be replaced with job specific data when the callback is called. Below is the list of tags that are supported: {job_id}, {job_name}, {elementlist_version}, {iwp_name} (The Interim Work Product name associated with this ElementList version) | [optional] 
**options** | **str** | A job options json. See JobOptions object for details. | [optional] 
**target_language** | **str** | An RFC 5646 language code to translate this job into. If not specified, then no translation will be performed. If specified, but the language code specified matches the language code on the job request, then no translation will be performed. | [optional] 
**turnaround_hours** | **int** | The number of hours after submission that the job will be returned. If not specified, it will be set to a default based on the value of the priority parameter. The defaults are 24 and 48 for the PRIORITY and STANDARD priorities respectively. If you request a smaller number of hours than the default for the priority you have selected, the priority will be automatically changed. For example if you request a turnaround_hours of 16 with a priority of STANDARD, the priority will be automatically, and silently, changed to PRIORITY. | [optional] 
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


