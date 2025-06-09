# 대학교내 물품 대여 서비스 RENTit
![KakaoTalk_20250605_232252838](https://github.com/user-attachments/assets/3c5b6a0b-175d-431a-89e8-c56a9c3e50da)

## 👤 팀원 소개
|이름|학과|학번|역할|
|---|---|---|---|
|김지환|소프트웨어학과|202020768|raspberry pi, frontend(app/web)|
|박준우|소프트웨어학과|202020798|backend|
|장지윤|소프트웨어학과|202127418|frontend(app/web)|

## 🎈 프로젝트 개요

### Main Target
비대면으로 교내에서 안전하게 물건을 빌리고 싶은 대학생

### Problem
- 직접 만나서 물건을 주고 받는 게 부담스러움
- 대여 절차가 복잡하거나 불확실함
- 반납 시 파손 책임 분쟁이 걱정됨

### Solution
- 모바일 앱을 통한 손쉬운 대여 신청
- OTP인증 기반으로 비대면 거래 지원
- 키오스크 UI로 손쉽게 대여/반납
- 사진을 통한 반납 인증
- 파손 정책 템플릿 제공 및 원하는 대로 수정 가능

## 🛠️ 개발 아키텍처
<details>
<summary><b>시스템 개요</b></summary>

</br>

![architecture](https://github.com/user-attachments/assets/ce2576cf-a240-4773-8b6d-f87e2457140b)

</br>

</details>

<details>
<summary><b>CI/CD</b></summary>

</br>

### 프론트엔드 - 웹
![devops frontend](https://github.com/user-attachments/assets/a71426a6-0738-498a-9208-cc9de492bbaf)

### 백엔드
![devops Backend](https://github.com/user-attachments/assets/4ca86323-b550-4f5a-9e5a-6cd95cb76974)

### Rasberry Pi
![devops rpi](https://github.com/user-attachments/assets/35978d03-9203-4fab-9a06-5e209b9dafff)

</details>

</br>

## 🗃️ 주요 기술 스택

<details>
<summary><b> Front-End(Web) </b></summary>

</br>

| 기술 스택 | 사용 목적 및 선택 이유 |
| --- | --- |
| React | UI 컴포넌트 기반의 웹 애플리케이션 개발을 위해 사용한다. 팀원이 사전에 사용해본 경험이 있으며, 생태계가 풍부하고 유지보수가 용이한 구조를 제공한다. |
| HTML | 웹 페이지의 구조를 정의하기 위해 사용한다. 모든 웹의 기반이며, SEO 및 접근성 측면에서도 필수적인 요소이다. |
| CSS | 디자인 및 레이아웃 스타일링을 위해 사용한다. |
| JavaScript | 동적인 UI 기능 구현 및 웹 페이지의 이벤트 처리, DOM 조작 등 웹 앱 동작의 핵심적인 언어이다. |
| Vite | 프론트엔드 빌드 및 개발 서버로 사용한다. 빠른 모듈 번들링과 HMR(Hot Module Replacement)을 제공하여, 개발 과정의 생산성을 높인다. |
| tailwindCSS | 빠른 개발 속도와 일관된 디자인 시스템을 적용하기 위해 선택하였다. 러닝커브가 다소 있지만 시장 점유율이 매우 높아 많은 레퍼런스로 커버 할 수 있을 것이라 예상하였다. Styled Component의 경우 반복되는 코드의 양을 줄이고 효율적인 CSS를 작성하기 위한 노력이 필요하나, tailwindCSS는 저수준의 유틸리티 클래스를 반복적으로 사용하는 방식을 권장하기 때문에 코드 리팩토링, 효율성을 위한 노력을 어느정도 덜어주는 효과를 기대하였다. |
| axios | 백엔드와 통신하는 API구현을 쉽게 하기 위해 사용하였다. Axios Instance, intercept 등의 기능을 제공하여 API 호출 함수를 쉽게 모듈화 할 수 있고, 공통 request 헤더, 자동 로그인 등을 적은 양의 코드로 구현할 수 있다. fetchAPI의 경우 response를 직접 JSON 형식으로 변환해야 하며 앞서 말한 기능을 직접 구현해야 하므로, axios를 사용하면 개발 속도 및 생산성을 높일 수 있을 것이라 기대하였다. |
| TypeScript | 정적 타입 기반의 개발을 지원하기 위해 사용한다. 컴파일 타임에 오류를 방지하고, 협업 시에 코드 안정성을 향상시켜 에러 및 버그를 미연에 방지할 수 있다. |
| recharts | 데이터를 시각화하는 컴포넌트를 제공한다. 간결한 문법으로 손쉽게 차트와 그래프 시각화를 구현할 수 있다. 동일한 데이터 시각화 라이브러리인 Chart.js도 고려하였으나, rechart가 통합, 문법 면에서 react에 더 친화적인 사항을 고려하였다. |
</br>

</details>


<details>
<summary><b> Front-End(App) </b></summary>

</br>

| 기술 스택 | 사용 목적 및 선택 이유 |
| --- | --- |
| React Native | Andriod와 iOS를 동시에 지원할 수 있으며, React 생태계와의 코드 공유가 가능하여 러닝커브가 낮고 개발 효율성이 높아서 사용한다. Flutter도 고려 대상이었으나, 팀원들이 React에 더 익숙하고, 도입까지 공부할 수 있는 시간이 부족하다고 판단하여 RN을 사용하게 되었다. |
| JavaScript | React Native 및 다양한 라이브러리와 연동되며, 빠른 프로토타이핑에 적합한 표준 스크립트 언어이다. |
| TypeScript | 정적 타입 기반의 개발을 지원하기 위해 사용한다. 컴파일 타임에 오류를 방지하고, 협업 시에 코드 안정성을 향상시켜 에러 및 버그를 미연에 방지할 수 있다. |
| Expo | 초기 개발 속도를 높이고 복잡한 네이티브 설정을 간소화하기 위해 사용하였고, 커뮤니티가 매우 활발하여 도움을 받을 수 있는 창구가 많다. 추후 필요 시 expo를 eject하여 네이티브 기능 확장도 할 수 있을 것으로 기대한다. |
| expo router | 페이지 기반 자동 라우팅을 지원하여 디렉토리 구조가 곧 app의 사이트맵과 유사한 구조를 가진다. react navigation을 사용할 때 처럼 직접 설정해야 하는 부분이 적고, 구조에 적응하면 빠르게 익힐 수 있어 선택하였다. |
| StyleSheet API | react-native 환경에서 기본적으로 styling을 적용하기 위한 tool이며, 많은 framework, library를 제치고 2024년 기준 개발자들이 2번째로 많이 사용함을 고려하였다. tamagui, react-native-paper, nativewind등 다른 UI library 및 tool도 테스트하였으나, 성능 저하, 버그, 지원하는 기능 등의 관점에서 StyleSheet API를 사용하는 것이 최선이라고 판단하였다. |

</br>

</details>

<details>
<summary><b> Back-End(Web/App) </b></summary>

</br>

| 기술 스택 | 사용 목적 및 선택 이유 |
| --- | --- |
| Spring | 대규모 웹 애플리케이션에 적합한 구조와 생태계를 갖춘 프레임워크로, MVC 기반 REST API에 활용된다. |
| Spring boot | 복잡한 Spring의 설정을 자동화하여 빠른 개발을 지원하며, 내장 서버로 배포가 용이하여 사용한다. |
| MySQL | 관계형 데이터베이스로, 대여 기록, 유저 정보 등 구조화된 데이터 관리를 위해 사용한다. |
| Spring Security | 유저 인증과 인가를 위한 보안 프레임워크로, JWT 및 Role 기반 접근 제어 구현에 사용한다. |
| Spring Data JPA | ORM 기반의 DB접근을 간소화하고, 생산성을 높이기 위해 사용한다. |
| Query DSL | 복잡한 조건 검색에 유리하고, 동적 쿼리 생성을 안전하게 작성하기 위해 사용한다. |
| JWT | 세션 없는 인증 방식으로, 모바일/웹 연동에 적합하며, 토큰 기반 인증 로직을 위해 사용한다. |
| JUnit5 | 테스트 자동화를 위한 표준 프레임워크로, 서비스 품질 확보 및 회귀 테스트에 용이하여 사용한다. |
| Firebase Cloud Notification | 대여 승인/반납 알림 등 실시간 푸시 알림 서비스를 사용자에게 제공하기 위해 사용한다. |
| UnivCert | 대학교 이메일 인증을 하기 위해 사용한다. |
| Paho-MQTT | MQTT 프로토콜을 사용해, RabbitMQ 브로커를 통해 Pi들과 통신하기 위해 사용한다. |
| Java | Spring 생태계의 기본 언어로, 안정적인 서버 개발 및 유지보수에 적합하여 사용한다. |
| Gradle | 프로젝트 의존성 관리 및 빌드 자동화를 위한 도구로, CI/CD 파이프라인과 연동하여 사용한다. |
| Object Storage(NCP) | 물품 이미지 및 대여 관련 파일들을 저장하기 위한 정적 파일 스토리지로 사용한다. 또한, 프론트엔드의 정적파일을 서빙하는 용도로도 사용한다. |

</br>

</details>

<details>
<summary><b> Front-End(Raspberry Pi) </b></summary>

| 기술 스택 | 사용 목적 및 선택 이유 |
| --- | --- |
| HTML | 웹페이지의 기본 구조를 구성하기 위해 사용한다. |
| CSS | 키오스크 UI의 스타일링과 레이아웃 구성을 위해 사용한다. |
| JS | 버튼 인터랙션, 상태 변경 등 동적인 기능을 구현하기 위해 사용하며, 자체 개발한 초경량 프론트엔드 프레임워크인 supeRThin의 핵심 구현 언어로도 사용한다다. |
| Chromium | HTML, CSS, JS로 구성된 웹페이지를 Raspberry Pi에서 로컬 환경으로 구동하기 위해 사용한다. |
| supeRThin | JS로 자체개발한 프론트엔드 프레임워크로, React나 Preact(React의 경량화 버전)보다 더 가볍게 구성되어 Raspberry Pi같은 저사양 환경에서도 충분히 구동된다. 상태관리, 컴포넌트 기반의 UI 개발을 통해, 프론트엔드 개발의 생산성을 높이기 위해 사용한다. |

</br>

</details>

<details>
<summary><b> Back-End(Rasberry Pi) </b></summary>


| 기술 스택 | 사용 목적 및 선택 이유 |
| --- | --- |
| FastAPI | 프론트에서 입력 된 데이터와 RabbitMQ로부터 전달되는 데이터를 처리하고, 키오스크 내부 제어 로직을 수행하기 위한 경량 웹서버로 사용한다. |
| FastAPI-MQTT | FastAPI와 RabbitMQ 간의 통신을 MQTT기반으로 구현하여, 비동기 메시지 수신 및 명령 수행을 지원하기에 사용한다. |
| Python | FastAPI 및 zerogpio 등 주요 키오스크 제어 모듈을 구동하기 위한 기본 언어로 사용한다. |
| zerogpio | Raspberry Pi 보드의 GPIO와 PWM을 Python 환경에서 관리하여, 물리적 락 제어나 센서 연동을 구현하기 위해 사용한다. |

</br>

</details>

<details>
<summary><b> MiddleWare </b></summary>

| 기술 스택 | 사용 목적 및 선택 이유 |
| --- | --- |
| RabbitMQ | 메시지 기반의 브로커로, Spring Boot API서버와 Raspberry Pi의 FastAPI간 통신을 비동기적으로 중계하고 제어하기 위해 사용한다.
Mosquitto도 고려 대상이었으나, NCP에서 RabbitMQ를 저렴한 가격에 제공 중이고, 다양한 관리 기능들을 통해 확장성을 더 제공해서 선택하게 되었다. |
| MQTT Plugin | 기본적으로 AMQP 프로토콜 기반으로 동작하는 RabbitMQ를 MQTT 프로토콜도 지원하도록 확장하여, IoT 환경(Pi↔ 서버)과의 효율적인 통신을 구현하기 위해 사용한다. |

</br>

</details>


<details>
<summary><b> Cloud 및 Infrastructure 구성 </b></summary>

| 기술 스택 | 사용 목적 및 선택 이유 |
| --- | --- |
| Global Edge(CDN) | 정적 웹 자산을 사용자들에게 빠르게 전달하고, 실제 정적 파일을 배포하는 Object Storage의 접근 부하를 줄이기 위해 사용한다. |
| Gateway | 내부 서버 API를 외부로 연결하고, 이 과정에서 보안 및 인증을 강화하기 위해 사용한다. |
| Object Storage | 이미지, 로그파일 등의 비정형 데이터를 저장하고, 또한 웹 페이지 정적 파일들을 배포하는 웹서버로서 동작하도록 하기 위해 사용한다. |
| ALB(Application Load Balancer) | 트래픽을 Auto Scaling을 통해 증설된 Server Instance로 분산해주기 위해 사용한다. |
| Server Instance | 백엔드 API 서버 등의 핵심 서비스를 호스팅하기 위해 사용한다. |
| Auto Scaling | 사용량이 몰리는 시간 등에 Server Instance를 정해진 규칙에 따라 자동으로 늘리고 줄이기 위해 사용한다. |
| Simple RabbitMQ | 키오스크와 서버 간의 메시지 통신을 관리하고, 비동기 처리를 통해 안정적인 연결을 지원하기 위해 사용한다. |
| subnet | 네트워크를 논리적인 단계에서 분리하여 보안성과 관리 효율을 높히기 위해 사용한다. |
| VPC | 격리된 네트워크 환경을 구축하여, 보안성과 제어력을 손쉽게 확보하기 위해 사용한다. |

</br>

</details>
