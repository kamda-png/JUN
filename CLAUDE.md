# CLAUDE.md

이 파일은 이 저장소(`kamda-png/JUN`, 로컬 경로 `C:\Users\kamda\translate`)에서 작업할 때 Claude Code가 참고하는 프로젝트 지침 스냅샷이다. 사실이 바뀌면 이 파일을 최신 상태로 덮어쓴다.

## 저장소 개요
- GitHub: `kamda-png/JUN` (원격 `origin`), **브랜치: `translate`** (main 아님)
- 2026-07-21 기준: 이 폴더에는 세션 운영 문서(GOTCHAS/WIKI/STATUS/DECISIONS/COST_REFERENCE/DASHBOARD/RUNBOOKS/AGENTS/omc-routing)만 있고, 애플리케이션 코드나 실제 "번역" 관련 작업 내용은 아직 없음.
- 같은 저장소(`kamda-png/JUN`)를 clone한 별도 작업 폴더가 `C:\Users\kamda\love`에도 있음 — `love`는 `main` 브랜치를 쓴다. 두 폴더가 같은 파일명(STATUS.md 등)을 다른 내용으로 커밋하기 때문에 브랜치를 분리했다 (자세한 배경은 [DECISIONS.md](DECISIONS.md) 참고). `git push`/`git pull` 시 반드시 `translate` 브랜치를 대상으로 할 것 — `main`으로 착각해 push하면 충돌한다.

## 빌드/실행
- 아직 정의되지 않음. 이 폴더의 목적(폴더명 "translate"로 미루어 번역 관련 작업으로 추정되나 미확인)이 확정되고 코드가 추가되면 이 섹션을 채울 것.

## 환경 관련 유의사항
- 이 머신에서 `C:\Users\dev`는 현재 로그인 계정(`kamda`)에 쓰기 권한이 없다 — 파일 작업은 `C:\Users\kamda` 아래에서 진행할 것. 자세한 내용은 [GOTCHAS.md](GOTCHAS.md), [RUNBOOKS.md](RUNBOOKS.md) 참고.
- `gh` (GitHub CLI)는 이 머신에 설치되어 있지 않음.
