# Authentication

The Sight Line API uses Token Authentication.

## Acquiring a Authentication Token

Authentication Tokens are granted on request. 

Please email sightline [at] rossatkin [dot] com with a brief explanation of the reason for your request along with the following details:

* Email
* Organisation
* Address
* Telephone

## Authenticating Requests

```shell
$ http "https://api.sight-line.uk/sites/" \
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
    ...
    "active": true,
    "source": "streetworks"
}
```

**All** requests must be authenticated with an access token supplied in the `Authorization` header using the `Token` scheme. 

Clients may only have *one* active access token at a time, per user. 

Acquiring a new access token will invalidate any other token you own for that user.
