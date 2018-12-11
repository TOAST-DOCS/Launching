## Game > Launching > Error Code
## 에러 코드

에러 코드는 Response body의 header에 있는 resultCode 및 resultMessage의 의미를 설명합니다.

[표1 에러 코드]

| Result Code | Result Message | 설명 |
| --- | --- | --- |
| 0 | Success | 요청 성공 |
| 10001 | CONFIGURATION_GET_FAILED | Launching 정보 조회 실패 |
| 90020 | APPKEY_VERIFICATION_FAILED | 등록되지 않은 AppKey |
| 90404 | CONFIGURATION_PATH_NOT_FOUND | 주어진 서브 키에 대응되는 Launching 데이터를 찾을 수 없음 |
| -1 | FAIL | 미확인 에러 |

> [참고]
> 그 외 일반적인 에러 코드에 대한 추가 정보는 다음 링크에서 확인하기 바랍니다.
> http://www.iana.org/assignments/http-status-codes/http-status-codes.xhtml