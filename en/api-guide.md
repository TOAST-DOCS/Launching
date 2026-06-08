## Game > Launching > API Guide

## Launching API Common Information

### API Endpoint

| Region | Endpoint                                  |
|--------|-------------------------------------------|
| Global | https://launching.api.nhncloudservice.com |

### Authentication and Authorization

Appkey is required to use the Launching API. The Appkey is included in the request URL to identify and specify a particular resource when making API calls.

For more information on checking and using Appkeys, please refer to the [Appkey](/nhncloud/en/public-api/appkey).

## Query Launching Data

```
GET /launching/v3.0/appkeys/{appKey}/configurations
```

### Request

| Name   | Type  | Format | Required | Description                                                                                     |
|--------|-------|--------|----------|-------------------------------------------------------------------------------------------------|
| appKey | URL   | String | O        | Launching Service Appkey                                                                        |
| subKey | Query | String | X        | Key used to retrieve only specific data from Launching information</br>Starts with "launching." |

### Response

| Name      | Type | Format | Description           |
|-----------|------|--------|-----------------------|
| launching | Body | Object | Launching information |

### Examples

<details><summary>Query All</summary>
<p>

[Request]

```
GET /launching/v3.0/appkeys/EyJ6IEGKv1pDVCHc/configurations
```

[Response]

```json
{
    "header": {
        "isSuccessful": true,
        "resultCode": 0,
        "resultMessage": "Success"
    },
    "launching": {
        "server": {
            "cds": "",
            "ip": ""
        },
        "client": {
            "privacyUrl": "",
            "termsUrl": "",
            "eventUrl": "",
            "bannerUrl": "",
            "downloadUrl": "",
            "noticeUrl": "",
            "currentVersion": ""
        },
        "state": "",
        "maintenance": {
            "message": {
                "ko": "",
                "jp": "",
                "en": ""
            }
        }
    }
}
```

</p>
</details>

<details><summary>Query Using subKey</summary>
<p>

[Request]

```
GET /launching/v3.0/appkeys/EyJ6IEGKv1pDVCHc/configurations?subKey=launching.server
```

[Response]

```json
{
    "header": {
        "isSuccessful": true,
        "resultCode": 0,
        "resultMessage": "Success"
    },
    "launching": {
        "cds": "",
        "ip": ""
    }
}
```

</p>
</details>
