# speak-up (스픽업)

**"악센트를 듣고, 알맞게 발음한다"** — AI 기반 영어 악센트 스피킹 튜터링 서비스

## 프로젝트 소개

기존 영어 학습 서비스는 대부분 미국식 발음과 문법·회화 중심으로 설계되어 있어, 영국·호주 등 다양한 영어권 국가의 악센트와 표현 차이를 체계적으로 학습하기 어렵습니다.

스픽업은 AI 음성 분석·생성 기술을 활용해 사용자가 원하는 악센트(미국식/영국식/호주식)를 선택해 학습하고, 발음·억양·강세를 실시간으로 분석·교정받을 수 있는 개인화된 스피킹 튜터링 서비스입니다.

### 차별화 포인트

1. **악센트별 '리듬' 코칭** — 단어 발음의 정오뿐 아니라 영국/호주식 특유의 억양과 말하는 리듬감을 분리해 교정
2. **현지 맞춤형 '어휘' 추천** — 문법적으로 맞아도 현지에서 어색한 표현을 실시간으로 자연스러운 현지 어휘로 안내 (예: `drugstore` → `chemist's`)
3. **직관적인 '성적표' UX** — 복잡한 파형/음소 그래프 대신 "런던 출근 3일 차, 영국인 싱크로율 58%" 같은 이해하기 쉬운 피드백 제공

## 주요 기능 (목표)

- STT 기반 음성 인식 및 실시간 발음/억양 분석
- 미국식(en-US) / 영국식(en-GB) / 호주식(en-AU) 악센트 선택 학습
- 음소·단어·문장 단위의 정확도·유창성·완결성·운율(prosody) 피드백
- 국가·지역별 표현·어휘·슬랭 차이를 추천하는 NLP 기반 학습 기능
- TTS 기반 원어민 음성 제공

## 기술 스택 (예정)

| 영역 | 스택 |
| --- | --- |
| Frontend | React Native |
| Backend | Django |
| DB | MySQL / MariaDB |
| 음성 분석 | Microsoft Azure Speech Service (Pronunciation Assessment, en-US/en-GB/en-AU 지원) |
| 초기 플랫폼 | Android 우선 진행 |

> 기술 스택 및 아키텍처는 초기 기획 단계로, 세부 사항은 추후 확정·변경될 수 있습니다.

## 팀

| 이름 | 역할 |
| --- | --- |
| 조수인 | 프로젝트 총괄(PM), 데이터 엔지니어링, 풀스택 아키텍처 및 클라이언트 구현 |
| 조아람 | 핵심 AI 엔진 엔지니어링 및 백엔드 코어 비즈니스 로직 개발 |

## 폴더 구조

```
speak-up/
├── backend/    # 백엔드 (API 서버, 데이터 처리 등)
├── frontend/   # 프론트엔드 (UI/UX, 클라이언트 애플리케이션)
├── ai/         # AI (모델, 학습/추론 파이프라인)
└── .github/    # GitHub 설정 (CI 워크플로우, CODEOWNERS)
```

각 영역별 상세 내용은 하위 README를 참고하세요.

- [backend/README.md](backend/README.md)
- [frontend/README.md](frontend/README.md)
- [ai/README.md](ai/README.md)

## 브랜치 전략

```
main
  └── develop
        ├── feature/back-*   (backend 작업)
        ├── feature/front-*  (frontend 작업)
        └── feature/ai-*     (ai 작업)
```

- `main`: 배포 가능한 안정 버전을 유지하는 브랜치
- `develop`: 다음 릴리즈를 준비하는 통합 개발 브랜치
- `feature/*`: 개별 기능 개발 브랜치 (아래 네이밍 컨벤션 참고)

## 기여 방법 / PR 규칙

1. `develop`에서 `feature/*` 브랜치를 생성하여 작업합니다.
2. 작업이 끝나면 `feature/*` → `develop`으로 PR을 생성합니다.
3. 릴리즈 시점에는 `develop` → `main`으로 PR을 생성합니다.

## feature 브랜치 네이밍 컨벤션

| 영역 | 브랜치 접두사 |
| --- | --- |
| Backend | `feature/back-*` |
| Frontend | `feature/front-*` |
| AI | `feature/ai-*` |

예: `feature/back-login-api`, `feature/front-signup-page`, `feature/ai-stt-model`
