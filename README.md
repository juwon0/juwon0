# 임주원 (Juwon Lim)

Backend engineer at 한국딥러닝, building the backend of Vision-LLM Document AI products.

모델을 둘러싼 부분을 만듭니다. 추론 엔진과의 계약, VLM 출력 정규화, 과금과 공개 API, 배포 뒤 추출이 실제로 되는지 확인하는 안전망입니다.

## 경력

| 기간 | 회사 | 역할 |
|---|---|---|
| 2025.11 부터 현재 | [한국딥러닝](https://koreadeep.com) | Backend Engineer. Document AI 제품 (DEEP Agent, DEEP Parser) |
| 2022.08 부터 2025.11 | [시선AI](https://secern.ai) (구 씨유박스) | Backend Engineer, AI Lab. 영상 AI 보안과 인증 |

## 주요 작업

### 한국딥러닝

- **DEEP Agent SaaS 백엔드**: 구독 결제와 크레딧, OCR 공개 API, VLM 출력 정규화 계층. 2026년 4월 정식 출시. [보도](https://www.venturesquare.net/1079342)
- **설치형 제품의 배포 안전망**: 배포 뒤 실문서 1건을 추출까지 돌리고, 원인이 우리 코드일 때만 자동 롤백.
- **경기도청 생성형 AI 플랫폼의 DEEP Parser 백엔드**: 동기 배치를 Celery 비동기 파이프라인으로 교체하고 고아 페이지 12,557건 복구. [보도](https://www.venturesquare.net/1001395)
- **금융권 고객사 BMT**: 3주 안에 요구 기능 전부와 평가 대시보드, 온프레미스 스토리지 이전 완료.

### 시선AI

- **국토교통부 AI 3D X-ray 수하물 검색 R&D**: 장비 관리 API 서버와 커스텀 TCP 프로토콜, Redis HA. TTA V&V 인증. [보도](https://m.boannews.com/html/detail.html?idx=96408)
- **얼굴 인식 매칭 서버**: 증권사 비대면 인증을 위해 liveness 판정을 모바일에서 서버로 옮겨 운영 배포.

## 활동 지표

| 지표 | 값 |
|---|---|
| 작성한 PR | 2,167건 (머지 2,096건) |
| 리뷰한 PR | 135건 |
| 커밋 | 4,964건 |
| 기여한 레포 | 27개 |

측정: GitHub 검색 API, KDL-Solution 조직, 작성자 기준. 2025-11-17 부터 2026-09-22 까지.

## 오픈소스 기여

[stuartcrobinson/unique-window-colors](https://github.com/stuartcrobinson/unique-window-colors) (VS Code 확장)

- [#74](https://github.com/stuartcrobinson/unique-window-colors/issues/74): 색상 설정 무시가 확장이 아니라 VS Code 회귀임을 규명. 업스트림 [microsoft/vscode#326126](https://github.com/microsoft/vscode/issues/326126) 이 [PR #329701](https://github.com/microsoft/vscode/pull/329701) 로 수정됨.
- [#75](https://github.com/stuartcrobinson/unique-window-colors/issues/75): JSONC 설정 파일을 `JSON.parse` 로 읽던 버그 리포트. `jsonc-parser` 로 수정됨.

## 스택

| 영역 | 도구 |
|---|---|
| 주력 | <img src="https://skillicons.dev/icons?i=python,fastapi,postgres,redis&theme=light" alt="Python, FastAPI, PostgreSQL, Valkey (Redis)" /> |
| 인프라 | <img src="https://skillicons.dev/icons?i=docker,githubactions,terraform,aws,nginx&theme=light" alt="Docker, GitHub Actions, Terraform, AWS, Nginx" /> |
| 그 밖에 | <img src="https://skillicons.dev/icons?i=cs,dotnet,java,spring,ts,nextjs&theme=light" alt="C#, .NET, Java, Spring, TypeScript, Next.js" /> |

아이콘 없는 도구: Celery, SQLAlchemy, Alembic, SeaweedFS, NVIDIA Triton, Kong, Harbor.
