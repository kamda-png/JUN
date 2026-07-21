# Runbooks

## JUN 저장소를 새 위치에 다시 clone하기

**언제**: 새 머신이나 새 폴더에서 `kamda-png/JUN` 작업을 이어가야 할 때.

**절차**:
1. `git ls-remote https://github.com/kamda-png/JUN` 로 접근 가능 여부 확인 (출력 없이 exit 0이면 커밋이 없는 빈 저장소여도 정상).
2. 대상 폴더가 쓰기 가능한지 확인: `icacls "대상경로"`로 현재 계정에 `F`/`M` 권한이 있는지 확인. 없으면 [WIKI.md](WIKI.md) 참고.
3. `git clone https://github.com/kamda-png/JUN <대상폴더>` 실행.
4. `git -C <대상폴더> remote -v`로 origin이 올바른지 확인.

## 이 머신에서 git identity가 없을 때

**언제**: 첫 커밋 시 "Author identity unknown" 에러가 날 때.

**절차**:
1. `git config --global user.email` / `git config --global user.name`으로 기존 설정 여부 확인.
2. 없으면 `git config --global user.email "kamda9017@gmail.com"`, `git config --global user.name "kamda"`로 설정.
3. 다시 `git commit` 재시도.

자세한 내용은 [love/RUNBOOKS.md](../love/RUNBOOKS.md) 참고 (같은 저장소의 다른 clone, 권한 우회 런북 포함).
