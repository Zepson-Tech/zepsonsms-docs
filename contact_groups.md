# CONTACT GROUPS API

Zepson Sms Contact Groups API allows you to manage contact groups that are identified by a unique random ID. Use this ID to create, view, update or delete groups.

## API Endpoint

```
https://zepsonsms.co.tz/api/v3/contacts
```

### ### Parameters

| Parameter | Required      | Description               |
| --------- | ------------- | ------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| #         | Authorization | YES                       | When calling our API, send your api token with the authentication type set as `Bearer` (### Example: `Authorization: Bearerjson {api_token}`) |
| Accept    | YES           | Set to `application/json` |

## Create a group

Creates a new group object. Zepson Sms returns the created group object with each request.

### API Endpoint

```
https://zepsonsms.co.tz/api/v3/contacts
```

### Parameters

| Parameter | Required | Type   | Description           |
| --------- | -------- | ------ | --------------------- |
| name      | YES      | string | The name of the group |

#### Example request

```bash
curl -X POST https://zepsonsms.co.tz/api/v3/contacts\
-H 'Authorization: Bearer 7|xs6pv2dspHJq8sWLhrpNFH5YLilMRQcVxLwSw2Sd'\
-d "name=codeglen"
```

Returns

Returns a contact object if the request was successful.

```json
{
    "status": "success",
    "data": "group data with all details",
}
```

If the request failed, an error object will be returned.

```json
{
    "status": "error",
    "message" : "A human-readable description of the error."
}
```

## View a group

Retrieves the information of an existing group. You only need to supply the unique group ID that was returned upon creation or receiving.

API Endpoint

```bash
https://zepsonsms.co.tz/api/v3/contactsjson/{group_id}/show/
```

### Parameters

| Parameter | Required | Type   | Description          |
| --------- | -------- | ------ | -------------------- |
| group_id  | YES      | string | Contact Groups `uid` |

#### Example request

```bash
curl -X POST https://zepsonsms.co.tz/api/v3/contacts/6065ecdc9184a/show\
-H 'Authorization: Bearer 7|xs6pv2dspHJq8sWLhrpNFH5YLilMRQcVxLwSw2Sd'
```

Returns

Returns a contact object if the request was successful.

```json
{
    "status": "success",
    "data": "group data with all details",
}
```

If the request failed, an error object will be returned.

```json
{
    "status": "error",
    "message" : "A human-readable description of the error."
}
```

## Update a group

Updates an existing group. You only need to supply the unique ID that was returned upon creation.

API Endpoint

```bash
https://zepsonsms.co.tz/api/v3/contactsjson/{group_id}
```

### Parameters

| Parameter | Required | Type   | Description          |
| --------- | -------- | ------ | -------------------- |
| group_id  | YES      | string | Contact Groups `uid` |
| name      | YES      | string | New group name       |

#### Example request

```bash
curl -X PATCH https://zepsonsms.co.tz/api/v3/contacts/6065ecdc9184a\
-H 'Authorization: Bearer 7|xs6pv2dspHJq8sWLhrpNFH5YLilMRQcVxLwSw2Sd'\
-d "name=codeglen new"
```

Returns

Returns a contact object if the request was successful.

```json
{
    "status": "success",
    "data": "groups data with all details",
}
```

If the request failed, an error object will be returned.

```json
{
    "status": "error",
    "message" : "A human-readable description of the error."
}
```

## Delete a group

Deletes an existing group. You only need to supply the unique id that was returned upon creation.

API Endpoint

```bash
https://zepsonsms.co.tz/api/v3/contactsjson/{group_id}
```

### Parameters

| Parameter | Required | Type   | Description          |
| --------- | -------- | ------ | -------------------- |
| group_id  | YES      | string | Contact Groups `uid` |

#### Example request

```bash
curl -X DELETE https://zepsonsms.co.tz/api/v3/contacts/6065ecdc9184a\
-H 'Authorization: Bearer 7|xs6pv2dspHJq8sWLhrpNFH5YLilMRQcVxLwSw2Sd'
```

Returns

Returns a contact object if the request was successful.

```json
{
    "status": "success",
    "data": "null",
}
```

If the request failed, an error object will be returned.

```json
{
    "status": "error",
    "message" : "A human-readable description of the error."
}
```

## View all groups

API Endpoint

```bash
https://zepsonsms.co.tz/api/v3/contacts/
```

#### Example request

```bash
curl -X GET https://zepsonsms.co.tz/api/v3/contacts\
-H 'Authorization: Bearer 7|xs6pv2dspHJq8sWLhrpNFH5YLilMRQcVxLwSw2Sd'
```

Returns

Returns a contact object if the request was successful.

```json
{
    "status": "success",
    "data": "group data with pagination",
}
```

If the request failed, an error object will be returned.

```json
{
    "status": "error",
    "message" : "A human-readable description of the error."
}
```
