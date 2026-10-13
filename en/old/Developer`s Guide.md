<!-- pre-align:aligned sig=df943cdccd6e -->

<a id="common-launching-developers-guide"></a>
## Common > Launching > Developer's Guide { #common-launching-developers-guide }

After enabling the Launching service in the console and configuring the Launching information required for your mobile app, you can retrieve the data as follows.

<a id="launching"></a>
## Retrieve Launching Data { #launching }

You can query the Launching information configured through Console.

[URL]

```http
GET https://api-lnc.cloud.toast.com/launching/v2/application/{appKey}/launching  
Content-Type: application/json
```

[URL Parameters]

| Name     | Data type    | Description                   |
| ------ | ------ | -------------------- |
| appkey | String | User Launching AppKey |

[Example Request]

```http
GET https://api-lnc.cloud.toast.com/launching/v2/application/7bfa6111b2141c13a813b90e4b314ac7308ea00dc2584611c089518f2da5cb6a/launching
Content-Type: application/json
```

[Example Response]

```http
HTTP/1.1 200 OK
Content-Type: application/json;charset=UTF-8

{
    "header":{
        "resultCode":0,
        "resultMessage":"ok",
        "isSuccessful":true,
        "serviceCode":900021
    },
    "launching":{
        "state":"",
        "server":{
            "ip":"",
            "cds":""
        },
        "client":{
            "currentVersion":"",
            "downloadUrl":"",
            "noticeUrl":"",
            "privacyUrl":"",
            "termsUrl":"",
            "eventUrl":"",
            "bannerUrl":""
        },
        "maintenance":{
            "message":{
                "ko":"",
                "en":"",
                "jp":""
            }
        }
    }
}
```

> [Note]
> The request result is a JSON string. You can parse the string in your application to use it.

<a id="section-1"></a>
## Error Code { #section-1 }

Error codes indicate the HTTP Response Status result code values.

[Table 1] Error Codes

| Result Code | Description                                                |
| ----------- | ------------------------------------------------- |
| 200         | OK : Request success                                  |
| 400         | Bad Request : When the request is invalid                          |
| 401         | Unauthorized : Invalid App Key                    |
| 404         | Not Found: Requested resource not found                   |
| 500         | Internal Server Error : Errors caused by a server internal error. Contact the administrator. |
