# CONTACTS API


ZepsonSMS Contacts API helps you manage contacts that are identified by a unique random ID. Using this ID, you can create, view, update, or delete contacts. This API works as a collection of customer-specific contacts that allows you to group them and assign custom values that you can later use when sending SMS template messages.

The Contacts API uses HTTP verbs and a RESTful endpoint structure with an access key that is used as the API Authorization. Request and response payloads are formatted as JSON using UTF-8 encoding and URL encoded values.

### API Endpoint

```
https://zepsonsms.co.tz/api/v3/contacts
```

### Parameters

| Parameter | Required | Description |
| --- | --- | --- |
| Authorization | YES | When calling our API, send your api token with the authentication type set as `Bearer` (Example: `Authorization: Bearer {api_token}`) |
| Accept | YES | Set to `application/json` |

## Create a contact

Creates a new contact object. Zepson Sms returns the created contact object with each request.

### API Endpoint

```
https://zepsonsms.co.tz/api/v3/contactsjson/{group_id}/store
```

### Parameters

| Parameter | Required | Type | Description |
| --- | --- | --- | --- |
| group_id | YES  |string | Contact Groups `uid` |
| phone | YES | number | The phone number of the contact. |
| first_name | No | string | The first name of the contact. |
| last_name | No | string | The last name of the contact. |

Example request

```bash
curl -X POST https://zepsonsms.co.tz/api/v3/contacts/6065ecdc9184a/store\
-H 'Authorization: Bearer 7|xs6pv2dspHJq8sWLhrpNFH5YLilMRQcVxLwSw2Sd'\
-d "phone=31612345678"
```

Returns

Returns a contact object if the request was successful.

```json
{
    "status": "success",
    "data": "contacts data with all details",
}
```

If the request failed, an error object will be returned.

```json
{
    "status": "error",
    "message" : "A human-readable description of the error."
}
```

## View a contact

Retrieves the information of an existing contact. You only need to supply the unique contact uid and group uid that was returned upon creation or receiving.

### API Endpoint

```
https://zepsonsms.co.tz/api/v3/contactsjson/{group_id}/searchjson/{uid}
```

### Parameters

| Parameter | Required | Type | Description |
| --- | --- | --- | --- |
| group_id | YES  | string | Contact Groups `uid` |
| uid | YES | string | Contact `uid` |

Example request

```bash
curl -X POST https://zepsonsms.co.tz/api/v3/contacts/6065ecdc9184a/search/606732aec8705\
-H 'Authorization: Bearer 7|xs6pv2dspHJq8sWLhrpNFH5YLilMRQcVxLwSw2Sd'
```

Returns

Returns a contact object if the request was successful.

```json
{
    "status": "success",
    "data": "contacts data with all details",
}
```

If the request failed, an error object will be returned.

```json
{
    "status": "error",
    "message" : "A human-readable description of the error."
}
```

## Update a contact

Updates an existing contact. You only need to supply the unique uid of contact and contact group uid that was returned upon creation.

### API Endpoint

```
https://zepsonsms.co.tz/api/v3/contactsjson/{group_id}/updatejson/{uid}
```

### Parameters

| Parameter | Required | Type | Description |
| --- | --- | --- | --- |
| group_id | YES | string | Contact Groups `uid` |
| uid | YES | string | Contact `uid` |
| phone | YES | number | The phone number of the contact. |
| first_name | No | string | The first name of the contact. |
| last_name | No | string | The last name of the contact. |

Example request

```bash
curl -X PATCH https://zepsonsms.co.tz/api/v3/contacts/6065ecdc9184a/update/606732aec8705\
-H 'Authorization: Bearer 7|xs6pv2dspHJq8sWLhrpNFH5YLilMRQcVxLwSw2Sd'\
-d "phone=31612345678"
```

Returns

Returns a contact object if the request was successful.

```json
{
    "status": "success",
    "data": "contacts data with all details",
}
```

If the request failed, an error object will be returned.

```json
{
    "status": "error",
    "message" : "A human-readable description of the error."
}
```

## Delete a contact

Deletes an existing contact. You only need to supply the unique contact uid and group uid that was returned upon creation.

### API Endpoint

```
https://zepsonsms.co.tz/api/v3/contactsjson/{group_id}/deletejson/{uid}
```

### Parameters

| Parameter | Required | Type | Description |
| --- | --- | --- | --- |
| group_id |YES | string | Contact Groups `uid` |
| uid | YES | string | Contact `uid` |

Example request

```bash
curl -X DELETE https://zepsonsms.co.tz/api/v3/contacts/6065ecdc9184a/delete/606732aec8705\
-H 'Authorization: Bearer 7|xs6pv2dspHJq8sWLhrpNFH5YLilMRQcVxLwSw2Sd'
```

Returns

Returns a contact object if the request was successful.

```json
{
    "status": "success",
    "data": "contacts data with all details",
}
```

If the request failed, an error object will be returned.

```json
{
    "status": "error",
    "message" : "A human-readable description of the error."
}
```

## View all contacts in group

### API Endpoint

```
https://zepsonsms.co.tz/api/v3/contactsjson/{group_id}/all
```

### Parameters

| Parameter | Required | Type | Description |
| --- | --- | --- | --- |
| group_id |

YES

 | string | Contact Groups `uid` |

Example request

```bash
curl -X POST https://zepsonsms.co.tz/api/v3/contacts/6065ecdc9184a/all\
-H 'Authorization: Bearer 7|xs6pv2dspHJq8sWLhrpNFH5YLilMRQcVxLwSw2Sd'
```

Returns

Returns a contact object if the request was successful.

```json
{
    "status": "success",
    "data": "contacts data with pagination",
}
```

If the request failed, an error object will be returned.

```json
{
    "status": "error",
    "message" : "A human-readable description of the error."
}
```