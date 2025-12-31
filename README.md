# Trippy-BE ✈️
Trippy는 복잡한 여행 경비 관리 때문에 스트레스를 받는 여행자를 위한 전자 지갑 서비스입니다.

## 프로젝트 목적
정신없는 여행 일정 속에서 소비를 파악하고 조절하기 어려울 때 지출 관리를 하나의 전자 지갑 앱만으로 편리하게 해결하고자 이 서비스를 기획하게 되었습니다.

## 프로젝트 기간
2025.07.09 ~ 2025.08.21

## 기술 스택
| 구분 | 기술스택 |
|-----|-----|
| Core | Spring Framework(Legacy), Java 17, Lombok |
| 보안/인증 | Spring Security, JWT, CORS |
| 세션/토큰 | Redis |
| 데이터베이스 | MySQL(AWS RDS), MyBatis |
| 문서화 | Swagger (Springfox) |
| 배포/인프라 | AWS EC2, Nginx, Docker, Github Actions |
| 운영/모니터링 | AWS CloudWatch, Discord |
| 협업 | Git, GitHub, Slack, Discord, Notion |

## 주요 기능
<img width="1007" height="565" alt="image" src="https://github.com/user-attachments/assets/ab611962-5e65-4230-8a04-e4ab2bd04ea6" />

<details>
  <summary>💳 모임계좌</summary>

  - 여행 중 발생하는 결제 내역을 하나의 전자 지갑에서 관리
  - 카드 / 계좌 / 현금 지출 통합 관리
  - 해외 결제 내역 자동 환율 적용
</details>

<details>
  <summary>💳 여행로그</summary>

  - 여행 중 발생하는 결제 내역을 하나의 전자 지갑에서 관리
  - 카드 / 계좌 / 현금 지출 통합 관리
  - 해외 결제 내역 자동 환율 적용
</details>

<details>
  <summary>💳 환율/환전</summary>

  - 여행 중 발생하는 결제 내역을 하나의 전자 지갑에서 관리
  - 카드 / 계좌 / 현금 지출 통합 관리
  - 해외 결제 내역 자동 환율 적용
</details>

<details>
  <summary>💳 항공권/바우처</summary>

  - 여행 중 발생하는 결제 내역을 하나의 전자 지갑에서 관리
  - 카드 / 계좌 / 현금 지출 통합 관리
  - 해외 결제 내역 자동 환율 적용
</details>

<details>
  <summary>💳 신분증/여권</summary>

  - 여행 중 발생하는 결제 내역을 하나의 전자 지갑에서 관리
  - 카드 / 계좌 / 현금 지출 통합 관리
  - 해외 결제 내역 자동 환율 적용
</details>

## 팀원
| 이름 | 담당기능 | 
|-----|-----|
| 이재정 | 팀리드, DB 설계, 수출입 은행 외부API연동, 환율/환전 기능 |
| 이소정 | 클라이언트 리드, UI 디자인, Codef OpenAPI 연동, 홈/계좌/송금 기능, PWA 프론트엔드 배포 |
| 안현주 | 백엔드 리드, UI 디자인, AWS - S3 연동, 디스코드 웹 후크, 바우처/JWT 자동화, GPT 번역 기능 구현 |
| 강병현 | DB 설계, CI/CD 무중단 배포, 보안 관리, 모니터링 연결, 주민등록증 OCR, 여권 등록 기능 |
| 강예성 | UI 디자인, 모임 계좌, 카카오톡 초대 링크기능 |
| 이주원 | DB 설계, Codef OpenAPI 연동, 카드 결제/QR 코드 생성 및 활성화, 카드 설정 기능 |
| 홍승원 | DB 설계, Google Map API 연동, 여행 로그/여행 리포트, 결제 내역 지도 조회 |

## 시스템 아키텍처
<img width="1001" height="557" alt="image" src="https://github.com/user-attachments/assets/0026c6be-a2a4-4985-a341-9ce9825527d6" />
