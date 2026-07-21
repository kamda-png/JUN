# Gotchas

- 2026-07-19: `mcp__claude-in-chrome__computer`의 `zoom` 액션이 CDP `Page.captureScreenshot` 30초 타임아웃으로 실패함 → 그냥 일반 `screenshot` 액션으로 재시도해서 상태 확인.
- 2026-07-21: `C:\Users\dev`는 `kamda` 계정에 쓰기 권한이 없음(`icacls` 확인 결과 `BUILTIN\Users:(RX)`만 부여, Administrators/SYSTEM만 Full Control) → git clone이 "Permission denied"로 실패. 비대화형 셸에서 `icacls ... /grant`로 권한을 올리려 해도 관리자 승인 없이는 "Access is denied"로 막힘 → 대신 이미 쓰기 가능한 `C:\Users\kamda` 아래로 작업 위치를 옮김.
- 2026-07-21: Git Bash에서 `icacls "path" /grant "user:(OI)(CI)F" /T`를 그대로 전달하면 `/grant`를 경로로 오인해 깨짐 → 이런 Windows 전용 플래그 명령은 PowerShell 도구로 실행해야 함.
- 2026-07-21: 이 머신에 git 전역 사용자 정보(`user.name`/`user.email`)가 전혀 설정돼 있지 않아 첫 커밋 시도가 "Author identity unknown"으로 실패 → `git config --global`로 먼저 설정 필요.
