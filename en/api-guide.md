<!-- pre-align:aligned sig=8c4ed6dd268d -->

<a id="game-launching-api-guide"></a>
## Game > Launching > API Guide { #game-launching-api-guide }

<a id="launching-api-common-information"></a>
## Launching API Common Information { #launching-api-common-information }

<a id="api-endpoint"></a>
### API Endpoint { #api-endpoint }

| Region | Endpoint                                  |
|--------|-------------------------------------------|
| Global | https://launching.api.nhncloudservice.com |

<a id="authentication-and-authorization"></a>
### Authentication and Authorization { #authentication-and-authorization }

Appkey is required to use the Launching API. The Appkey is included in the request URL to identify and specify a particular resource when making API calls.

For more information on checking and using Appkeys, please refer to the [Appkey](/nhncloud/en/public-api/appkey).

<a id="query-launching-data"></a>
## Query Launching Data { #query-launching-data }

```
GET /launching/v3.0/appkeys/{appKey}/configurations
```

<a id="request"></a>
### Request { #request }

| Name   | Type  | Format | Required | Description                                                                                     |
|--------|-------|--------|----------|-------------------------------------------------------------------------------------------------|
| appKey | URL   | String | O        | Launching Service Appkey                                                                        |
| subKey | Query | String | X        | Key used to retrieve only specific data from Launching information</br>Starts with "launching." |

<a id="response"></a>
### Response { #response }

| Name      | Type | Format | Description           |
|-----------|------|--------|-----------------------|
| launching | Body | Object | Launching information |

<a id="examples"></a>
### Examples { #examples }

<details><summary>Query All</summary>

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

</details>

<details><summary>Query Using subKey</summary>

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

</details>
