# Report

Errors with specific Sites can be reported.

Authentication is **NOT** required for this API.

## Report a specific site

```shell
$ http POST "https://api.sight-line.uk/sites/report/" \
    "Authorization: Token $auth_token" \
    "site==$site_uuid"
```
```json
{
  "uuid": "91d3536e-bb5b-4b8b-9dec-4fae3a35528e",
  "site": "cd54227c-664c-4631-bc19-d42a0440b5f7"
}
```
Flags a specific Site as having erroneous data.

<span class="hide">Parameter</span> | <span class="hide">Description</span>
------------------------------------|--------------------------------------
`site`<br><span class="label notice">Required</span>|The uuid of the Site.

##### Response arguments

<span class="hide">Parameter</span> | <span class="hide">Description</span>
------------------------------------|--------------------------------------
`uuid`| The report's uuid.
`site`| The specified site's uuid.