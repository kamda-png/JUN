# Runbooks

## JUN 저장소를 새 위치에 다시 clone하기

**언제**: 새 머신이나 새 폴더에서 `kamda-png/JUN` 작업을 이어가야 할 때.

**절차**:
1. `git ls-remote https://github.com/kamda-png/JUN` 로 접근 가능 여부 확인 (출력 없이 exit 0이면 커밋이 없는 빈 저장소여도 정상).
2. 대상 폴더가 쓰기 가능한지 확인: `icacls "대상경로"`로 현재 계정에 `F`/`M` 권한이 있는지 확인. 없으면 [Windows 사용자 폴더 쓰기 권한 확인/우회](WIKI.md) 참고.
3. `git clone https://github.com/kamda-png/JUN <대상폴더>` 실행.
4. `git -C <대상폴더> remote -v`로 origin이 올바른지 확인.

## 이 머신에서 git identity가 없을 때

**언제**: 첫 커밋 시 "Author identity unknown" 에러가 날 때.

**절차**:
1. `git config --global user.email` / `git config --global user.name`으로 기존 설정 여부 확인.
2. 없으면 `git config --global user.email "kamda9017@gmail.com"`, `git config --global user.name "kamda"`로 설정 (이 사용자의 기본 identity).
3. 다시 `git commit` 재시도.

## Windows 폴더 쓰기 권한이 없을 때 (관리자 권한 없이)

**언제**: 특정 폴더에서 git clone/파일 생성이 "Permission denied"로 실패하고, 비대화형 셸이라 UAC 승격도 안 될 때.

**절차**:
1. `icacls "경로"`로 ACL 확인.
2. 관리자 권한 셸에서 직접 `icacls`를 실행할 수 있는 사용자라면, 그 사용자에게 명령을 안내하고 `!` 접두사로 대신 실행하도록 요청.
3. 그마저 여의치 않으면 이미 쓰기 가능한 경로(로그인 계정 홈 디렉토리 등)로 작업 위치를 옮기는 것을 대안으로 제시.
