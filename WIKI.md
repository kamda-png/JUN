# Wiki

## Windows 사용자 폴더 쓰기 권한 확인/우회

문제: 특정 폴더(예: `C:\Users\dev`)에서 git clone 등 파일 생성이 "Permission denied"로 실패.

해결:
1. `icacls "경로"` 로 ACL 확인 — 현재 계정이 속한 그룹(`BUILTIN\Users` 등)에 `F`(Full)나 `M`(Modify)이 없고 `RX`(읽기/실행)만 있으면 쓰기 불가.
2. 권한을 고치려면 `icacls "경로" /grant "사용자:(OI)(CI)F" /T` (관리자 권한 필요, PowerShell에서 실행 — Git Bash로 실행하면 `/grant`가 경로로 오인되어 깨짐).
3. 비대화형 셸(Claude Code 등)은 UAC 승격을 띄울 수 없어서 관리자 권한이 없으면 이 명령 자체가 "Access is denied"로 실패함 → 사용자가 직접 관리자 PowerShell을 열어 실행하거나, 이미 쓰기 가능한 다른 경로(예: 로그인 계정의 홈 디렉토리 `C:\Users\<계정명>`)를 대신 사용.

자세한 배경은 [love/WIKI.md](../love/WIKI.md) 참고 (같은 저장소의 다른 clone).
