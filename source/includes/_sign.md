# Sign

## Get list of Signs

```shell
$ http "https://api.sight-line.uk/sites/sign/" \
    "Authorization: Token $auth_token"
```
```json
[
    {
        "uuid": "c643db34-6875-49fc-a579-8010b6e52169",
        "owner_uuid": "60fe3539-056a-4333-912f-cae8ed206388",
        "owner_email": "streetworks@streetworks.info",
        "device_id": 1,
        "major_id": 2,
        "minor_id": 2,
        "latitude": 51.5665781,
        "longitude": -0.1272192,
        "sign_type": "RIGHT"
    },
    ...
    {
        "uuid": "e01c6991-32ab-4b84-850b-9cca9d6f1490",
        "owner_uuid": "60fe3539-056a-4333-912f-cae8ed206388",
        "owner_email": "streetworks@streetworks.info",
        "device_id": 1,
        "major_id": 1,
        "minor_id": 1,
        "latitude": 51.5347709,
        "longitude": -0.1440306,
        "sign_type": "LEFT"
    }
]
```

Returns list of Signs you own.

## Get a Sign

```shell
$ http "https://api.sight-line.uk/sites/sign/$sign_uuid" \
    "Authorization: Token $auth_token"  
```
```json
{
    "uuid": "1cbf7316-6ed3-4cbe-a9d7-27a7c9b04e66",
    "owner_uuid": "60fe3539-056a-4333-912f-cae8ed206388",
    "owner_email": "streetworks@streetworks.info",
    "device_id": 1,
    "major_id": 2,
    "minor_id": 1,
    "latitude": 51.5349945,
    "longitude": -0.0552559,
    "sign_type": "RIGHT"
}
```

Returns information about a specific Sign.

##### Request arguments

<span class="hide">Parameter</span> | <span class="hide">Description</span>
------------------------------------|--------------------------------------
`sign_uuid`<br><span class="label notice">Required</span>|The uuid of the Sign.

## Create a Sign

```shell
$ http --form POST "https://api.sight-line.uk/sites/sign/" \
    "Authorization: Token $auth_token" \
    "device_id=$device_id" \
    "major_id=$major_id" \
    "minor_id=$minor_id" \
    "latitude=$latitude" \
    "longitude=$longitude" \
    "sign_type=$sign_type" 
```
```json
{
    "uuid": "e01c6991-32ab-4b84-850b-9cca9d6f1490",
    "owner_uuid": "60fe3539-056a-4333-912f-cae8ed206388",
    "owner_email": "streetworks@streetworks.info",
    "device_id": 1,
    "major_id": 1,
    "minor_id": 1,
    "latitude": 51.5347709,
    "longitude": -0.1440306,
    "sign_type": "LEFT"
}
```

Creates a specified Sign.

The combination of Device, Major and Minor ID's must be unique otherwise they will replace an existing Sign.

##### Request arguments

<span class="hide">Parameter</span> | <span class="hide">Description</span>
------------------------------------|--------------------------------------
`device_id`<br><span class="label notice">Required</span>|Device ID (Integer)
`major_id`<br><span class="label notice">Required</span>|Major ID (Integer)
`minor_id`<br><span class="label notice">Required</span>|Minor ID (Integer)
`latitude`<br><span class="label notice">Required</span>|Latitude (Float)
`longitude`<br><span class="label notice">Required</span>|Longitude (Float)
`sign_type`<br><span class="label notice">Required</span>|Sign Type of the sign. See [**Sign Type choices**](#get-sign-types-choices)

##### Response arguments

<span class="hide">Parameter</span> | <span class="hide">Description</span>
------------------------------------|--------------------------------------
`uuid`|Sign's uuid
`owner_uuid`|Sign owner's uuid
`owner_email`|Sign owner's email
`device_id`|Device ID (Integer)
`major_id`|Major ID (Integer)
`minor_id`|Minor ID (Integer)
`latitude`|Latitude (Float)
`longitude`|Longitude (Float)
`sign_type`|Sign Type of the sign. See [**Sign Type choices**](#get-sign-types-choices)


## Update a Sign

```shell
$ http --form PATCH "https://api.sight-line.uk/sites/sign/$sign_uuid" \
    "Authorization: Token $auth_token" \
    "device_id=$device_id" \
    "major_id=$major_id" \
    "minor_id=$minor_id" \
    "latitude=$latitude" \
    "longitude=$longitude" \
    "sign_type=$sign_type" 
```
```json
{
    "uuid": "e01c6991-32ab-4b84-850b-9cca9d6f1490",
    "owner_uuid": "60fe3539-056a-4333-912f-cae8ed206388",
    "owner_email": "streetworks@streetworks.info",
    "device_id": 1,
    "major_id": 1,
    "minor_id": 1,
    "latitude": 51.5347709,
    "longitude": -0.1440306,
    "sign_type": "LEFT"
}
```

Updates specified Sign. If successful, will return the updated Sign reponse.

The combination of Device, Major and Minor ID's must be unique otherwise they will replace an existing Sign.

##### Request arguments

<span class="hide">Parameter</span> | <span class="hide">Description</span>
------------------------------------|--------------------------------------
`sign_uuid`<br><span class="label">Optional</span>|Sign's uuid
`device_id`<br><span class="label">Optional</span>|Device ID (Integer)
`major_id`<br><span class="label">Optional</span>|Major ID (Integer)
`minor_id`<br><span class="label">Optional</span>|Minor ID (Integer)
`latitude`<br><span class="label">Optional</span>|Latitude (Float)
`longitude`<br><span class="label">Optional</span>|Longitude (Float)
`sign_type`<br><span class="label">Optional</span>|Sign Type of the sign. See [**Sign Type choices**](#get-sign-types-choices)

##### Response arguments

<span class="hide">Parameter</span> | <span class="hide">Description</span>
------------------------------------|--------------------------------------
`uuid`|Sign's uuid
`owner_uuid`|Sign owner's uuid
`owner_email`|Sign owner's email
`device_id`|Device ID (Integer)
`major_id`|Major ID (Integer)
`minor_id`|Minor ID (Integer)
`latitude`|Latitude (Float)
`longitude`|Longitude (Float)
`sign_type`|Sign Type of the sign. See [**Sign Type choices**](#get-sign-types-choices)

## Delete Sign

```shell
$ http DELETE "https://api.sight-line.uk/sites/sign/$sign_uuid" \
    "Authorization: Token $auth_token"
```
```
STATUS: HTTP 204 No Content
```

Deletes a specified Sign.
<br><span class="label notice">WARNING: This will delete the associated Site.</span>

##### Request arguments

Deletes a specified Sign.

<span class="hide">Parameter</span> | <span class="hide">Description</span>
------------------------------------|--------------------------------------
`sign_uuid`<br><span class="label notice">Required</span>|The uuid of the Sign.

## Get Sign Types choices

```shell
$ http "https://api.sight-line.uk/sites/type-choices/" \
    "Authorization: Token $auth_token"
```
```json
[
    [
        "LEFT",
        "Left"
    ],
    [
        "RIGHT",
        "Right"
    ],
    [
        "CROSS",
        "Cross"
    ],
    [
        "BARRIER",
        "Barrier"
    ]
]
```

Returns a list of Sign Type choices to use when creating/updating a Sign.
The first value of each item is the `API value` and the second is the `Display value`.
