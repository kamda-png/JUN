# Wiki

## Vercel-GitHub 계정 연동

문제: Vercel 계정에서 GitHub 저장소를 임포트/배포하려면 먼저 Git 계정 연동이 필요.

해결:
1. `https://vercel.com/account/settings/authentication` 로 이동
2. "Sign-in Methods" 섹션에서 GitHub 항목의 "Connect" 버튼 클릭
3. 브라우저에 이미 GitHub 로그인 세션이 있으면 별도 인증 없이 즉시 연동됨 (팝업/리다이렉트 없이 바로 "Last used just now"로 표시됨)

연동 후 `https://vercel.com/[team]` 대시보드의 "Add New → Import Project"에서 연동된 GitHub 저장소를 가져와 배포 가능.
