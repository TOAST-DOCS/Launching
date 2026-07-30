<!-- pre-align:aligned sig=8c4ed6dd268d -->

<a id="game-launching-api-guide"></a>
## Game > Launching > API 가이드 { #game-launching-api-guide }

<a id="launching-api-common-information"></a>
## Launching API 공통 정보 { #launching-api-common-information }

<a id="api-endpoint"></a>
### API 엔드포인트 { #api-endpoint }

| 리전     | 엔드포인트                                     |
|--------|-------------------------------------------|
| Global | https://launching.api.nhncloudservice.com |

<a id="authentication-and-authorization"></a>
### 인증 및 권한 { #authentication-and-authorization }

Launching API를 사용하려면 Appkey가 필요합니다. Appkey는 API 호출 시 요청 URL에 포함하여 특정 리소스를 가리키고 식별하는 데 사용됩니다.

Appkey 확인 및 사용에 대한 자세한 내용은 [Appkey](/nhncloud/ko/public-api/appkey)를 참고하세요.

<a id="query-launching-data"></a>
## Launching 데이터 조회 { #query-launching-data }

```
GET /launching/v3.0/appkeys/{appKey}/configurations
```

<a id="request"></a>
### 요청 { #request }

| 이름     | 종류    | 형식     | 필수 | 설명                                                          |
|--------|-------|--------|----|-------------------------------------------------------------|
| appKey | URL   | String | O  | Launching 서비스 Appkey                                        |
| subKey | Query | String | X  | Launching 정보에서 일부 데이터만 가져오기 위해 사용하는 키</br>"launching."으로 시작 |

<a id="response"></a>
### 응답 { #response }

| 이름        | 종류   | 형식     | 설명           |
|-----------|------|--------|--------------|
| launching | Body | Object | Launching 정보 |

<a id="examples"></a>
### 예시 { #examples }

<details><summary>전체 조회</summary>

[요청]

```
GET /launching/v3.0/appkeys/EyJ6IEGKv1pDVCHc/configurations
```

[응답]

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

<details><summary>subKey를 사용한 조회</summary>

[요청]

```
GET /launching/v3.0/appkeys/EyJ6IEGKv1pDVCHc/configurations?subKey=launching.server
```

[응답]

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
