# Agents

이 프로젝트에서 Claude Code가 사용할 수 있는 에이전트/서브에이전트 종류와 역할. 라우팅 규칙(어떤 작업을 어느 에이전트로 보낼지)은 [omc-routing.md](omc-routing.md) 참고.

- **claude** — 특정 유형에 맞지 않는 범용 작업을 처리하는 기본 에이전트.
- **claude-code-guide** — Claude Code CLI, Claude Agent SDK, Claude API(Messages API, Tool Runner 등), Claude Tag(Slack) 관련 질문 전용. 읽기 전용 도구(Glob/Grep/Read/WebFetch/WebSearch)만 사용.
- **Explore** — 코드 위치를 찾는 읽기 전용 검색 에이전트. 파일 패턴 찾기, 심볼/키워드 grep, "X가 어디 정의됐나" 류 질문에 적합. 코드 리뷰나 설계 문서 감사, 전수 분석에는 부적합(일부 발췌만 읽음).
- **general-purpose**: 복잡한 질문 조사, 코드 검색, 여러 단계로 이뤄진 작업 실행에 쓰는 범용 에이전트. 검색 결과가 확실치 않을 때 이 에이전트로 위임.
- **Plan** — 구현 전략을 설계하는 소프트웨어 아키텍트 에이전트. 단계별 계획, 핵심 파일 식별, 아키텍처 트레이드오프 검토에 사용. 파일 쓰기(Edit/Write)는 하지 않음.
- **statusline-setup** — Claude Code 상태줄(statusline) 설정 전용.

## 아직 확인 안 된 것
- 이 프로젝트 전용 커스텀 서브에이전트(`.claude/agents/*.md`)는 2026-07-21 기준 없음. 새로 만들면 이 문서에 추가할 것.
