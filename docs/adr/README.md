# Architecture Decision Records

엔디즈 조직의 중요한 기술·운영 결정을 기록하는 저장소.

## ADR이란

**Architecture Decision Record**. 중요한 결정의 "무엇을 왜 어떻게 정했는가"를 짧은 문서 단위로 남기는 방식. 6개월 뒤 "왜 이걸 이렇게 했지?" 질문에 답이 되는 유일한 소스.

자세한 철학·작성 기준·상태 관리 규칙은 엔디즈 노션 `문서화 규칙` 페이지 `ADR` 섹션 참고.

## 저장 범위

이 디렉토리(`.github/docs/adr/`)에는 **조직 전체에 영향을 주는 결정**만 둔다.

- 모든 앱 레포에 적용되는 규약 (Git Flow, CI 전략 등)
- 조직 운영 정책 (공용 계정, 보안, 외부 도구 사용)
- 메타 규칙 (예: "앱마다 기술 스택을 자율 선택한다")

앱 고유의 결정(SwiftUI vs UIKit, 아키텍처 선택 등)은 **해당 앱 레포의 `docs/adr/`**에 둔다.

## 파일명 규칙

```
NNN-short-title.md
```

- `NNN`: 3자리 숫자, 생성 순서대로 증가. 폐기된 ADR도 번호 유지 (재사용 금지).
- `short-title`: kebab-case, 결정의 요지를 3~5단어로.

예: `001-adopt-git-flow.md`

## 상태(Status) 관리

- **proposed**: 초안. 팀 리뷰 중.
- **accepted**: 확정. 현재 유효.
- **deprecated**: 더는 유효하지 않음. 대체 ADR 없이 폐기.
- **superseded by ADR-NNN**: 새 ADR이 대체함. 링크로 후속 ADR 지정.

한 번 `accepted`된 ADR은 본문을 수정하지 않는다. 결정이 바뀌면 새 ADR을 작성하고 기존 ADR의 상태만 `superseded by ADR-NNN`으로 변경한다. 히스토리 보존이 목적.

## 작성 방법

### 자동 (권장)

Claude Code에서 슬래시 커맨드 `/adr`을 사용한다. Claude가 다음을 자동 수행:

- 다음 번호 계산
- `TEMPLATE.md` 기반 초안 작성 (대화 컨텍스트와 memory에서 배경·근거 추출)
- `NNN-title.md` 파일 생성
- `README.md` 색인 갱신
- 브랜치·커밋·PR 생성

작성자는 PR에서 초안 검토·수정·머지.

> 슬래시 커맨드는 추후 구축 예정. 그전까지는 아래 수동 방식 사용.

### 수동

1. `TEMPLATE.md`를 복사해서 `NNN-short-title.md`로 저장
2. 상단 메타(작성일, 작성자, 상태) 입력
3. 배경·결정·근거·결과 섹션 작성
4. 아래 색인 표에 새 행 추가
5. 브랜치 생성(`docs/ANDIZ-N-adr-NNN`)·커밋·PR 제출
6. 리뷰 통과 후 상태를 `accepted`로 변경하고 머지

## 색인

| 번호 | 제목 | 상태 | 작성일 | 링크 |
|------|------|------|--------|------|
| 001 | Git Flow 풀버전 채택 | accepted | 2026-04-22 | [001-adopt-git-flow.md](./001-adopt-git-flow.md) |
| 002 | 앱별 기술 스택 유연성 | accepted | 2026-04-22 | [002-flexible-tech-stack.md](./002-flexible-tech-stack.md) |
| 003 | 공용 계정 정책 및 Bitwarden 옵션 A 구조 | accepted | 2026-04-22 | [003-shared-accounts-bitwarden-option-a.md](./003-shared-accounts-bitwarden-option-a.md) |
| 004 | Chrome 프로필 분리 유예 | accepted | 2026-04-22 | [004-defer-chrome-profile-separation.md](./004-defer-chrome-profile-separation.md) |
