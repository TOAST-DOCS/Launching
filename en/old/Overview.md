## Common > Launching > Overview

모바일 앱을 실행하기 위해서는 서버의 정보, 공지사항 URL, 다운로드 URL등 다양한 정보가 필요합니다. 하지만 모바일 앱에 필요한 정보가 변경 된다면 새로운 모바일 앱 배포가 필요 합니다.  Launching은 모바일 앱 실행 시 초기 실행에 필요한 다양한 정보를 실시간 반영하는 기능을 제공하여 앱 배포 없이 운영하도록 지원합니다.

## 주요 기능

다음과 같은 기능을 제공합니다.

* **동적으로 변경 가능한 서비스 정보들을 서버 및 모바일 앱 패치 없이 변경 가능**  
서비스 모바일 앱의 초기 구동에 필요한 서버 정보, CDN 정보, 점검 상태 등의 변경 가능한 정보들을 Launching에서 관리 한다면, 해당 정보들이 변경 될 때 서버나 모바일 앱의 패치 작업이 필요 없습니다.

* **새로운 모바일 앱 버전이 출시되면, 이전 버전에 대한 관리가 가능**  
서비스 모바일 앱의 새로운 버전이 출시되면 이전 버전에 대한 업그레이드 알림, 강제 업데이트 수행 및 접속 불가 등의 동작을 설정할 수 있습니다.

* **특정 단말기 또는 OS 버전에 따른 서비스 접근 제한 가능**  
특정 단말기 또는 iOS/Android 버전 업그레이드에 따른 서비스 장애 발생시, 서버 및 모바일 앱 패치 없이 임의의 단말기에 대해 서비스 제한을 할 수 있습니다.

* **사용자가 설정한 시간 동안 모바일 앱에 메시지를 공지 가능**  
사용자가 설정한 임의의 시간 동안에만 점검 일정 및 이벤트 등의 공지 메시지를 제공 할 수 있으며, 서비스 점검 동안 서비스 제공을 중단하고 점검 메시지를 공지 할 수 있습니다.

## 서비스 용어

Launching 서비스에서는 다음 용어를 사용 합니다.

| 용어  | 설명                                                                    |
| --- | --------------------------------------------------------------------- |
| 런칭  | 서비스 단말기에서 앱구동에 필요한 초기 정보                                              |
| 폴더  | 런칭 정보는 트리(tree) 구조로 구성되는데, 이때 중간 노드들을 폴더로 지칭 폴더는 또 다른 폴더 및 키를 가질 수 있음 |
| KEY | 트리 구조의 최하단 단말노드로서 값(value)을 가짐                                        |

[표 1 Launching 용어]
