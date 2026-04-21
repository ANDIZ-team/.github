# Andiz 기여 가이드

## 브랜치 전략 (Git Flow)
- `main` ← 앱스토어 출시 코드
- `develop` ← 개발 통합
- `feature/{이슈키}-{기능명}` ← 기능 개발 (예: `feature/ONION-123-login`)
- `release/v{버전}` ← 출시 준비
- `hotfix/{이슈키}-{설명}` ← 긴급 수정

상세: 노션 - Git 컨벤션 (URL은 노션 페이지 확정 후 업데이트)

## 커밋 메시지 (Conventional Commits)
```
{type}({이슈키}): {한글 설명}

예시:
feat(ONION-123): 로그인 버튼 추가
fix(ONION-456): 앱 실행 시 크래시 수정
```

type: `feat`, `fix`, `refactor`, `chore`, `docs`, `test`, `style`

## PR 규칙
- 제목: 커밋 메시지와 동일 형식
- **리뷰 1명 이상 approve 후 머지 (팀 약속, 셀프 머지 금지)**
- Squash merge 사용
- ⚠️ Free 플랜 제약으로 자동 강제 안 됨. Team 플랜 전환 시 Branch Protection으로 강제 예정

## Jira 키와 GitHub 레포 매칭
- 앱별 레포의 작업 → 그 앱 스페이스 키 사용 (예: OneOnion 레포 → `ONION-*`)
- 회사 운영/인프라 작업 → `ANDIZ-*` 사용 (어느 레포에서든 OK)

## 더 자세한 컨벤션
👉 노션 컨벤션 문서 (URL은 확정 후 업데이트)
