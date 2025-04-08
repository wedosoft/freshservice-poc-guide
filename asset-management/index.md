---
layout: default
---
[홈으로 돌아가기](../) | [ITSM 워크플로우](../itsm-workflow/) | [라이선스 권장사항](../license-recommendations/) | [PoC 전략](../strategy/) | [셀프 POC 가이드](../self-service-poc/)

# 자산관리 워크플로우

> **실습 링크**: <a href="https://gsholdings.freshservice.com/cmdb/items" target="_blank">자산 관리 화면</a>

## 1. 자산 수명주기 개요

Freshservice에서 관리 가능한 자산 수명주기:
- 자산 도입 및 등록 → 자산 할당 → 사용 및 유지보수 → 자산 이관 → 자산 회수 → 자산 폐기

## 2. 설정 및 테스트 방법

| 설정 항목 | 실습 링크 | 주요 기능 |
|---------|-----------|---------|
| 자산 가져오기 | [데이터 업로드](https://gsholdings.freshservice.com/cmdb/items) | CSV 파일로 자산 데이터 대량 등록 |
| 자산 유형 관리 | [유형 설정](https://gsholdings.freshservice.com/cmdb/ci_types) | 하드웨어, 소프트웨어 등 유형별 속성 정의 |
| 자산 자동화 | [워크플로우 설정](https://gsholdings.freshservice.com/ws/2/admin/automators) | 자산 상태 변경, 알림 자동화 |
| 보고서 | [자산 보고서](https://gsholdings.freshservice.com/analytics) | 자산 현황 분석 및 시각화 |

## 3. 샘플 데이터 활용

> **실습 링크**: <a href="https://gsholdings.freshservice.com/cmdb/items" target="_blank">자산 가져오기 화면</a>

아래 샘플 CSV를 이용해 자산 데이터 업로드를 테스트할 수 있습니다:

```csv
자산_태그,자산명,자산_유형,제조사,모델,시리얼_번호,구매일,보증_만료일,상태,할당_상태,위치,사용자,부서,할당일,OS,CPU,RAM,스토리지
GS-PC-0001,Dell Latitude 7420,노트북,Dell,Latitude 7420,ABC123456,2023-01-15,2026-01-14,사용 중,할당됨,본사 3층,홍길동,마케팅,2023-01-20,Windows 11 Pro,Intel i7-1185G7,16GB,512GB SSD
GS-PC-0002,HP EliteBook 840,노트북,HP,EliteBook 840 G8,DEF789012,2023-02-10,2026-02-09,사용 중,할당됨,본사 2층,김영희,재무,2023-02-15,Windows 11 Pro,Intel i5-1145G7,8GB,256GB SSD
GS-PC-0003,Lenovo ThinkPad X1,노트북,Lenovo,ThinkPad X1 Carbon,GHI345678,2023-02-20,2026-02-19,사용 중,할당됨,지사 1층,이철수,영업,2023-02-25,Windows 11 Pro,Intel i7-1165G7,16GB,512GB SSD
GS-PC-0004,Dell OptiPlex 7080,데스크탑,Dell,OptiPlex 7080,JKL901234,2023-03-05,2026-03-04,사용 중,할당됨,본사 1층,박지민,인사,2023-03-10,Windows 11 Pro,Intel i5-10500,16GB,512GB SSD
GS-PC-0005,MacBook Pro 14,노트북,Apple,MacBook Pro 14,MNO567890,2023-03-15,2025-03-14,사용 중,할당됨,본사 3층,최민지,디자인,2023-03-20,macOS Monterey,Apple M1 Pro,16GB,512GB SSD
GS-TAB-0001,iPad Pro 12.9,태블릿,Apple,iPad Pro 12.9,PQR123456,2023-04-10,2025-04-09,사용 중,할당됨,본사 3층,홍길동,마케팅,2023-04-15,iPadOS 16,Apple M2,8GB,256GB
GS-TAB-0002,Samsung Galaxy Tab S8,태블릿,Samsung,Galaxy Tab S8 Ultra,STU789012,2023-04-20,2025-04-19,사용 중,할당됨,지사 1층,이철수,영업,2023-04-25,Android 13,Snapdragon 8 Gen 1,12GB,256GB
GS-PHN-0001,iPhone 14 Pro,스마트폰,Apple,iPhone 14 Pro,VWX345678,2023-05-10,2025-05-09,사용 중,할당됨,본사 3층,최민지,디자인,2023-05-15,iOS 16,Apple A16 Bionic,6GB,256GB
GS-PHN-0002,Samsung Galaxy S23,스마트폰,Samsung,Galaxy S23 Ultra,YZA901234,2023-05-20,2025-05-19,사용 중,할당됨,본사 2층,김영희,재무,2023-05-25,Android 13,Snapdragon 8 Gen 2,12GB,256GB
GS-SVR-0001,Dell PowerEdge R750,서버,Dell,PowerEdge R750,BCD567890,2023-01-05,2027-01-04,사용 중,할당됨,데이터센터,IT인프라팀,IT,2023-01-10,Windows Server 2022,Intel Xeon Gold 5318Y,128GB,4TB SSD
```

**CSV 파일 준비 팁**: UTF-8 인코딩으로 저장, 한글 칼럼명 사용 가능
**[샘플 파일 다운로드](./sample-data/asset-sample.csv)**

## 4. 주요 테스트 시나리오

> **실습 링크**: <a href="https://gsholdings.freshservice.com/support/tickets/new" target="_blank">새 티켓 생성 화면</a>

| 시나리오 | 테스트 방법 |
|---------|------------|
| 신규 입사자 자산 할당 | 입사자 정보 입력 → 자산 준비 → 자산 할당 |
| 퇴직자 자산 회수 | 퇴직자 정보 입력 → 자산 목록 확인 → 자산 회수 |
| 자산 이관 | 이관 요청 → 데이터 백업 → 재할당 → 정보 업데이트 |
| 자산 폐기 | 폐기 대상 식별 → 승인 요청 → 상태 변경 |

## 5. 확인 포인트

- 자산 데이터 가져오기 성공 여부
- 자산과 티켓 연결 기능
- 자산 상태 자동 업데이트
- 자산 보고서 생성 및 대시보드 구성

[홈으로 돌아가기](../) | [ITSM 워크플로우](../itsm-workflow/) | [라이선스 권장사항](../license-recommendations/) | [PoC 전략](../strategy/) | [셀프 POC 가이드](../self-service-poc/)
