# PROFILE API

ZepsonSMS Profile API allows you to retrieve your total remaining sms unit, used sms unit, and your profile information.

## API Endpoint

```
https://zepsonsms.co.tz/api/v3/me
```

Parameters

| Parameter | Required | Description |
| --- | --- | --- |
| Authorization | YES | When calling our API, send your api token with the authentication type set as `Bearer` (Example: `Authorization: Bearer {api_token}`) |
| Accept | YES | Set to `application/json` |

## View sms unit

API Endpoint

```
https://zepsonsms.co.tz/api/v3/balance
```

Example request

```bash
curl -X GET https://zepsonsms.co.tz/api/v3/balance\
-H 'Authorization: Bearer 7|xs6pv2dspHJq8sWLhrpNFH5YLilMRQcVxLwSw2Sd'
```

Returns

Returns a contact object if the request was successful.

```json
{
    "status": "success",
    "data": "sms unit with all details",
}
```

If the request failed, an error object will be returned.

```json
{
    "status": "error",
    "message" : "A human-readable description of the error."
}
```

## View Profile

API Endpoint

```
https://zepsonsms.co.tz/api/v3/me
```

Example request

```bash
curl -X GET https://zepsonsms.co.tz/api/v3/me\
-H 'Authorization: Bearer 7|xs6pv2dspHJq8sWLhrpNFH5YLilMRQcVxLwSw2Sd'
```

Returns

Returns a contact object if the request was successful.

```json
{
    "status": "success",
    "data": "profile data with all details",
}
```

If the request failed, an error object will be returned.

```json
{
    "status": "error",
    "message" : "A human-readable description of the error."
}
```