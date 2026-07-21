# Decisions

## 2026-07-21: 저장소 clone 위치를 `C:\Users\dev` 대신 `C:\Users\kamda`로 변경

**배경**: `C:\Users\dev`는 `kamda` 계정에 쓰기 권한이 없어(`icacls` 확인 결과 `BUILTIN\Users:(RX)`만 부여) `git clone`이 실패.

**대안 검토**: `icacls`로 권한을 올리는 것을 시도했으나, 비대화형 셸에서는 관리자 승인(UAC) 없이 "Access is denied"로 막힘.

**결정**: 권한 문제를 우회해, 이미 쓰기 가능한 `kamda` 계정 홈 디렉토리(`C:\Users\kamda\translate`, `C:\Users\kamda\love`)에 저장소를 clone. `C:\Users\dev`의 원본 파일은 손대지 않고 그대로 둠. 향후 `C:\Users\dev`에 쓰기 권한이 필요하면 사용자가 직접 관리자 권한 PowerShell에서 `icacls` 명령을 실행해야 함.

## 2026-07-21: `translate`와 `love`를 같은 저장소(`kamda-png/JUN`)의 별도 clone으로 유지

**배경**: 사용자가 두 로컬 폴더(`translate`, `love`) 모두를 동일한 GitHub 저장소에 연결해 달라고 요청.

**결정**: 두 폴더를 하나로 합치지 않고, 각각 독립적인 clone으로 유지(둘 다 origin이 `kamda-png/JUN`을 가리킴).

**후속(같은 날)**: `love`와 `translate`가 같은 파일명(STATUS.md, GOTCHAS.md 등)을 서로 다른 내용으로 커밋하다 보니 `main` 하나로는 충돌이 남. 결국 `translate`를 별도 브랜치(`translate`)로 분리하고 `love`는 계속 `main`을 사용하기로 함. 자세한 내용은 [translate/DECISIONS.md](../translate/DECISIONS.md) 참고.

## 2026-07-21: 기존 `dev\love` 문서 파일을 새 저장소로 이전 후 커밋+푸시

**배경**: `C:\Users\dev\love`에 이미 GOTCHAS.md/STATUS.md/WIKI.md/out.txt가 있었음.

**결정**: 사용자 승인을 받아 파일을 새 저장소로 복사하고 커밋, `origin/main`에 push. 원본은 삭제하지 않고 `C:\Users\dev\love`에 그대로 남김.
