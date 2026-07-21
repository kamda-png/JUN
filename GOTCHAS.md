# Gotchas

- 2026-07-21: `C:\Users\dev`는 `kamda` 계정에 쓰기 권한이 없음(`icacls` 확인 결과 `BUILTIN\Users:(RX)`만 부여) → git clone이 "Permission denied"로 실패. 비대화형 셸에서 `icacls ... /grant`로 권한을 올리려 해도 관리자 승인 없이는 "Access is denied"로 막힘 → 대신 이미 쓰기 가능한 `C:\Users\kamda` 아래로 작업 위치를 옮김.
- 2026-07-21: 이 머신에 git 전역 사용자 정보(`user.name`/`user.email`)가 전혀 설정돼 있지 않아 첫 커밋 시도가 "Author identity unknown"으로 실패할 수 있음 → `git config --global`로 먼저 설정 필요 (이 머신은 `kamda9017@gmail.com` / `kamda`로 이미 설정됨, [love/GOTCHAS.md](../love/GOTCHAS.md) 참고).
