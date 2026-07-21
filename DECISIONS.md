# Decisions

## 2026-07-21: 저장소 clone 위치를 `C:\Users\dev` 대신 `C:\Users\kamda`로 변경

**배경**: `C:\Users\dev`는 `kamda` 계정에 쓰기 권한이 없어(`icacls` 확인 결과 `BUILTIN\Users:(RX)`만 부여) `git clone`이 실패.

**대안 검토**: `icacls`로 권한을 올리는 것을 시도했으나, 비대화형 셸에서는 관리자 승인(UAC) 없이 "Access is denied"로 막힘.

**결정**: 이미 쓰기 가능한 `kamda` 계정 홈 디렉토리(`C:\Users\kamda\translate`)에 저장소를 clone. 자세한 배경은 [love/DECISIONS.md](../love/DECISIONS.md) 참고 (같은 저장소의 다른 clone에서 동일하게 적용된 결정).

## 2026-07-21: `translate`와 `love`를 같은 저장소(`kamda-png/JUN`)의 별도 clone으로 유지

**배경**: 사용자가 두 로컬 폴더(`translate`, `love`) 모두를 동일한 GitHub 저장소에 연결해 달라고 요청.

**결정**: 두 폴더를 하나로 합치지 않고, 각각 독립적인 clone으로 유지. 한쪽에서 커밋/푸시해도 다른 쪽은 자동 반영되지 않으므로, 작업 시작 전 `git pull`로 최신화할 것.

## 2026-07-21: `translate`는 `main`이 아닌 별도 브랜치(`translate`)에 push

**배경**: `love`와 `translate`가 같은 저장소의 같은 파일명(STATUS.md, GOTCHAS.md 등)을 서로 다른 내용으로 커밋하면서, 둘 다 `main`에 push하려 하니 `git pull --rebase`에서 add/add 충돌이 발생함 (love가 먼저 push한 상태였음).

**대안 검토**: (1) 파일을 하위 폴더로 분리해 경로 충돌을 피하는 방법, (2) 이번에 만든 문서를 취소하고 love 기준으로 맞추는 방법도 검토했으나, 사용자가 브랜치 분리를 선택.

**결정**: 로컬 브랜치명을 `main`에서 `translate`로 바꾸고 `origin/translate`(신규 브랜치)로 push. `love`는 계속 `origin/main`을 사용. 같은 저장소(`kamda-png/JUN`)를 공유하되 브랜치로 분리해 파일 경로 충돌을 피함.
