# ✈️Trippy
Trippy는 복잡한 여행 경비 관리 때문에 스트레스를 받는 여행자를 위한 전자 지갑 서비스입니다.

## 📑기획 배경
**1. 파편화된 정보 관리의 불편함**<br>
- 여행자들은 지출 내역을 확인하기 위해 금융 앱을 확인하고, 이를 다시 엑셀이나 별도의 메모 앱에 수기로 정리하며, 방문 장소를 기억하기 위해 지도 앱을 오가는 번거로운 과정을 반복하고 있습니다.  

**2. 단체 정산의 페인 포인트**<br>
- 여행 후 영수증을 모아 한꺼번에 정산하는 방식은 내역 누락의 위험이 큽니다. 이는 정산 시간의 지연뿐만 아니라 모임원 간의 오해와 감정적 소모를 야기하는 원인이 됩니다.  

**3. 실시간 소비 파악의 어려움**<br>
- 복잡한 환율 변동과 다양한 지출 카테고리(항공, 숙박, 교통 등)로 인해, 현재 내가 예산 대비 얼마나 쓰고 있는지 실시간으로 체감하기 어렵습니다.

## 🎯프로젝트 목적
Trippy는 정신없는 여행 일정 속에서 소비를 파악하고 조절하기 어려울 때 지출 관리를 하나의 전자 지갑 앱만으로 편리하게 해결하고자 이 서비스를 기획하게 되었습니다.

## 📅프로젝트 기간
2025.07.09 ~ 2025.08.21

## 🛠기술 스택
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

## ✨주요 기능
<img width="1007" height="565" alt="image" src="https://github.com/user-attachments/assets/ab611962-5e65-4230-8a04-e4ab2bd04ea6" />

<details>
  <summary>💳 모임계좌</summary>
  <img width="6852" height="3820" alt="image" src="https://github.com/user-attachments/assets/a538226a-09ff-4243-918f-5e7c47c9587b" />
  
</details>

<details>
  <summary>🗺️ 여행로그</summary>
  <img width="7380" height="4448" alt="image" src="https://github.com/user-attachments/assets/b8682102-82d7-47ef-8173-ed708b041399" />

</details>

<details>
  <summary>💱 환율/환전</summary>
  <img width="3294" height="1788" alt="image" src="https://github.com/user-attachments/assets/b5449d63-70a8-4701-bb12-36f956dc3df3" />

</details>

<details>
  <summary>📱 결제</summary>
  <img width="6944" height="3756" alt="image" src="https://github.com/user-attachments/assets/8bb854ea-bffc-47ae-9990-98c6ed710c39" />

</details>

<details>
  <summary>🎟️ 항공권/바우처</summary>
  <img width="6900" height="3596" alt="image" src="https://github.com/user-attachments/assets/84544d60-4c4f-4e6a-8d9e-e79f456af8cf" />

</details>

<details>
  <summary>💳 신분증/여권</summary>
  <img width="6732" height="3520" alt="image" src="https://github.com/user-attachments/assets/48c851d2-a1c6-40eb-b271-c48309168118" />

</details>

## 👥팀원
| 이름 | 담당역할 | 
|-----|-----|
| 이재정 | 팀리드, DB 설계, 수출입 은행 외부API연동, 환율/환전 기능 |
| 이소정 | 클라이언트 리드, UI/UX 디자인, Codef OpenAPI 연동, 홈/계좌/송금 기능 |
| 안현주 | 백엔드 리드, UI/UX 디자인, AWS - S3 연동, 디스코드 웹 후크, 바우처/JWT 자동화, GPT 번역 기능 구현 |
| 강병현 | DB 설계, CI/CD 무중단 배포, 보안 관리, 모니터링 연결, 주민등록증 OCR, 여권 등록 기능 |
| 강예성 | 모임 계좌, UI/UX 디자인, 카카오톡 초대 링크기능 |
| 이주원 | DB 설계, Codef OpenAPI 연동, 카드 결제/QR 코드 생성 및 활성화, 카드 설정 기능 |
| 홍승원 | DB 설계, Google Map API 연동, 여행 로그/여행 리포트, 결제 내역 지도 조회 |

## 🏗️시스템 아키텍처
<img width="1001" height="557" alt="image" src="https://github.com/user-attachments/assets/0026c6be-a2a4-4985-a341-9ce9825527d6" />

## 🗄️ERD (Entity Relationship Diagram) 설계
금융권의 데이터 처리 방식과 시스템의 안정성을 고려하여 다음과 같은 원칙을 적용했습니다.

**1. 삭제 대신 비활성 플래그를 도입(Soft Delete)** <br>
- 금융감독 및 법적 감사에 대비하여 물리적 삭제 대신 **is_deleted**를 도입하였습니다.

**2. FK 대신 식별 컬럼 사용** <br>
- 대규모 트랜잭션 환경에서의 데드락(Deadlock) 방지와 성능 최적화를 위해 물리적 FK를 제거했습니다.
- 향후 서비스 확장에 따른 DB 샤딩 및 분산 환경을 고려한 설계입니다.

**3. 애플리케이션 레벨의 정합성 통제** <br>
- DB 제약조건 대신 서비스 레이어에서 유효성 검사를 수행하고, Spring **@Transactional**을 통해 데이터 무결성을 보장했습니다. <br>

<details>
  <summary>ERD 상세내용</summary>
  <img width="1880" height="1806" alt="image" src="https://github.com/user-attachments/assets/486ad887-b748-406c-914b-079d2d643abe" />  

</details>

