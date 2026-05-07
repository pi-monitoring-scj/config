#  Pi-Monitoring: Infra & Config Center

> **"분산된 디지털 트윈 시스템의 환경 설정과 인프라를 중앙 집중적으로 관리합니다."**

IoT 엣지 디바이스(라즈베리파이)부터 백엔드(FastAPI), 프론트엔드(Next.js) 대시보드에 이르기까지 전체 데이터 파이프라인의 인프라스트럭처와 `Config`를 제어하는 저장소입니다.

##  Repository Purpose
하드웨어 센서 계층과 소프트웨어 서비스 계층이 분리된 아키텍처에서, 설정의 파편화를 방지하고 배포 안정성을 확보하기 위해 인프라 설정을 완전히 분리했습니다.
* **단일 진실 공급원(SSOT)**: 시스템 전반의 환경 변수 및 의존성 템플릿 관리
* **보안 및 규격화**: 민감한 인증 정보는 배제하고 `.env.example`을 통한 규격 제공
* **인프라 자동화**: Docker Compose를 활용하여 복잡한 마이크로서비스 환경 원클릭 구축

##  Architecture & Structure
```text
.
├── docker-compose.yml         # 시스템 전체(API, Web, DB, MQTT 브로커) 오케스트레이션
├── backend/
│   └── .env.example           # FastAPI (Pydantic Settings) 및 DB/MQTT 접속 설정 가이드
└── frontend/
    └── .env.example           # Next.js 클라이언트 환경 변수 가이드
