# 임주원 (Juwon Lim)

Backend engineer at 한국딥러닝, building the backend of Vision-LLM Document AI products (DEEP Agent, DEEP Parser).

문서 AI 제품의 백엔드를 맡습니다. 모델 자체가 아니라 모델을 둘러싼 부분이 일입니다. 추론 엔진과 주고받는 계약, VLM 출력을 제품 스키마로 정규화하는 층, 과금과 공개 API, 그리고 배포 때마다 추출이 실제로 되는지 확인하는 안전망을 만듭니다.

## 경력

| 기간 | 회사 | 역할 |
|---|---|---|
| 2025.11 부터 현재 | [한국딥러닝](https://koreadeep.com) | Backend Engineer. Vision-LLM 기반 Document AI 제품 (DEEP Agent, DEEP Parser) |
| 2022.08 부터 2025.11 | 시선AI (구 씨유박스, KOSDAQ 상장) | Backend Engineer, AI Lab. 영상 AI 보안과 인증 (얼굴 인식, X-ray) |

## 주요 작업

### 한국딥러닝

- **DEEP Agent SaaS 백엔드** (2025.12 부터 2026.08). Paddle 구독 결제와 크레딧 시스템 (원자적 차감, 웹훅 멱등성과 순서 뒤바뀜 처리). OCR Direct API (동기, 비동기 잡과 폴링, 웹훅, API 키별 rate limit 과 동시성 제한). VLM 이 내는 평평한 key-value 를 섹션 트리와 중첩 표로 정규화하는 SchemaDocument 계층. 보안 감사에서 16건을 찾아 critical 4건 (IDOR, stored XSS, brute force, admin fail-open) 을 포함해 전부 닫음. 2026-04-01 정식 출시. [보도](https://www.venturesquare.net/1079342)
- **DEEP Agent 설치형 제품** (2026.06 부터 현재). SaaS 를 fork 해 온프레미스 제품으로 분리. 배포 안전망 설계: 배포 뒤 실제 문서 1건을 업로드부터 추출까지 돌리고, 실패하면 외부 의존성 (추론 엔진, 변환기, 파서, 마스킹, 스토리지) 을 프로브해 원인을 귀속하며, 우리 코드 탓일 때만 자동 롤백. 롤백 여부는 직전 이미지로 같은 추출을 다시 돌리는 대조 실험으로 판정. 실 변환기와 파서에 실문서 9종을 보내는 계약 드리프트 게이트. 5분 스트림을 감싸던 DB 트랜잭션 (idle-in-transaction), 스토리지 커넥션 풀 고갈, DB 커넥션 고갈을 근본 수정.
- **금융권 고객사 BMT** (2026.05, 3주, PR 185건). 요구 기능 전부, 정확도와 속도 평가 대시보드, AWS 에서 온프레미스 SeaweedFS 로 이전, GPU 가 없을 때 쓰는 데모 모드.
- **경기도청 생성형 AI 플랫폼의 DEEP Parser 백엔드** (2025.11 부터 2026.08). 동기 배치를 Celery 와 Valkey 비동기 파이프라인으로 교체 (워커 5개, 재시도, 타임아웃 복구). 고아 페이지 12,557건 정합성 복구, 적재마다 테이블을 다시 만들던 데드락 원인 제거, 폐쇄망 릴리스 패키징. [보도](https://www.venturesquare.net/1001395)
- **Polyground 3D 마켓플레이스 재구축** (2026.06 부터 2026.08). 백엔드를 혼자 처음부터 구축 (FastAPI, PostgreSQL, Celery). 텍스트와 이미지에서 3D 생성 (제공자 추상화, ModelsLab 에서 Tripo3D 로 교체), FBX 를 GLB 와 Draco 로 바꾸는 파이프라인 (8.25배 압축), Blender headless 프리뷰 렌더링, Terraform AWS 와 Docker Swarm 무중단 배포.
- **공통 SDK 와 내부 도구**. SaaS 와 온프레미스 사본의 드리프트를 막는 사내 공통 SDK (새 버전이 나오면 각 제품 레포에 버전 상향 PR 을 자동으로 연다). Claude Code 플러그인 3종 중 공개 2종: [claude-jira-ticket](https://github.com/KDL-Solution/claude-jira-ticket), [claude-tempo](https://github.com/KDL-Solution/claude-tempo).

### 시선AI

- **국토교통부 국가 R&D, AI 3D X-ray 기내 반입 수하물 검색** (5년, 150억). 장비 관리 REST API 서버 (ASP.NET, EF, MySQL), 링 버퍼 기반 커스텀 TCP 프로토콜, Redis Active-Active HA, 하드웨어 없이 도는 시뮬레이터. 인천공항 테스트베드 2024, TTA V&V 인증 2025. [보도](https://m.boannews.com/html/detail.html?idx=96408)
- **얼굴 인식 매칭 서버 (FRS)**. 증권사 비대면 인증을 위해 liveness 판정을 모바일에서 서버로 옮기고 OTP 와 AES-256 적용. 카지노 키오스크의 쌍둥이 구분용 Top-N. 운영 배포.
- **AI 모델 서빙 API**. FastAPI 와 NVIDIA Triton 으로 신분증, 얼굴, X-ray 모델 서빙. Locust 부하 테스트로 1초 안에 응답하는 최대 사용자 수를 재고 EC2 를 4코어에서 2코어로 줄임.

## 활동 지표

한국딥러닝 GitHub 조직 (KDL-Solution) 에서 2025-11-17 부터 2026-09-22 까지, 약 10개월.

| 지표 | 값 |
|---|---|
| 작성한 PR | 2,167건 (머지 2,096건, 96.7%) |
| 리뷰한 PR | 135건 |
| 커밋 | 4,964건 |
| 기여한 레포 | 27개 (백엔드, 프론트엔드, 인프라, SDK, 내부 도구) |

측정: GitHub 검색 API 로 조직 안 PR 과 커밋을 작성자 기준으로 센 값. 레포가 전부 비공개라 프로필의 기여 그래프에는 잡히지 않는다.

## 오픈소스 기여

**[stuartcrobinson/unique-window-colors](https://github.com/stuartcrobinson/unique-window-colors)** (VS Code 확장)

- [#74](https://github.com/stuartcrobinson/unique-window-colors/issues/74): VS Code 1.131 모던 UI 가 타이틀바, 액티비티바, 상태바 색상 커스터마이징을 무시하는 문제의 원인 규명. 확장 버그가 아니라 업스트림 회귀임을 밝히고, `workbench.experimental.modernUI` 가 선언상 기본값 `false` 인데도 실험 `mode: "auto"` 로 켜져서 진단이 어려웠던 지점까지 정리. README 안내 반영됨 (v1.2.11). 업스트림 [microsoft/vscode#326126](https://github.com/microsoft/vscode/issues/326126) 은 [PR #329701](https://github.com/microsoft/vscode/pull/329701) 로 수정되어 1.133.0 에 릴리스.
- [#75](https://github.com/stuartcrobinson/unique-window-colors/issues/75): `.vscode/settings.json` 은 JSONC 인데 `JSON.parse` 로 읽어 창 종료 시 `SettingsFileDeleter.dispose` 가 예외를 던지던 버그 리포트. `jsonc-parser` 도입으로 수정됨 (v1.2.11).

## 스택

Python 3.13, FastAPI, SQLAlchemy (asyncpg), Alembic, Celery, Pydantic, PostgreSQL, Valkey, SeaweedFS, S3, Docker Swarm, GitHub Actions (self-hosted), Terraform, Kong, Harbor, NVIDIA Triton. 이전에는 C# ASP.NET 과 Java Spring Boot.
