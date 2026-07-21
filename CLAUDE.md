# CLAUDE.md

이 파일은 이 저장소(`kamda-png/JUN`, 로컬 경로 `C:\Users\kamda\love`)에서 작업할 때 Claude Code가 참고하는 프로젝트 지침 스냅샷이다. 사실이 바뀌면 이 파일을 최신 상태로 덮어쓴다 (session-close 스킬의 "에이전트/라우팅" 절차 참고).

## 저장소 개요
- GitHub: `kamda-png/JUN` (원격 `origin`)
- 2026-07-21 기준: 커밋 히스토리에 애플리케이션 코드는 없고, 세션 운영 문서(GOTCHAS/WIKI/STATUS/DECISIONS/COST_REFERENCE/DASHBOARD/RUNBOOKS/AGENTS/omc-routing 등)만 존재.
- 같은 저장소(`kamda-png/JUN`)를 clone한 별도 작업 폴더가 `C:\Users\kamda\translate`에도 있음 — 서로 독립적인 working copy이며 자동 동기화되지 않음. 한쪽에서 커밋/푸시한 내용은 다른 쪽에서 `git pull`해야 반영됨.

## 빌드/실행
- 아직 애플리케이션 코드가 없어 빌드/테스트/실행 명령이 정의되지 않음. 코드가 추가되면 이 섹션을 채울 것.

## 배포
- Vercel 계정(`kamda9017-2411`)에 GitHub 연동은 되어 있으나, 이 저장소를 Vercel 프로젝트로 import하는 단계는 아직 진행 전. 자세한 내용은 [STATUS.md](STATUS.md), [DASHBOARD.md](DASHBOARD.md) 참고.

## 환경 관련 유의사항
- 이 머신에서 `C:\Users\dev`는 현재 로그인 계정(`kamda`)에 쓰기 권한이 없다 — 파일 작업은 `C:\Users\kamda` 아래에서 진행할 것. 자세한 내용은 [GOTCHAS.md](GOTCHAS.md), [RUNBOOKS.md](RUNBOOKS.md) 참고.
- `gh` (GitHub CLI)는 이 머신에 설치되어 있지 않음 — 저장소 목록 조회 등은 `git` 명령이나 웹으로 대체.
