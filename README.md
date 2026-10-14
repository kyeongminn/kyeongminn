<div align="center">

<h1>Hi, I'm Kyeong Min 👋</h1>

<p><strong>사용자 화면부터 서버의 상태까지, 서비스의 흐름을 잇는 개발자 김경민입니다.</strong></p>

<p>
  <img src="https://img.shields.io/badge/Backend-2563EB?style=flat-square" alt="Backend" />
  <img src="https://img.shields.io/badge/Web%20%26%20Mobile-0F172A?style=flat-square" alt="Web and Mobile" />
  <img src="https://img.shields.io/badge/Data-64748B?style=flat-square" alt="Data" />
</p>

<p>
  <a href="#-about-me">About</a> ·
  <a href="#-tech-stack">Tech Stack</a> ·
  <a href="#-selected-projects">Projects</a>
</p>

</div>

---

## 🌱 About Me

Java와 Spring으로 서버를 만들고, React와 Flutter로 사용자 화면을 구현해 왔습니다.<br>
실시간 연결이 끊기거나 요청이 중복되는 상황에서도 데이터와 화면이 일관되게 이어지는 서비스에 관심이 있습니다.

- **Backend** — 인증·권한, 실시간 메시지 처리, 트랜잭션과 상태 복원
- **Web & Mobile** — API 연동, 비동기 응답 처리, 공통 컴포넌트와 사용자 흐름
- **Data** — 공공데이터 수집·정제·결합, 리뷰 감성분석과 시각화

## 🛠 Tech Stack

**Backend**

<p>
  <img src="https://img.shields.io/badge/Java-0F172A?style=flat-square" alt="Java" />
  <img src="https://img.shields.io/badge/Spring%20Boot-0F172A?style=flat-square&amp;logo=springboot&amp;logoColor=6DB33F" alt="Spring Boot" />
  <img src="https://img.shields.io/badge/Spring%20Security-0F172A?style=flat-square&amp;logo=springsecurity&amp;logoColor=6DB33F" alt="Spring Security" />
  <img src="https://img.shields.io/badge/JPA-0F172A?style=flat-square" alt="JPA" />
  <img src="https://img.shields.io/badge/WebSocket%20%2F%20STOMP-0F172A?style=flat-square" alt="WebSocket and STOMP" />
</p>

**Frontend**

<p>
  <img src="https://img.shields.io/badge/React-0F172A?style=flat-square&amp;logo=react&amp;logoColor=61DAFB" alt="React" />
  <img src="https://img.shields.io/badge/TypeScript-0F172A?style=flat-square&amp;logo=typescript&amp;logoColor=3178C6" alt="TypeScript" />
  <img src="https://img.shields.io/badge/JavaScript-0F172A?style=flat-square&amp;logo=javascript&amp;logoColor=F7DF1E" alt="JavaScript" />
  <img src="https://img.shields.io/badge/Flutter-0F172A?style=flat-square&amp;logo=flutter&amp;logoColor=54C5F8" alt="Flutter" />
  <img src="https://img.shields.io/badge/Dart-0F172A?style=flat-square&amp;logo=dart&amp;logoColor=54C5F8" alt="Dart" />
</p>

**Database & Data**

<p>
  <img src="https://img.shields.io/badge/PostgreSQL-0F172A?style=flat-square&amp;logo=postgresql&amp;logoColor=8CB4E2" alt="PostgreSQL" />
  <img src="https://img.shields.io/badge/Redis-0F172A?style=flat-square&amp;logo=redis&amp;logoColor=FF4438" alt="Redis" />
  <img src="https://img.shields.io/badge/Python-0F172A?style=flat-square&amp;logo=python&amp;logoColor=FFD43B" alt="Python" />
  <img src="https://img.shields.io/badge/pandas-0F172A?style=flat-square&amp;logo=pandas&amp;logoColor=FFFFFF" alt="pandas" />
</p>

## 🚀 Selected Projects

| Project | 서비스 소개 | 내가 맡은 부분 |
| :--- | :--- | :--- |
| **ANTENNA · 앤테나**<br><sub>React · TypeScript · Spring Boot</sub> | 근거와 함께 주식 예측을 기록하고, 해시와 블록체인 앵커로 기록의 변경 여부를 검증하는 투자 정보 플랫폼 | React 화면·라우트 권한 가드·API 오류 처리, 커밋 원장과 검산 UI, 구독·대회 기능의 일부 Spring API |
| **BidLive · 비드라이브**<br><sub>Spring Boot · PostgreSQL · Redis</sub> | 라이브 방송을 보며 비공개로 입찰하고, 최고 입찰자가 2등가를 기준으로 낙찰받는 경매 플랫폼 | 실시간 채팅, STOMP 인증·구독 권한, 중복 메시지 처리, 재접속 상태 복원, 운영 지표 |
| **[SSAIREN · 싸이렌](https://github.com/SSAIREN/Frontend)**<br><sub>Flutter · Dart · WebSocket</sub> | 통화 중 보이스피싱 위험을 분석하고 경고와 대응 흐름으로 연결하는 예방 서비스 | 홈·키패드·연락처·통화기록·결과 화면, 실시간 감시 연결과 통화 종료 시 비동기 처리 |
| **[FinStart](https://github.com/FinManager2025/finstart_front)**<br><sub>React · Spring Boot · Oracle</sub> | 사회초년생을 위한 금융정보 입력과 예·적금 상품 비교 서비스 | 금융정보 입력·수정 및 추천 결과 UI, 금융정보 저장 API, 금융감독원 API 연동과 규칙 기반 점수화 로직 |

<details>
<summary><strong>🔎 구현하면서 고민한 것들</strong></summary>

<br>

**BidLive — 메시지를 저장하는 시점과 보여주는 시점**

재전송된 메시지가 중복 저장되지 않도록 `clientMessageId`를 멱등 키로 사용했습니다. PostgreSQL 트랜잭션이 커밋된 뒤에 WebSocket 이벤트를 발행하고, 재접속 시 REST 스냅샷으로 현재 상태를 복원하도록 구성했습니다.

**BidLive — 외부 API의 지연과 실패 처리**

채팅의 연락처·계좌번호 마스킹과 비동기 LLM 검열을 분리했습니다. 검열 작업에 재시도와 DLQ를 두고, 처리 상태를 로그와 지표로 확인할 수 있도록 구현했습니다.

**SSAIREN — 통화가 끝난 뒤 도착하는 응답**

통화 종료 상태를 비동기 콜백에서 확인해, 늦게 도착한 분석 결과가 종료된 화면을 다시 바꾸지 않도록 처리했습니다. 종료 시 타이머와 WebSocket 구독을 정리하고, 서버 종료 확인에는 대기 시간 제한을 적용했습니다.

**FinStart — 화면과 추천 로직의 연결**

금융상품과 금리 옵션을 상품 코드로 묶고, 금액·기간 단위를 정규화해 점수화했습니다. 추천 요청에 고정 예시값이 남아 있어 사용자 입력부터 추천까지의 개인화 연결은 후속 개선 과제로 남았습니다.

</details>

<details>
<summary><strong>📂 More Projects</strong></summary>

<br>

### [Segye World · 세계월드](https://github.com/segye-world)

일정·할 일·수입과 지출을 하루의 타임라인에 모으는 생활 관리 서비스입니다.

- **담당:** Flutter 일정 상세·입력 화면, 인증·API 연동, 일정·할 일 Spring API와 검증, PostgreSQL 전환
- **기술:** Flutter, Dart, Spring Boot, PostgreSQL

### [광진구 착한가격업소 발굴](https://github.com/kyeongminn/bigdata_contest)

공공데이터와 메뉴 가격·리뷰를 결합해 착한가격업소 후보를 찾는 팀 분석 프로젝트입니다.

- **담당:** 데이터 수집·전처리·주소 및 상호 매칭, 크롤링, BERT 기반 리뷰 감성분석
- **팀 결과:** 가격·위생·서비스 기준으로 최종 후보 **96개 업소** 선정 및 지도 시각화
- **기술:** Python, pandas, Selenium, BERT, matplotlib

</details>

---

<div align="center">
  <sub>화면에 보이는 결과와 서버에 남는 기록이 일치하는 서비스를 만들고 싶습니다.</sub>
</div>
