## Game > Launching > APIガイド

## Launching API共通情報

### APIエンドポイント

| リージョン  | エンドポイント                                   |
|--------|-------------------------------------------|
| Global | https://launching.api.nhncloudservice.com |

### 認証及び権限

Launching APIを使用するには、Appkeyが必要です。Appkeyは、API呼び出し時にリクエストURLに含めて特定のリソースを指定し、識別するために使用されます。

Appkeyの確認及び使用に関する詳細は、[Appkey](/nhncloud/ja/public-api/appkey)を参照してください。

## Launchingデータ照会

```
GET /launching/v3.0/appkeys/{appKey}/configurations
```

### リクエスト

| 名前     | 種類    | 形式     | 必須 | 説明                                                      |
|--------|-------|--------|----|---------------------------------------------------------|
| appKey | URL   | String | O  | LaunchingサービスのAppkey                                    |
| subKey | Query | String | X  | Launching情報から一部のデータのみを取得するために使用するキー</br>"launching."で開始 |

### レスポンス

| 名前        | 種類   | 形式     | 説明          |
|-----------|------|--------|-------------|
| launching | Body | Object | Launching情報 |

### 例

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
