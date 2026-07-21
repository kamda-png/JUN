# Wiki

## Vercel-GitHub 계정 연동

문제: Vercel 계정에서 GitHub 저장소를 임포트/배포하려면 먼저 Git 계정 연동이 필요.

해결:
1. `https://vercel.com/account/settings/authentication` 로 이동
2. "Sign-in Methods" 섹션에서 GitHub 항목의 "Connect" 버튼 클릭
3. 브라우저에 이미 GitHub 로그인 세션이 있으면 별도 인증 없이 즉시 연동됨 (팝업/리다이렉트 없이 바로 "Last used just now"로 표시됨)

연동 후 `https://vercel.com/[team]` 대시보드의 "Add New → Import Project"에서 연동된 GitHub 저장소를 가져와 배포 가능.

## Windows 사용자 폴더 쓰기 권한 확인/우회

문제: 특정 폴더(예: `C:\Users\dev`)에서 git clone 등 파일 생성이 "Permission denied"로 실패.

해결:
1. `icacls "경로"` 로 ACL 확인 — 현재 계정이 속한 그룹(`BUILTIN\Users` 등)에 `F`(Full)나 `M`(Modify)이 없고 `RX`(읽기/실행)만 있으면 쓰기 불가.
2. 권한을 고치려면 `icacls "경로" /grant "사용자:(OI)(CI)F" /T` (관리자 권한 필요, PowerShell에서 실행 — Git Bash로 실행하면 `/grant`가 경로로 오인되어 깨짐).
3. 비대화형 셸(Claude Code 등)은 UAC 승격을 띄울 수 없어서 관리자 권한이 없으면 이 명령 자체가 "Access is denied"로 실패함 → 사용자가 직접 관리자 PowerShell을 열어 실행하거나, 이미 쓰기 가능한 다른 경로(예: 로그인 계정의 홈 디렉토리 `C:\Users\<계정명>`)를 대신 사용.

## Git 최초 커밋 시 Author identity 에러

문제: 새 머신/새 셸 환경에서 첫 `git commit`이 "Author identity unknown"으로 실패.

해결: `git config --global user.email "you@example.com"`, `git config --global user.name "Your Name"`로 전역 설정 후 재시도. (이 머신은 `kamda9017@gmail.com` / `kamda`로 2026-07-21에 설정함.)
