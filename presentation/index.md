---
layout: default
---

# PoC 프레젠테이션 자료

## 1. PoC 개요 및 목표

### 배경
- GS는 한국의 대기업으로, IT 서비스 관리 및 자산 관리를 위한 솔루션으로 Freshservice 도입을 검토
- 현재 MS 환경의 SCIM을 사용 중이며, 보다 효율적이고 통합된 ITSM 솔루션 필요

### PoC 목표
- ITSM 워크플로우 구현 및 시연을 통한 Freshservice 기능 검증
- IT 자산관리 워크플로우 구현 및 시연을 통한 자산관리 기능 검증
- Freshservice의 사용자 경험 및 인터페이스 평가
- 라이선스 옵션 평가 및 최적 플랜 결정

### PoC 기간 및 참여자
- 기간: 약 2주
- 참여자: GS 측 2-3명, Freshservice 전문가(컨설팅 및 가이드 제공)

### PoC 성공 기준
1. **ITMS 워크플로우**
   - 현업 담당자 요청 → 현업 리더 승인 → 지주사 IT담당자 확인 및 할당 → IT운영팀 처리 → 완료 결과 확인 → 만족도 측정 워크플로우 구현
   - 각 단계별 알림 및 에스컬레이션 기능 작동 확인
   - SLA 설정 및 모니터링 기능 확인

2. **IT 자산관리**
   - CSV를 통한 20개 이상의 자산 데이터 업로드 성공
   - 자산 수명주기(입사~퇴직, 자산이관, 폐기) 추적 설정
   - 자산과 티켓 연결 기능 확인
   - 온보딩/오프보딩 티켓 생성 및 처리 확인

## 2. Freshservice 소개

### Freshservice란?
- 클라우드 기반 ITSM(IT Service Management) 솔루션
- 직관적인 인터페이스와 강력한 자동화 기능 제공
- 전 세계 72,000개 이상의 기업에서 사용 중

### 주요 기능
- 인시던트 관리, 서비스 카탈로그, 변경 관리 등 ITIL 기반 ITSM 기능
- 자산 관리 및 자산 수명주기 관리
- 워크플로우 자동화 및 승인 프로세스
- 보고 및 분석 기능
- AI 기반 서비스 개선 기능

### Freshservice의 장점
- 직관적인 사용자 인터페이스로 빠른 적응 가능
- 코드 없이 워크플로우 구성 가능
- 유연한 확장성 및 통합 옵션
- 빠른 구현 및 ROI 실현

## 3. ITMS 워크플로우 구현 가이드

### 워크플로우 개요
- 현업 담당자 요청부터 만족도 측정까지의 전체 프로세스 자동화
- 다단계 승인 및 할당 프로세스 구현
- SLA 및 알림 설정을 통한 효율적인 관리

### 티켓 상태 및 역할 정의
- 신규, 승인 대기, 승인됨, 할당 대기, 할당됨, 진행 중, 해결됨, 종료, 거부됨 등의 상태 정의
- 현업 담당자, 현업 리더, 지주사 IT담당자, IT운영팀 등의 역할 정의

### 구현 단계
1. **서비스 요청 양식 설정**
   - 요청 제목, 설명, 우선순위, 유형, 사유 등의 필드 포함
   - 첨부 파일 기능 활성화

2. **승인 워크플로우 설정**
   - 현업 리더 승인 단계 설정
   - 지주사 IT담당자 승인 단계 설정

3. **자동화 규칙 설정**
   - 요청 제출 시 자동화: 상태 변경, 알림 발송
   - 승인 후 자동화: 상태 변경, 담당자 알림
   - 할당 후 자동화: 상태 변경, 담당자 알림
   - 해결 후 자동화: 만족도 평가 요청

4. **만족도 측정 설정**
   - 서비스 요청 처리에 대한 만족도 설문 구성
   - 처리 속도, 커뮤니케이션, 전반적 만족도 측정

### 시연 시나리오
- 소프트웨어 설치 요청 시나리오
- 하드웨어 문제 해결 요청 시나리오

## 4. 자산관리 워크플로우 구현 가이드

### 자산관리 개요
- 자산의 도입부터 폐기까지 전체 수명주기 관리
- PC, 노트북, 태블릿, 모니터 등 다양한 자산 유형 지원
- 자산 관련 이슈 발생 시 신속한 대응 체계 구축

### 자산 데이터 구조
- 자산 태그, 자산명, 유형, 제조사, 모델, 시리얼 번호 등 기본 정보
- 구매일, 보증 만료일, 상태, 할당 상태 등 관리 정보
- 사용자, 부서, 위치 등 할당 정보
- OS, CPU, RAM 등 기술 정보

### 자산 수명주기 워크플로우
1. **신규 입사자 자산 할당 워크플로우**
   - 입사 예정 알림 → 자산 준비 → 자산 할당 → 자산 인계 및 교육 → 완료 및 기록

2. **퇴직자 자산 회수 워크플로우**
   - 퇴직 예정 알림 → 자산 확인 → 자산 회수 → 자산 상태 업데이트 → 자산 평가 및 처리 결정

3. **자산 이관 워크플로우**
   - 이관 요청 → 요청 승인 → 자산 회수 및 준비 → 자산 재할당 → 완료 및 기록

4. **자산 폐기 워크플로우**
   - 폐기 대상 식별 → 폐기 승인 요청 → 승인 프로세스 → 데이터 삭제 및 초기화 → 물리적 폐기 → 자산 기록 업데이트

### 구현 단계
1. **자산 데이터 업로드**
   - CSV 파일 준비 및 업로드
   - 필드 매핑 및 가져오기 실행

2. **자산 관계 설정**
   - 관계 유형 정의 (연결됨, 부속품, 하위 항목 등)
   - 자산 간 관계 설정

3. **자산 수명주기 자동화 설정**
   - 자산 상태 정의
   - 자동화 규칙 설정

4. **서비스 요청 템플릿 설정**
   - 온보딩/오프보딩 템플릿
   - 자산 이관/폐기 템플릿

### 시연 시나리오
- 신규 입사자 온보딩 시나리오
- 퇴직자 오프보딩 시나리오
- 자산 이관 시나리오
- 자산 폐기 시나리오

## 5. 라이선스 옵션 분석

### 라이선스 플랜 개요
- Starter 플랜 ($19/에이전트/월): 기본적인 ITSM 기능
- Growth 플랜 ($49/에이전트/월): 중간 규모 기업용, 기본 자산관리 포함
- Pro 플랜 ($99/에이전트/월): 대규모 조직용, ITSM, ITOM, 프로젝트 관리
- Enterprise 플랜 (맞춤형 가격): 엔터프라이즈급 서비스 관리 솔루션

### Pro vs Enterprise 플랜 비교
- **ITSM 기능**: Enterprise는 AI 에이전트, ServiceBot with AI agent 등 추가 기능 제공
- **자산관리 기능**: 대부분의 자산관리 기능은 두 플랜 모두 제공
- **자동화 및 통합**: Enterprise는 더 많은 오케스트레이션 트랜잭션과 고급 통합 옵션 제공
- **지원 및 서비스**: Enterprise는 프리미엄 지원 및 맞춤형 구현 지원 제공

### GS에 적합한 라이선스 권장사항
- **1순위: Enterprise 플랜**
  - 복잡한 워크플로우 자동화 지원
  - 고급 자산관리 기능
  - 향후 확장성 보장
  - 맞춤형 구현 지원

- **2순위: Pro 플랜**
  - 대부분의 핵심 기능 제공
  - 비용 효율적인 옵션
  - 향후 Enterprise로 업그레이드 가능

### Pro에서 Enterprise로의 업그레이드 경로
- 데이터 마이그레이션 없이 업그레이드 가능
- 일부 워크플로우 재구성 및 추가 구성 작업 필요
- 장기적 관점에서는 처음부터 Enterprise 플랜 선택이 효율적

## 6. 추가 지원 옵션

### 초기 설정 및 구성 지원
- 기본 설정 지원: 3-5일 소요
- 워크플로우 구성 지원: 5-10일 소요
- 자산관리 설정 지원: 3-5일 소요
- 통합 구성 지원: 5-15일 소요

### 커스터마이징 프로젝트
- 맞춤형 워크플로우 개발: 10-20일 소요
- 맞춤형 보고서 및 대시보드: 5-10일 소요
- 맞춤형 통합 개발: 15-30일 소요

### 교육 및 지원 옵션
- 관리자 교육: 1-2일 과정
- 최종 사용자 교육: 0.5-1일 과정
- 지속적인 기술 지원 및 컨설팅

## 7. PoC 진행 계획

### 1주차
- 1일차: 초기 설정 및 교육 세션
- 2-3일차: ITMS 워크플로우 구현
- 4-5일차: IT 자산관리 워크플로우 구현

### 2주차
- 6-7일차: 통합 테스트 및 시나리오 검증
- 8-9일차: 피드백 수집 및 조정
- 10일차: 결과 평가 및 향후 계획 논의

### PoC 이후 단계
- PoC 결과 평가 및 의사결정
- 라이선스 구매 및 계약
- 전체 구현 프로젝트 계획 수립
- 단계적 구현 및 롤아웃

## 8. 결론 및 질의응답

### 주요 결론
- Freshservice는 GS의 ITSM 및 자산관리 요구사항을 충족할 수 있는 적합한 솔루션
- 2주간의 PoC를 통해 주요 기능 검증 및 실제 환경 적용 가능성 평가 가능
- Enterprise 플랜이 GS의 요구사항에 가장 적합하나, 비용 제약 시 Pro 플랜으로 시작 가능

### 다음 단계
- PoC 일정 확정
- 참여자 지정 및 역할 정의
- 트라이얼 라이선스 발급
- PoC 환경 구성

### 질의응답
- 추가 질문이나 요청사항이 있으신가요?

[홈으로 돌아가기](../)
