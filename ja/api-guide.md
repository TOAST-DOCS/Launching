<!-- pre-align:aligned sig=8c4ed6dd268d -->

<a id="game-launching-api-guide"></a>
## Game > Launching > APIガイド { #game-launching-api-guide }

<a id="launching-api-common-information"></a>
## Launching API共通情報 { #launching-api-common-information }

<a id="api-endpoint"></a>
### APIエンドポイント { #api-endpoint }

| リージョン  | エンドポイント                                   |
|--------|-------------------------------------------|
| Global | https://launching.api.nhncloudservice.com |

<a id="authentication-and-authorization"></a>
### 認証及び権限 { #authentication-and-authorization }

Launching APIを使用するには、Appkeyが必要です。Appkeyは、API呼び出し時にリクエストURLに含めて特定のリソースを指定し、識別するために使用されます。

Appkeyの確認及び使用に関する詳細は、[Appkey](/nhncloud/ja/public-api/appkey)を参照してください。

<a id="query-launching-data"></a>
## Launchingデータ照会 { #query-launching-data }

```
GET /launching/v3.0/appkeys/{appKey}/configurations
```

<a id="request"></a>
### リクエスト { #request }

| 名前     | 種類    | 形式     | 必須 | 説明                                                      |
|--------|-------|--------|----|---------------------------------------------------------|
| appKey | URL   | String | O  | LaunchingサービスのAppkey                                    |
| subKey | Query | String | X  | Launching情報から一部のデータのみを取得するために使用するキー</br>"launching."で開始 |

<a id="response"></a>
### レスポンス { #response }

| 名前        | 種類   | 形式     | 説明          |
|-----------|------|--------|-------------|
| launching | Body | Object | Launching情報 |

<a id="examples"></a>
### 例 { #examples }

<details><summary>全体照会</summary>

[リクエスト]

```
GET /launching/v3.0/appkeys/EyJ6IEGKv1pDVCHc/configurations
```

[レスポンス]

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

<details><summary>subKeyを使用した照会</summary>

[リクエスト]

```
GET /launching/v3.0/appkeys/EyJ6IEGKv1pDVCHc/configurations?subKey=launching.server
```

[レスポンス]

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
