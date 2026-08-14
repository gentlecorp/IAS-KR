# 필독:

## 이 프로젝트의 원본은 지원 중단된지 오래이며, 단순 번역판입니다.

------------------------------------------------------------------------

## IDM Activation Script

[Internet Download Manager](https://www.internetdownloadmanager.com/)의 체험 일수를 바꾸거나 활성화 할 수 있는 오픈소스 툴 입니다.

## 기능

- 레지스트리 키 잠금 방식을 이용한 IDM 체험판 동결 및 활성화
- IDM 업데이트를 설치한 후에도 활성화 및 체험판 상태 유지
- IDM 체험판 초기화
- 완전한 오픈 소스
- 투명한 배치 스크립트를 기반으로 제작

## IAS 최신 릴리스

최신 릴리스 - v1.2 (2024년 2월 12일)  
[GitHub](https://github.com/WindowsAddict/IDM-Activation-Script) - [BitBucket](https://bitbucket.org/WindowsAddict/idm-activation-script/)

## 다운로드 / 사용 방법

- 먼저 [Internet Download Manager](https://www.internetdownloadmanager.com/)를 새로 설치합니다. 이전에 사용하던 크랙/패치가 있다면 모두 제거하거나 삭제했는지 확인하세요.
- 그런 다음 아래 방법에 따라 활성화합니다.

## 참고

- 📌 현재 스크립트의 **활성화 옵션은 작동하지 않습니다.** 대신 **Freeze trial(체험판 동결)** 옵션을 사용하여 30일 체험 기간을 영구적으로 잠글 수 있습니다.

## 방법 1 - PowerShell

**(권장)**

- Windows 시작 메뉴를 마우스 오른쪽 버튼으로 클릭하고 **PowerShell** 또는 **Terminal**을 선택합니다. (**CMD가 아님**)
- 아래 코드를 복사하여 붙여넣고 Enter 키를 누릅니다.

  `irm https://massgrave.dev/ias | iex`

- 활성화 옵션이 표시되면 화면의 안내에 따라 진행합니다.
- 이것으로 완료됩니다.

## 방법 2 - 기존 방식

- [GitHub](https://github.com/WindowsAddict/IDM-Activation-Script/archive/refs/heads/main.zip) 또는 [Bitbucket](https://bitbucket.org/WindowsAddict/idm-activation-script/get/main.zip)에서 파일을 다운로드합니다.
- 다운로드한 ZIP 파일을 마우스 오른쪽 버튼으로 클릭하고 압축을 풉니다.
- 압축을 푼 폴더에서 `IAS.cmd`라는 파일을 실행합니다.
- 활성화 옵션이 표시되면 화면의 안내에 따라 진행합니다.
- 이것으로 완료됩니다.
- 혹은 이 저장소의 릴리즈에서도 다운로드 할 수 있습니다.

## 정보

### 체험판 동결 (Freeze Trial)

- IDM은 30일의 체험 기간을 제공합니다. 이 스크립트의 이 옵션을 사용하면 이 체험 기간을 **영구적으로 잠글 수 있어**, 이후 체험판을 다시 초기화할 필요가 없으며 체험 기간도 만료되지 않습니다.
- 이 옵션을 적용할 때 인터넷 연결이 필요합니다.
- IDM 업데이트는 다시 동결할 필요 없이 바로 설치할 수 있습니다.

### 활성화 (Activation)

**(\* 현재 작동하지 않음)**

- 이 스크립트는 레지스트리 잠금 방식을 사용하여 Internet Download Manager를 활성화합니다.
- 활성화할 때 인터넷 연결이 필요합니다.
- 활성화 후에도 IDM 업데이트를 다시 활성화할 필요 없이 바로 설치할 수 있습니다.
- 활성화 후 어떤 경우에 IDM이 다시 활성화 요구 화면을 표시한다면, **Reset 옵션을 사용하지 말고 Activation 옵션을 다시 실행**하면 됩니다.

### IDM 활성화 / 체험판 초기화

- Internet Download Manager는 30일의 체험 기간을 제공합니다. 이 스크립트를 사용하면 원하는 시점에 활성화/체험판 기간을 초기화할 수 있습니다.
- IDM에서 가짜 시리얼 키를 감지하거나 이와 유사한 오류가 발생한 경우에도 상태를 복구하는 데 사용할 수 있습니다.

## 운영체제 요구 사항

- Windows 7/8/8.1/10/11 및 해당 Server 버전
- PowerShell 방식은 Windows 8 이상 필요

## 고급 정보

- 무인 모드로 활성화하려면 스크립트에 `/act` 매개변수를 사용합니다.
- 무인 모드로 체험판을 동결하려면 `/frz` 매개변수를 사용합니다.
- 무인 모드로 초기화하려면 `/res` 매개변수를 사용합니다.

## 작동 원리
- IDM은 체험판 및 활성화와 관련된 데이터를 여러 레지스트리 키에 저장합니다. 이러한 키 중 일부는 변경을 방지하기 위해 잠겨 있으며, 데이터는 가짜 시리얼 키 문제와 남은 체험 기간을 추적할 수 있는 방식으로 저장됩니다.
- 활성화를 위해 이 스크립트는 IDM에서 몇 차례 다운로드를 실행하여 해당 레지스트리 키를 생성한 다음, 관련 레지스트리 키를 찾아 잠급니다. 이를 통해 IDM이 해당 키를 수정하거나 확인하지 못하게 하여 **가짜 시리얼 키로 활성화되었다는 경고가 표시되지 않도록 하는 방식**입니다.

## 문제 해결

- 브라우저 통합 문제 해결: [Chrome](https://www.internetdownloadmanager.com/register/new_faq/bi9.html) - [Firefox](https://www.internetdownloadmanager.com/register/new_faq/bi4.html)
- 스크린샷과 함께 [Github](https://github.com/WindowsAddict/IDM-Activation-Script)에 문제를 제보하세요.

## 크레딧

| 기여자 | 내용 |
|---|---|
| Dukun Cabul | IDM 체험판 초기화 및 활성화 로직을 처음 연구한 사람으로, 이러한 방법을 위한 AutoIt 도구인 [IDM-AIO_2020_Final](https://nsaneforums.com/topic/371047-discussion-internet-download-manager-fixes/page/8/#comment-1632062)을 제작 |
| AveYo aka BAU | [reg_own lean and mean snippet](https://pastebin.com/XTPt0JSC) 제공 |
| [abbodi1406](https://github.com/abbodi1406) | 코드 작성 지원 |
| WindowsAddict | IAS 제작자 |
