# SMS API

Zepson Sms SMS API allows you to send and receive SMS messages to and from any country in the world through a REST API. Each message is identified by a unique random ID so that users can always check the status of a message using the given endpoint.

### API Endpoint

```
https://zepsonsms.co.tz/api/v3/sms/send
```

Parameters

| Parameter | Required | Description |
| --- | --- | --- |
| Authorization | YES | When calling our API, send your api token with the authentication type set as `Bearer` (Example: `Authorization: Bearerjson {api_token}`) |
| Accept | YES | Set to `application/json` |

## Send outbound SMS

Zepson Sms's Programmable SMS API enables you to programmatically send SMS messages from your web application. First, you need to create a new message object. Zepson Sms returns the created message object with each request.

Send your first SMS message with this example request.

### API Endpoint

```
https://zepsonsms.co.tz/api/v3/sms/send
```

Parameters

| Parameter | Required | Type | Description |
| --- | --- | --- | --- |
| recipient | YES | string | Number to send message |
| sender_id | YES | string | The sender of the message. This can be a telephone number (including country code) or an alphanumeric string. In case of an alphanumeric string, the maximum length is 11 characters. |
| message | YES | string | The body of the SMS message. |

Example request

```bash
curl -X POST https://zepsonsms.co.tz/api/v3/sms/send\
-H 'Authorization: Bearer 7|xs6pv2dspHJq8sWLhrpNFH5YLilMRQcVxLwSw2Sd'\
-d "recipient=31612345678"\
-d "sender_id=YourName"\
-d "message=This is a test message"
```

Returns

Returns a contact object if the request was successful.

```json
{
    "status": "success",
    "data": "sms reports with all details",
}
```

If the request failed, an error object will be returned.

```json
{
    "status": "error",
    "message" : "A human-readable description of the error."
}
```

## View an SMS

You can use Zepson Sms's SMS API to retrieve information of an existing inbound or outbound SMS message.

You only need to supply the unique message id that was returned upon creation or receiving.

### API Endpoint

```
https://zepsonsms.co.tz/api/v3/smsjson/{uid}
```

Parameters

| Parameter | Required | Type | Description |
| --- | --- | --- | --- |
| uid | YES | string | A unique random uid which is created on the Zepson Sms platform and is returned upon creation of the object. |

Example request

```bash
curl -X GET https://zepsonsms.co.tz/api/v3/sms/606812e63f78b\
-H 'Authorization: Bearer 7|xs6pv2dspHJq8sWLhrpNFH5YLilMRQcVxLwSw2Sd'
```

Returns

Returns a contact object if the request was successful.

```json
{
    "status": "success",
    "data": "sms data with all details",
}
```

If the request failed, an error object will be returned.

```json
{
    "status": "error",
    "message" : "A human-readable description of the error."
}
```

## View all messages

### API Endpoint

```
https://zepsonsms.co.tz/api/v3/sms/
```

Example request

```bash
curl -X GET https://zepsonsms.co.tz/api/v3/sms\
-H 'Authorization: Bearer 7|xs6pv2dspHJq8sWLhrpNFH5YLilMRQcVxLwSw2Sd'
```

Returns

Returns a contact object if the request was successful.

```json
{
    "status": "success",
    "data": "sms reports with pagination",
}
```

If the request failed, an error object will be returned.

```json
{
    "status": "error",
    "message" : "A human-readable description of the error."
}
```