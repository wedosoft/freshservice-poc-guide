---
layout: default
---
[홈으로 돌아가기](../) | [자산관리 워크플로우](../asset-management/) | [ITSM 워크플로우](../itsm-workflow/) | [라이선스 권장사항](../license-recommendations/) | [PoC 전략](../strategy/)

# 셀프 POC 가이드

> **실습 링크**: <a href="https://gsholdings.freshservice.com/" target="_blank">Freshservice 인스턴스 바로가기</a>

## 문서 안내

Freshservice POC 가이드는 다음과 같이 구성되어 있습니다:

| 문서명 | 목적 | 주요 내용 |
|-------|------|----------|
| **셀프 POC 가이드** (현재 문서) | 전체 POC 프로세스 개요 안내 | POC 범위, 주요 단계, 기본 설정 방법 |
| [ITSM 워크플로우](../itsm-workflow/) | ITSM 워크플로우 세부 구현 방법 | 요청-승인-할당-처리-만족도 측정 워크플로우 상세 구성 |
| [자산관리 워크플로우](../asset-management/) | 자산관리 세부 구현 방법 | 자산 등록, 할당, 회수, 폐기 프로세스 상세 구성 |
| [라이선스 권장사항](../license-recommendations/) | 라이선스 분석 정보 | Pro와 Enterprise 플랜 비교, TCO 분석 |
| [PoC 전략](../strategy/) | 전체 PoC 진행 전략 | 준비 단계, 실행 단계, 평가 단계, 성공 기준 |

**기본 접근 방법:**
1. 현재 문서(셀프 POC 가이드)에서 전체 흐름 확인
2. 각 워크플로우 문서에서 상세 구현 방법 참조
3. 라이선스 권장사항 문서에서 플랜 비교 정보 확인
4. PoC 전략 문서에서 전체 PoC 프로세스 이해

## 개요

이 가이드는 최소한의 외부 지원으로 Freshservice의 핵심 기능을 직접 테스트하고 평가할 수 있도록 설계되었습니다. 2주 내에 Freshservice의 핵심 기능들을 검증하고 비즈니스 요구사항에 대한 적합성을 직접 확인하세요.

PoC는 다음 핵심 영역에 중점을 둡니다:
- ITSM 워크플로우 구현 및 테스트
- IT 자산관리 구현 및 테스트
- Pro와 Enterprise 플랜 비교 평가

## 문서 구조 안내

본 PoC 가이드는 다음과 같은 문서 구조로 구성되어 있습니다:

| 문서 | 역할 | 사용 시점 |
|------|------|----------|
| **셀프 PoC 가이드** (현재 문서) | • 전체 PoC 진행 과정의 개요<br>• 주요 기능 검증을 위한 기본 실행 단계 | PoC 시작 시 첫 번째로 참조 |
| [**ITSM 워크플로우**](../itsm-workflow/) | • 티켓 처리 프로세스 상세 구현<br>• 승인 흐름, SLA, 자동화 규칙 심층 가이드 | ITSM 워크플로우 심화 구현 시 |
| [**자산관리 워크플로우**](../asset-management/) | • 자산 등록 및 라이프사이클 관리 상세 구현<br>• 자산 데이터 구조, 관계 설정 심층 가이드 | 자산관리 심화 구현 시 |
| [**라이선스 권장사항**](../license-recommendations/) | • Pro와 Enterprise 플랜 비교 분석<br>• 비용 대비 효과 및 ROI 계산 | 라이선스 결정 시 |
| [**PoC 전략**](../strategy/) | • PoC 준비 및 계획 수립<br>• 성공적인 PoC 수행을 위한 전략적 조언 | PoC 계획 수립 단계 |

**사용 방법**:
1. 현재 문서(셀프 PoC 가이드)에서 전체 PoC 흐름과 기본 실행 단계를 파악합니다.
2. 각 영역별 심층 구현이 필요한 경우, 해당 특화 문서를 참조하세요.
3. 모든 문서는 상단의 네비게이션 링크를 통해 쉽게 이동할 수 있습니다.

---

## 파트 1: ITSM 워크플로우 구현 (예상 소요 시간: 60분)

### 사용자 관리 구성요소 이해하기

ITSM 워크플로우를 설정하기 전에 Freshservice의 사용자 관리 구성요소를 이해하는 것이 중요합니다:

| 구성요소 | 설명 | 사용 목적 |
|---------|------|----------|
| **부서(Department)** | 조직 내 공식적인 부서 단위 | • 엔드 유저(요청자/직원) 그룹핑<br>• 조직 구조 반영<br>• 티켓 분류 및 라우팅 |
| **요청자(Requester)** | 서비스를 요청하는 엔드 유저 | • 티켓 생성<br>• 서비스 요청<br>• 상태 확인 |
| **요청자 그룹(Requester Group)** | 특정 목적을 위해 요청자를 묶은 그룹 | • 특정 서비스 접근 권한 관리<br>• 공통 요청 처리<br>• 알림 관리 |
| **에이전트(Agent)** | 서비스를 제공하는 IT 담당자 | • 티켓 처리<br>• 요청 관리<br>• 해결책 제공 |
| **그룹(Group)** | 기능적 목적으로 에이전트를 묶은 단위 | • 업무 영역별 티켓 할당<br>• 전문 분야별 관리<br>• 책임 영역 설정 |

**주요 특성**:
- Freshservice에서 **부서**는 엔드 유저를 관리하는 핵심 그룹핑 단위입니다.
- 별도의 하위 부서 개념은 제공되지 않으나, 부서를 다양한 기준으로 정의하여 유연하게 활용할 수 있습니다.
- **요청자 그룹**은 부서와는 별개로 특정 목적(예: 프로젝트, 서비스 접근)에 따라 사용자를 묶는 데 활용됩니다.
- **그룹**은 주로 에이전트를 전문 분야나 책임 영역에 따라 분류할 때 사용됩니다.

### 1.1 역할 및 부서 설정 (15분)

> **실습 링크**: <a href="https://gsholdings.freshservice.com/ws/2/admin/home" target="_blank">사용자 관리 > 역할/부서 설정 화면</a>

다음 부서(그룹)와 역할을 생성합니다:

| 구분 | 설정 항목 | 주요 권한/목적 |
|------|---------|--------------|
| 부서 | • 현업부서<br>• IT부서<br>• IT운영팀 | • 요청자 그룹 (현업부서)<br>• 관리자 그룹 (IT부서)<br>• 처리자 그룹 (IT운영팀) |
| 역할 | • 현업 담당자<br>• 현업 리더<br>• IT 담당자<br>• IT 운영팀 | • 요청 생성 (현업)<br>• 승인 권한 (리더)<br>• 할당 권한 (IT)<br>• 처리 권한 (운영) |

**설정 경로**: 관리자 > 그룹(부서용) 및 관리자 > 역할(권한용)

**완료 확인**: 각 역할별 테스트 계정 1개 이상 생성, 부서 소속 설정 완료

### 1.2 워크플로우 설정 (30분)

> **실습 링크**: <a href="https://gsholdings.freshservice.com/ws/2/admin/automators" target="_blank">워크플로우 자동화 설정</a>

다음 단계로 이루어진 워크플로우를 생성합니다:

| 단계 | 설정 내용 |
|------|----------|
| 1. 요청 생성 | 티켓 생성 시 현업 리더에게 승인 요청 자동 발송 |
| 2. 승인 처리 | 승인 완료 시 IT담당자에게 티켓 자동 할당 |
| 3. 할당 처리 | IT담당자가 적합한 IT운영팀에 티켓 배정 |
| 4. 해결 처리 | 티켓 해결 시 요청자에게 완료 알림 자동 발송 |
| 5. 만족도 측정 | 해결 후 요청자에게 만족도 평가 요청 발송 |

**완료 확인**: 생성된 워크플로우 규칙이 각 단계별로 올바르게 작동하는지 테스트합니다.

### 1.3 테스트 시나리오 실행 (15분)

> **실습 링크**: <a href="https://gsholdings.freshservice.com/support/tickets/new" target="_blank">새 티켓 생성 화면</a>

전체 워크플로우를 테스트합니다:

| 단계 | 작업 내용 |
|------|----------|
| 1 | 현업 담당자로 새 요청 생성 |
| 2 | 승인자로 로그인하여 승인 처리 |
| 3 | IT 담당자로 로그인하여 티켓 할당 |
| 4 | IT 운영팀으로 로그인하여 티켓 처리 |
| 5 | 요청자로 돌아가 만족도 평가 입력 |

**완료 확인**: 전체 워크플로우가 오류 없이 실행되고, 각 단계별 알림이 정상 작동하는지 확인합니다.

---

## 파트 2: IT 자산관리 구현 (예상 소요 시간: 80분)

### 2.1 자산 유형 설정 (20분)

> **실습 링크**: <a href="https://gsholdings.freshservice.com/cmdb/ci_types" target="_blank">자산 유형 설정 화면</a>

다음 자산 유형을 설정합니다:
- PC/노트북
- 모바일/태블릿
- 주변기기

각 자산 유형에 필요한 사용자 정의 필드를 추가합니다:
- 구매일자
- 보증기간
- 담당부서
- 자산상태

**완료 확인**: 모든 자산 유형과 필드가 설정되었는지 확인합니다.

### 2.2 샘플 자산 데이터 가져오기 (15분)

> **실습 링크**: <a href="https://gsholdings.freshservice.com/cmdb/items" target="_blank">'가져오기' 자산 가져오기 화면</a>

자산 데이터 가져오기는 다음 단계로 진행합니다:

1. [자산관리 워크플로우](../asset-management/) 문서에서 제공하는 샘플 CSV 파일 참조
2. **[샘플 파일 다운로드](./sample-data/asset-sample.csv)**: 완전한 자산 데이터 CSV 파일

3. 데이터 가져오기 작업 실행:
   - CSV 파일 업로드
   - 필드 매핑 설정 (한글 칼럼명 → 영문 필드명)
   - 가져오기 실행

**완료 확인**: 모든 샘플 자산이 오류 없이 시스템에 등록되었는지 확인합니다.

### 2.3 자산 수명주기 테스트 (30분)

> **실습 링크**: <a href="https://gsholdings.freshservice.com/cmdb/items" target="_blank">자산 목록 화면</a>

다음 시나리오를 테스트합니다:

| 시나리오 | 테스트 방법 |
|---------|------------|
| 신규 입사자 자산 할당 | 새 직원 생성 → 미할당 자산 할당 → 자산 상태 변경 |
| 자산 이관 | 한 사용자에서 다른 사용자로 자산 이관 → 이관 내역 기록 |
| 자산 반납 및 폐기 | 자산 회수 → '폐기 대기'로 상태 변경 → 폐기 프로세스 실행 |

**완료 확인**: 모든 라이프사이클 단계가 정상적으로 처리되고 기록되는지 확인합니다.

### 2.4 자산 분석 보고서 생성 (15분)

> **실습 링크**: <a href="https://gsholdings.freshservice.com/analytics" target="_blank">분석 화면</a>

다음 보고서를 생성합니다:
- 부서별 자산 현황
- 자산 유형별 분포
- 만료 예정 보증 목록

**완료 확인**: 모든 보고서가 정확한 데이터로 생성되고 적절히 시각화되는지 확인합니다.

---

## 파트 3: Pro vs Enterprise 플랜 비교 (예상 소요 시간: 15분)

> **실습 링크**: <a href="https://gsholdings.myfreshworks.com/subscriptions/828075798867937047/details" target="_blank">구독 관리 화면</a>

Freshservice의 Pro 플랜과 Enterprise 플랜의 주요 차이점을 확인합니다:

| 기능 | Pro 플랜 | Enterprise 플랜 |
|------|---------|---------------|
| ITSM 워크플로우 | 기본 승인 과정 | 다단계 승인, 조건부 분기 |
| 자동화 트랜잭션 | 월 2,000건 | 월 20,000건 |
| 자산 관리 | 기본 기능 | 고급 자산 관계, 소프트웨어 라이선스 관리 |
| 보안 기능 | 기본 보안 | IP 제한, SSO, 고급 감사 |
| 샌드박스 환경 | 미지원 | 지원 |

### 확인 포인트
- 동시에 다수의 워크플로우 규칙 생성이 가능한지 확인
- 고급 자산 관계 설정 기능 확인
- 보고서 및 대시보드 커스터마이징 옵션 확인

---

## 효과적인 POC 진행 팁

1. **테스트 계획 수립**: 
   - POC 범위와 목표를 명확히 정의합니다
   - 2~3일 정도의 집중 테스트 시간을 할당합니다

2. **순차적 접근**:
   - ITSM 워크플로우 → 자산관리 → 보고서 순으로 진행합니다
   - 각 단계마다 체크리스트 항목을 확인합니다

3. **실제 비즈니스 시나리오 적용**:
   - 실제 회사의 워크플로우와 유사한 테스트 케이스를 구성합니다
   - 다양한 사용자 역할로 테스트합니다

## 다음 단계

POC를 완료한 후:
1. 피드백 수렴
2. 담당자와 결과 논의 (위두소프트 이우석 이사 alan@wedosoft.net)
3. 필요한 경우 추가 테스트 계획 수립

[홈으로 돌아가기](../) | [자산관리 워크플로우](../asset-management/) | [ITSM 워크플로우](../itsm-workflow/) | [라이선스 권장사항](../license-recommendations/) | [PoC 전략](../strategy/) 