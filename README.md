# speak-up

## 프로젝트 개요

speak-up은 backend / frontend / ai 세 영역으로 구성된 monorepo 프로젝트입니다. 각 영역은 독립적인 디렉터리에서 관리되며, 하나의 저장소에서 함께 버전 관리됩니다. 프로젝트는 아직 초기 단계로, 세부 기술 스택과 아키텍처는 추후 확정될 예정입니다.

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
