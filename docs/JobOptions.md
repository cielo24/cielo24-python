# JobOptions


## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**customer_approval_steps** | **[str]** | Requires your approval of a job at specified points in the workflow. When the job is ready for approval you will be emailed a link that will take you to a web based tool you can use to view, edit and approve the job. You may request approval at two points in the workflow: before translation and before the job is returned. | [optional]  if omitted the server will use the default value of []
**customer_approval_tool** | **str** | Determines which web based tool to use for viewing, editing and approving jobs. | [optional]  if omitted the server will use the default value of "CIELO24"
**custom_metadata** | **{str: (bool, date, datetime, dict, float, int, list, str, none_type)}** | A JSON dictionary of key value pairs. These will be used as substitution strings when building the callback URL and custom DFXP caption header. | [optional] 
**notes** | **bool, date, datetime, dict, float, int, list, str, none_type** | Allows you to provide text that will be displayed to the transcriber when the job is processed. An HTML included will be escaped. | [optional] 
**return_iwp** | [**[IWPEnum]**](IWPEnum.md) | Allows you to receive additional callbacks when interim versions of the job are completed. If you specified a callback_url, then a callback will sent for FINAL regardless of the value of this option. | [optional]  if omitted the server will use the default value of []
**generate_media_intelligence_iwp** | [**[IWPEnum]**](IWPEnum.md) | Requests that media intelligence be generated for the specified interim/final versions of the transcript. Media intelligence data is added to the ElementList and can be retrieve using the get_elementlist API call. See [ElementList](https://cielo24.readthedocs.io/en/latest/output_formats/elementlist.html#media-intelligence-label) for details. | [optional]  if omitted the server will use the default value of []
**speaker_id** | **str** | Requests that speaker names be identified. | [optional]  if omitted the server will use the default value of "false"
**audio_description** | **str** | Requests that all noises and sounds be identified. | [optional]  if omitted the server will use the default value of "false"
**on_screen_text** | **str** | Requests that any text that appears in the media be added to the transcription. | [optional]  if omitted the server will use the default value of "false"
**music_lyrics** | **str** | Requests that lyrics to songs be transcribed instead of labeled [MUSIC]. | [optional]  if omitted the server will use the default value of "false"
**custom_special_handling** | **str** | Requests that transcribers follow submitted instruction set. | [optional]  if omitted the server will use the default value of "false"
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


