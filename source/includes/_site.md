# Site

Read and write information about site(s) you own.

## Get list of Sites

```shell
$ http "https://api.sight-line.uk/sites/" \
    "Authorization: Token $auth_token"
```
```json
[
    {
        "uuid": "b07e9578-24e5-47de-8c56-ed82508f9ed2",
        "first_sign": {
            "uuid": "1cbf7316-6ed3-4cbe-a9d7-27a7c9b04e66",
            "owner_uuid": "60fe3539-056a-4333-912f-cae8ed206388",
            "owner_email": "streetworks@streetworks.info",
            "device_id": 1,
            "major_id": 2,
            "minor_id": 1,
            "latitude": 51.5349945,
            "longitude": -0.0552559,
            "sign_type": "RIGHT"
        },
        "second_sign": {
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
        "third_sign": null,
        "fourth_sign": null,
        "owner_uuid": "60fe3539-056a-4333-912f-cae8ed206388",
        "owner_email": "streetworks@streetworks.info",
        "latitude": 51.5507863,
        "longitude": -0.09123755,
        "address": "45 Vyner St, Bethnal Green",
        "layout": {
            "display": "Temporary footway in road",
            "value": "TFIR"
        },
        "length": {
            "display": "5 to 10 metres",
            "value": "FIVE_TO_TEN"
        },
        "occupation_end_date": "2016-08-19",
        "notes": "",
        "entrances": ["Vehicle access", "Boots", "McDonald's"],
        "active": true,
        "source": "streetworks"
    },
    {
        "uuid": "cd54227c-664c-4631-bc19-d42a0440b5f7",
        "first_sign": {
            "uuid": "e01c6991-32ab-4b84-850b-9cca9d6f1490",
            "owner_uuid": "60fe3539-056a-4333-912f-cae8ed206388",
            "owner_email": "streetworks@streetworks.info",
            "device_id": 1,
            "major_id": 1,
            "minor_id": 1,
            "latitude": 51.5347709,
            "longitude": -0.1440306,
            "sign_type": "LEFT"
        },
        ...
        "source": "streetworks"
    }
]
```

Returns list of Sites you own.

## Get Site

```shell
$ http "https://api.sight-line.uk/sites/$site_uuid" \
    "Authorization: Token $auth_token" 
```
```json
    {
        "uuid": "b07e9578-24e5-47de-8c56-ed82508f9ed2",
        "first_sign": {
            "uuid": "1cbf7316-6ed3-4cbe-a9d7-27a7c9b04e66",
            "owner_uuid": "60fe3539-056a-4333-912f-cae8ed206388",
            "owner_email": "streetworks@streetworks.info",
            "device_id": 1,
            "major_id": 2,
            "minor_id": 1,
            "latitude": 51.5349945,
            "longitude": -0.0552559,
            "sign_type": "RIGHT"
        },
        "second_sign": {
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
        "third_sign": null,
        "fourth_sign": null,
        "owner_uuid": "60fe3539-056a-4333-912f-cae8ed206388",
        "owner_email": "streetworks@streetworks.info",
        "latitude": 51.5507863,
        "longitude": -0.09123755,
        "address": "45 Vyner St, Bethnal Green",
        "layout": {
            "display": "Temporary footway in road",
            "value": "TFIR"
        },
        "length": {
            "display": "5 to 10 metres",
            "value": "FIVE_TO_TEN"
        },
        "occupation_end_date": "2016-08-19",
        "notes": "",
        "entrances": ["Vehicle access", "Boots", "McDonald's"],
        "active": true,
        "source": "streetworks"
    }
```

Returns information about a specific Site.

##### Request arguments

<span class="hide">Parameter</span> | <span class="hide">Description</span>
------------------------------------|--------------------------------------
`site_uuid`<br><span class="label notice">Required</span>|The uuid of the Site.

## Create a Site

```shell
$ http --form POST "https://api.sight-line.uk/sites" \
    "Authorization: Token 1086d9ca78c169d39fb850f7f4ce3d87569303a0" \
    "address=45 Vyner St, Bethnal Green" \
    "length=FIVE_TO_TEN" \
    "layout=TFIR" \
    "occupation_end_date=2016-08-19" \
    "notes=Faulty lighting" \
    "entrances:='["Vehicle access", "Boots", "McDonald's"]'" \
    "source=streetworks" \
    "active=true" \
    "first_sign:='{"device_id": 1, "major_id": 2, "minor_id": 1, "latitude": 51.5349945, "longitude": -0.0552559, "sign_type": "RIGHT"}'" \
    "second_sign:='{"device_id": 1, "major_id": 2, "minor_id": 2, "latitude": 51.5665781, "longitude": -0.1272192, "sign_type": "LEFT"}'" 
```
```json
    {
        "uuid": "b07e9578-24e5-47de-8c56-ed82508f9ed2",
        "first_sign": {
            "uuid": "1cbf7316-6ed3-4cbe-a9d7-27a7c9b04e66",
            "owner_uuid": "60fe3539-056a-4333-912f-cae8ed206388",
            "owner_email": "streetworks@streetworks.info",
            "device_id": 1,
            "major_id": 2,
            "minor_id": 1,
            "latitude": 51.5349945,
            "longitude": -0.0552559,
            "sign_type": "RIGHT"
        },
        "second_sign": {
            "uuid": "c643db34-6875-49fc-a579-8010b6e52169",
            "owner_uuid": "60fe3539-056a-4333-912f-cae8ed206388",
            "owner_email": "streetworks@streetworks.info",
            "device_id": 1,
            "major_id": 2,
            "minor_id": 2,
            "latitude": 51.5665781,
            "longitude": -0.1272192,
            "sign_type": "LEFT"
        },
        "third_sign": null,
        "fourth_sign": null,
        "owner_uuid": "60fe3539-056a-4333-912f-cae8ed206388",
        "owner_email": "streetworks@streetworks.info",
        "latitude": 51.5507863,
        "longitude": -0.09123755,
        "address": "45 Vyner St, Bethnal Green",
        "layout": {
            "display": "Temporary footway in road",
            "value": "TFIR"
        },
        "length": {
            "display": "5 to 10 metres",
            "value": "FIVE_TO_TEN"
        },
        "occupation_end_date": "2016-08-19",
        "notes": "Faulty lighting",
        "entrances": ["Vehicle access", "Boots", "McDonald's"],
        "active": true,
        "source": "streetworks"
    }
```

Creates a Site.

Pre-existing Signs attached to this Site will be re-associated to this Site.

##### Request arguments

<span class="hide">Parameter</span> | <span class="hide">Description</span>
------------------------------------|--------------------------------------
`length`<br><span class="label">Required</span>|Site's Length. See [**Site Length choices**](#get-site-length-choices)
`layout`<br><span class="label">Required</span>|Site's Layout. See [**Site Layout choices**](#get-site-layout-choices)
`occupation_end_date`<br><span class="label">Required</span>|When the Site should no longer be present. (Date in format `YYYY-MM-DD`)
`address`<br><span class="label">Optional</span>|Site's address (String)
`notes`<br><span class="label">Optional</span>|Additional notes (String)
`entrances`<br><span class="label">Optional</span>|List of entrances along the path from Right Sign to Left sign (Array of Strings)
`source`<br><span class="label">Optional</span>|Free form field to identify unique source data such as engineer's name or gang name (String)
`active`<br><span class="label">Optional</span>|If site is active or not (Boolean)
`first_sign`<br><span class="label">Optional</span>|Sign object. See [**Sign**](#sign)
`second_sign`<br><span class="label">Optional</span>|Sign object. See [**Sign**](#sign)
`third_sign`<br><span class="label">Optional</span>|Sign object. See [**Sign**](#sign)
`fourth_sign`<br><span class="label">Optional</span>|Sign object. See [**Sign**](#sign)

##### Response arguments

<span class="hide">Parameter</span> | <span class="hide">Description</span>
------------------------------------|--------------------------------------
`uuid`|Site's uuid
`owner_uuid`|Site owner's uuid
`owner_email`|Site owner's email
`site_length`|Site's Length. See [**Site Length choices**](#get-site-length-choices)
`site_layout`|Site's Layout. See [**Site Layout choices**](#get-site-layout-choices)
`occupation_end_date`|When the Site should no longer be present. (Date in format `YYYY-MM-DD`)
`address`|Site address
`notes`|Additional notes (String)
`entrances`|List of entrances along the path from Right Sign to Left sign (Array of Strings)
`source`|Free form field to identify unique source data such as engineer's name or gang name (String)
`active`|Site's active value (Boolean)
`latitude`|Latitude mid-point calculated using sign 1 and sign 2. Null if less than 2 signs. (Float)
`longitude`|Longitude mid-point calculated using sign 1 and sign 2. Null if less than 2 signs. (Float)
`first_sign`|Sign object. See [**Sign**](#sign)
`second_sign`|Sign object. See [**Sign**](#sign)
`third_sign`|Sign object. See [**Sign**](#sign)
`fourth_sign`|Sign object. See [**Sign**](#sign)

## Update Site

```shell
$ http --form POST "https://api.sight-line.uk/sites/$site_uuid" \
    "Authorization: Token $auth_token" 

```
```json
    {
        "uuid": "b07e9578-24e5-47de-8c56-ed82508f9ed2",
        "first_sign": {
            "uuid": "1cbf7316-6ed3-4cbe-a9d7-27a7c9b04e66",
            "owner_uuid": "60fe3539-056a-4333-912f-cae8ed206388",
            "owner_email": "streetworks@streetworks.info",
            "device_id": 1,
            "major_id": 2,
            "minor_id": 1,
            "latitude": 51.5349945,
            "longitude": -0.0552559,
            "sign_type": "RIGHT"
        },
        "second_sign": {
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
        "third_sign": null,
        "fourth_sign": null,
        "owner_uuid": "60fe3539-056a-4333-912f-cae8ed206388",
        "owner_email": "streetworks@streetworks.info",
        "latitude": 51.5507863,
        "longitude": -0.09123755,
        "address": "45 Vyner St, Bethnal Green",
        "layout": {
            "display": "Temporary footway in road",
            "value": "TFIR"
        },
        "length": {
            "display": "5 to 10 metres",
            "value": "FIVE_TO_TEN"
        },
        "occupation_end_date": "2016-08-19",
        "notes": "",
        "entrances": ["Vehicle access", "Boots", "McDonald's"],
        "active": true,
        "source": "streetworks"
    }
```

Update a specific Site.

Pre-existing Signs attached to this Site will be re-associated to this Site.

##### Request arguments

<span class="hide">Parameter</span> | <span class="hide">Description</span>
------------------------------------|--------------------------------------
`site_uuid`<br><span class="label notice">Required</span>|The uuid of the Site.
`length`<br><span class="label">Required</span>|Site's Length. See [**Site Length choices**](#get-site-length-choices)
`layout`<br><span class="label">Required</span>|Site's Layout. See [**Site Layout choices**](#get-site-layout-choices)
`occupation_end_date`<br><span class="label">Required</span>|When the Site should no longer be present. (Date in format `YYYY-MM-DD`)
`address`<br><span class="label">Optional</span>|Site's address (String)
`notes`<br><span class="label">Optional</span>|Additional notes (String)
`entrances`<br><span class="label">Optional</span>|List of entrances along the path from Right Sign to Left sign (Array of Strings)
`source`<br><span class="label">Optional</span>|Free form field to identify unique source data such as engineer's name or gang name (String)
`active`<br><span class="label">Optional</span>|If site is active or not (Boolean)
`first_sign`<br><span class="label">Optional</span>|Sign object. See [**Sign**](#sign)
`second_sign`<br><span class="label">Optional</span>|Sign object. See [**Sign**](#sign)
`third_sign`<br><span class="label">Optional</span>|Sign object. See [**Sign**](#sign)
`fourth_sign`<br><span class="label">Optional</span>|Sign object. See [**Sign**](#sign)

##### Response arguments

<span class="hide">Parameter</span> | <span class="hide">Description</span>
------------------------------------|--------------------------------------
`uuid`|Site's uuid
`owner_uuid`|Site owner's uuid
`owner_email`|Site owner's email
`site_length`|Site's Length. See [**Site Length choices**](#get-site-length-choices)
`site_layout`|Site's Layout. See [**Site Layout choices**](#get-site-layout-choices)
`occupation_end_date`|When the Site should no longer be present. (Date in format `YYYY-MM-DD`)
`address`|Site address
`notes`|Additional notes (String)
`entrances`<br><span class="label">Optional</span>|List of entrances along the path from Right Sign to Left sign (Array of Strings)
`source`|Free form field to identify unique source data such as engineer's name or gang name (String)
`active`|Site's active value (Boolean)
`latitude`|Latitude mid-point calculated using sign 1 and sign 2. Null if less than 2 signs. (Float)
`longitude`|Longitude mid-point calculated using sign 1 and sign 2. Null if less than 2 signs. (Float)
`first_sign`|Sign object. See [**Sign**](#sign)
`second_sign`|Sign object. See [**Sign**](#sign)
`third_sign`|Sign object. See [**Sign**](#sign)
`fourth_sign`|Sign object. See [**Sign**](#sign)

## Delete a Site

```shell
$ http DELETE "https://api.sight-line.uk/sites/$site_uuid" \
    "Authorization: Token $auth_token"
```
```
STATUS: HTTP 204 No Content
```

Delete a specific site.
<br><span class="label notice">WARNING: This will delete all associated Signs.</span>

##### Request Arguments

<span class="hide">Parameter</span> | <span class="hide">Description</span>
------------------------------------|--------------------------------------
`site_uuid`<br><span class="label notice">Required</span>|The uuid of the Site.

## Get Site Length choices

```shell
$ http "https://api.sight-line.uk/sites/length-choices/" \
    "Authorization: Token $auth_token"
```
```json
[
    [
        "LESS_THAN_FIVE",
        "Less than 5 metres"
    ],
    [
        "FIVE_TO_TEN",
        "5 to 10 metres"
    ],
    [
        "TEN_TO_TWENTY",
        "10 to 20 metres"
    ],
    [
        "GREATER_THAN_TWENTY",
        "More than 20 metres"
    ]
]
```

Returns a list of Site Length choices to use when creating/updating a Site.
The first value of each item is the `API value` and the second is the `Display value`.

## Get Site Layout choices

```shell
$ http "https://api.sight-line.uk/sites/layout-choices/" \
    "Authorization: Token $auth_token"
```
```json
[
    [
        "NFO",
        "No footway obstruction"
    ],
    [
        "FC",
        "Footway closed"
    ],
    [
        "PFO",
        "Partial footway obstruction"
    ],
    [
        "TFIR",
        "Temporary footway in road"
    ]
]
```

Returns a list of Site Layout choices to use when creating/updating a Site.
The first value of each item is the `API value` and the second is the `Display value`.

