<!-- pre-align:aligned sig=df943cdccd6e -->

<a id="common-launching-developers-guide"></a>
## Common > Launching > Developer's Guide { #common-launching-developers-guide }

ConsoleでLaunchingサービスを有効化した後、モバイルアプリに必要なLaunching情報を設定した場合、次のようにデータを照会できます。

<a id="launching"></a>
## Launching データ照会 { #launching }

Consoleで設定したLaunching情報を照会する方法です。

[URL]

```http
GET https://api-lnc.cloud.toast.com/launching/v2/application/{appKey}/launching  
Content-Type: application/json
```

[URLパラメータ]

| 名前 | データ型 | 説明 |
| ------ | ------ | -------------------- |
| appkey | String | ユーザーLaunching AppKey |

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

> [参考]  
> リクエスト結果はJSON文字列です。アプリケーションでは、この文字列をパースして使用します。  

<a id="section-1"></a>
## エラーコード { #section-1 }

エラーコードはHTTP Response Statusの結果コード値を意味します。

[表1 エラーコード]

| Result Code | 説明                                                |
| ----------- | ------------------------------------------------- |
| 200         | OK : リクエスト成功                                      |
| 400         | Bad Request : リクエストが正しくない場合                          |
| 401         | Unauthorized : 無効なApp Keyの場合                     |
| 404         | Not Found : リクエストしたリソースが見つからない場合                   |
| 500         | Internal Server Error : サーバー内部エラーのため、管理者にお問い合わせください。 |
