---
wts:
    title: '13 - Azure 키 자격 증명 모음(Key vault) 구현'
    module: '모듈 03 - 보안, 개인정보보호, 규정준수, 신뢰'
---

# 13 - Azure 키 자격 증명 모음(Key vault) 구현

이 연습에서는 키 자격 증명 모음(Key vault)을 생성 한 다음 해당 키 자격 증명 모음 내에 비밀번호를 생성하여 응용프로그램에서 함께 사용할 수 있도록 안전하게 저장된 중앙 관리 비밀번호를 제공합니다.

실습 시간: 10 분

# 실습 1: Azure 키 자격 증명 만들기

이 실습에서는 Azure 키 자격 증명을 생성합니다.

1. <a href="https://portal.azure.com" target="_blank"><span style="color: #0066cc;" color="#0066cc">Azure Portal</span></a>에 로그인 합니다.

2. 검색창에 **키 자격 증명 모음**을 검색한 후 **+추가**를 클릭합니다. 

3. 키 자격 증명 모음 만들기 블레이드의 **기본** 탭에서 다음을 이용하여 정보를 입력합니다.

    | 설정 | 값 | 
    | --- | --- |
    | 구독 | **실습에 이용할 구독**|
	| 리소스 그룹 | **myRGKV** (새로 만들기) |
    | 주요 자격 증명 모음 이름 | **keyvaulttestxxx** (유니크 해야 함) |
    | 지역 | **아시아 남동부** |
    | 가격 책정 계층 | **표준** |
    | | |

4. **검토 + 만들기**를 클릭하여 유효성 검사를 완료한 후 **만들기** 버튼을 클릭합니다.

5. 새로운 키 자격 증명 모음의 배포가 완료되면 **리소스로 이동** 버튼을 클릭합니다.

6. 키 자격 증명 모음의 **개요** 블레이드에서 **DNS 이름**을 메모합니다. REST API를 통해 자격 증명 모음을 사용하는 응용프로그램에서는 이 URI가 필요합니다.

7. **설정** 섹션에서 **키**, **비밀**, **인증서**, **액세스 정책**, **방화벽 및 가상 네트워크**를 검토합니다.

    **메모**: 생성한 키 자격 증명 모음에서 작업은 오직 이 Azure 계정에서만 수행 할 권한이 있습니다. **설정**과 **액세스 정책** 섹션에서 원하는 경우 이를 수정할 수 있습니다.

# 실습 2: 키 자격 증명 모음에 비밀 추가
        
이 실습에서는 키 자격 증명 모엠이 비밀을 추가합니다.

1. **설정** 섹션에서 **비밀**을 선택하고 **+생성/가져오기**를 클릭합니다.

2. 다음을 이용하여 비밀을 구성합니다.명시되지 않은 정보는 기본 값으로 설정합니다. 비밀은 활성 및 만료 날짜를 설정할 수 있으며 비활성화 할 수도 있습니다.

    | 설정 | 값 | 
    | --- | --- |
    | 업로드 옵션 | **수동** |
    | 이름 | **ExamplePassword** |
    | 값 | **hVFkk96** |
    | | |

3. **만들기** 버튼을 클릭합니다.

4. 비밀이 성공적으로 생성되면 **ExamplePassword**를 클릭하고 상태가 **사용**인지 확인합니다.

5. 현재 버전을 클릭하고 **비밀 식별자**를 확인합니다. 이것은 응용프로그램에서 사용할 수있는 URL 값입니다. 중앙에서 관리되고 안전하게 저장된 암호를 제공합니다.

6. **비밀 값 표시** 버튼을 클릭하여 지정한 비밀번호가 정상적으로 표시되는지 확인합니다. 표시 될 값은 **hVFkk96** 입니다.

Azure 키 자격 증명 모음을 만든 다음 해당 키 자격 증명 모음에 비밀을 만들어 응용프로그램과 함께 사용할 수 있도록 안전하게 저장된 중앙 관리 암호를 제공했습니다.

**메모**: 추가 비용을 피하기 위해 리소스 그룹을 제거할 수 있습니다. 리소스 그룹(myRGKV)을 검색하고 리소스 그룹 블레이드에서 **Delete resource group**을 클릭한 후 삭제 창에 리소스 그룹 이름 입력란에 리소스 그룹 이름(myRGKV)을 입력합니다. 리소스 그룹 이름을 정확히 입력하면 하단에 **삭제** 버튼이 활성화 되며 삭제 버튼을 클릭하여 생성한 리소스들을 삭제합니다. **알람**에서 모니터링 할 수 있습니다.
