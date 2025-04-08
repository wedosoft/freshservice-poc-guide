---
layout: default
---
[홈으로 돌아가기](../) | [자산관리 워크플로우](../asset-management/) | [라이선스 권장사항](../license-recommendations/) | [PoC 전략](../strategy/) | [셀프 POC 가이드](../self-service-poc/) | <a href="#top" id="top">맨 위로</a>

# ITSM 워크플로우 

> **실습 링크**: <a href="https://gsholdings.freshservice.com/ws/2/admin/automators" target="_blank">워크플로우 자동화 설정</a>

## 1. 워크플로우 개요

Freshservice에서 관리 가능한 ITSM 워크플로우:
- 현업 담당자 요청 → 현업 리더 승인 → IT담당자 할당 → IT운영팀 처리 → 결과 확인 → 만족도 측정

## 2. 설정 및 테스트 방법

| 설정 항목 | 실습 링크 | 주요 기능 |
|---------|-----------|---------|
| 사용자/그룹 관리 | [사용자 관리](https://gsholdings.freshservice.com/ws/2/admin/home) | 역할, 부서, 그룹 설정 |
| 워크플로우 자동화 | [자동화 설정](https://gsholdings.freshservice.com/ws/2/admin/automators) | 승인 요청, 할당 규칙, 알림 설정 |
| SLA 정책 | [SLA 설정](https://gsholdings.freshservice.com/ws/2/admin/sla_policies) | 응답/해결 시간 설정 |

### 2.1 사용자 관리 구성요소

> **실습 링크**: <a href="https://gsholdings.freshservice.com/ws/2/admin/home" target="_blank">사용자 관리 화면</a>

사용자 관리 페이지에서 필요한 구성요소를 직접 설정해보세요:

| 구성요소 | 설명 | PoC 구성 권장사항 |
|---------|------|-----------------|
| 에이전트 | 서비스 데스크 담당자 관리 | 테스트용 에이전트 3-4명 추가 |
| 역할 | 권한 설정 및 관리 | 요청자, 승인자, 관리자, 처리자 역할 생성 |
| 부서 | 조직 구조 관리 | 현업부서, IT부서, IT운영팀 등 생성 |
| 요청자 그룹 | 서비스 요청자 그룹 관리 | 현업 사용자용 그룹 생성 |
| 변경자문위원회 | 변경 요청 승인 담당 | 간단한 변경관리 워크플로우용 설정 |

**PoC 진행에 필요한 최소 구성**:
- 현업 담당자 (요청자)
- 현업 리더 (승인자)
- 지주사 IT담당자 (관리자)
- IT운영팀 (처리자)

## 3. 주요 테스트 시나리오

> **실습 링크**: <a href="https://gsholdings.freshservice.com/support/tickets/new" target="_blank">새 티켓 생성</a>

| 시나리오 | 테스트 방법 |
|---------|------------|
| 소프트웨어 설치 요청 | 현업 담당자 요청 → 현업 리더 승인 → IT담당자 할당 → IT운영팀 처리 → 만족도 평가 |
| 하드웨어 요청 | 현업 담당자 요청 → 현업 리더 승인 → IT담당자 할당 → IT운영팀 처리 → 만족도 평가 |

## 4. 확인 포인트

- 자동 알림 발송 여부
- 각 단계별 상태 변경 적용
- SLA 타이머 작동 확인
- 워크플로우 보고서 생성

[홈으로 돌아가기](../) | [자산관리 워크플로우](../asset-management/) | [라이선스 권장사항](../license-recommendations/) | [PoC 전략](../strategy/) | [셀프 POC 가이드](../self-service-poc/) | <a href="#top">맨 위로</a>
