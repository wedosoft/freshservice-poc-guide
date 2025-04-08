# Freshservice 셀프 POC 가이드

## 시작하기 전에

이 가이드는 고객님께서 Freshservice의 주요 기능을 스스로 평가할 수 있도록 구성되었습니다. POC 평가는 크게 두 영역으로 진행됩니다:
1. ITSM 워크플로우 구현
2. IT자산관리 구현

## Freshservice 계정 정보

이 POC 가이드는 귀사의 Freshservice 계정에 맞게 설정되었습니다:
- 계정 URL: <a href="https://gsholdings.freshservice.com/" target="_blank">https://gsholdings.freshservice.com/</a>

## 파트 1: ITSM 워크플로우 구현

### 1.1 역할 및 부서 설정 (예상 소요 시간: 15분)

▶️ <a href="https://gsholdings.freshservice.com/admin/groups" target="_blank">역할/부서 설정 화면으로 이동</a>

- 다음 부서(그룹) 생성하기:
  - 현업부서
  - IT부서
  - IT운영팀

- 다음 역할 설정하기:
  - 현업 담당자
  - 현업 리더 (승인자)
  - IT 담당자
  - IT 운영팀

✅ **완료 확인**: 모든 부서와 역할이 생성되고, 테스트 사용자가 각 역할에 할당되었습니다.

### 1.2 워크플로우 설정 (예상 소요 시간: 30분)

▶️ <a href="https://gsholdings.freshservice.com/admin/workflow_automators" target="_blank">워크플로우 설정 화면으로 이동</a>

- 다음 단계로 이루어진 워크플로우 생성:
  1. 현업 담당자 요청 생성
  2. 현업 리더 승인 단계
  3. IT 담당자 확인 및 할당
  4. IT 운영팀 처리
  5. 처리 완료 알림
  6. 만족도 측정

▶️ <a href="https://gsholdings.freshservice.com/admin/sla_policies" target="_blank">SLA 정책 설정 화면으로 이동</a>

- 요청 유형별 SLA 정책 설정:
  - 일반 요청: 24시간
  - 긴급 요청: 4시간

✅ **완료 확인**: 전체 워크플로우가 설정되고, 테스트 요청을 통해 각 단계가 정상 작동하는지 확인했습니다.

### 1.3 테스트 시나리오 실행 (예상 소요 시간: 15분)

▶️ <a href="https://gsholdings.freshservice.com/a/tickets/new" target="_blank">새 티켓 생성 화면으로 이동</a>

- 현업 담당자로 새 요청 생성
- 승인자로 로그인하여 승인 처리
- IT 담당자로 로그인하여 티켓 할당
- IT 운영팀으로 로그인하여 티켓 처리
- 요청자로 돌아가 만족도 평가 입력

✅ **완료 확인**: 전체 워크플로우가 오류 없이 실행되고, 각 단계별 알림이 정상 작동합니다.

## 파트 2: IT자산관리 구현

### 2.1 자산 유형 설정 (예상 소요 시간: 20분)

▶️ <a href="https://gsholdings.freshservice.com/admin/asset_types" target="_blank">자산 유형 설정 화면으로 이동</a>

- 다음 자산 유형 설정:
  - PC/노트북
  - 모바일/태블릿
  - 주변기기

- 각 자산 유형에 필요한 사용자 정의 필드 추가:
  - 구매일자
  - 보증기간
  - 담당부서
  - 자산상태

✅ **완료 확인**: 모든 자산 유형과 필드가 설정되었습니다.

### 2.2 샘플 자산 데이터 가져오기 (예상 소요 시간: 15분)

▶️ <a href="https://gsholdings.freshservice.com/admin/import_assets" target="_blank">자산 가져오기 화면으로 이동</a>

- [여기를 클릭하여 샘플 CSV 파일 다운로드](https://raw.githubusercontent.com/wedosoft/freshservice-poc-guide/main/self-service-poc/sample-data/asset-sample.csv)
- CSV 파일의 필드와 시스템 필드 매핑
- 데이터 가져오기 실행

✅ **완료 확인**: 모든 샘플 자산이 오류 없이 시스템에 등록되었습니다.

### 2.3 자산 라이프사이클 테스트 (예상 소요 시간: 30분)

▶️ <a href="https://gsholdings.freshservice.com/cmdb/items" target="_blank">자산 목록 화면으로 이동</a>

다음 시나리오를 테스트해보세요:

- 신규 직원 입사 → 자산 할당
  - 새 직원 생성
  - 미할당 자산을 직원에게 할당
  - 자산 상태 변경

- 자산 이관
  - 한 사용자에서 다른 사용자로 자산 이관
  - 이관 내역 기록

- 자산 반납 및 폐기
  - 사용자로부터 자산 회수
  - 자산 상태를 '폐기 대기'로 변경
  - 폐기 프로세스 실행

✅ **완료 확인**: 모든 라이프사이클 단계가 정상적으로 처리되고 기록됩니다.

### 2.4 자산 보고서 생성 (예상 소요 시간: 15분)

▶️ <a href="https://gsholdings.freshservice.com/reports" target="_blank">보고서 화면으로 이동</a>

- 다음 보고서 생성:
  - 부서별 자산 현황
  - 자산 유형별 분포
  - 만료 예정 보증 목록

✅ **완료 확인**: 모든 보고서가 정확한 데이터로 생성되고 적절히 시각화됩니다.

## 파트 3: 플랜 비교 평가

Freshservice의 Pro 플랜과 Enterprise 플랜 비교 정보:

### 3.1 Pro vs Enterprise 기능 차이

| 기능 | Pro 플랜 | Enterprise 플랜 |
|------|---------|---------------|
| ITSM 워크플로우 | 기본 승인 과정 | 다단계 승인, 조건부 분기 |
| 자동화 트랜잭션 | 월 2,000건 | 월 20,000건 |
| 자산 관리 | 기본 기능 | 고급 자산 관계, 소프트웨어 라이선스 관리 |
| 보안 기능 | 기본 보안 | IP 제한, SSO, 고급 감사 |
| 샌드박스 환경 | 미지원 | 지원 |

## POC 완료

POC를 완료하신 후, 담당자에게 연락하여 다음 단계를 논의해 주시기 바랍니다.

---

© 2025 Freshservice POC 가이드 | 문의: support@wedosoft.net 