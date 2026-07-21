# Agents

이 프로젝트에서 Claude Code가 사용할 수 있는 에이전트/서브에이전트 종류와 역할. 라우팅 규칙은 [omc-routing.md](omc-routing.md) 참고.

- **claude** — 특정 유형에 맞지 않는 범용 작업을 처리하는 기본 에이전트.
- **claude-code-guide** — Claude Code CLI, Claude Agent SDK, Claude API, Claude Tag(Slack) 관련 질문 전용. 읽기 전용 도구만 사용.
- **Explore** — 코드 위치를 찾는 읽기 전용 검색 에이전트. 코드 리뷰나 전수 분석에는 부적합.
- **general-purpose** — 복잡한 질문 조사, 코드 검색, 여러 단계 작업 실행에 쓰는 범용 에이전트.
- **Plan** — 구현 전략을 설계하는 아키텍트 에이전트. 파일 쓰기는 하지 않음.
- **statusline-setup** — Claude Code 상태줄 설정 전용.

## 아직 확인 안 된 것
- 이 프로젝트 전용 커스텀 서브에이전트는 2026-07-21 기준 없음.
- 이 폴더(`translate`)의 실제 작업 목적이 아직 정해지지 않아, 목적에 특화된 에이전트가 필요한지 여부도 미확인.
