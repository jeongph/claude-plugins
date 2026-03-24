# jeongph/claude-plugins

[@jeongph](https://github.com/jeongph)의 Claude Code 플러그인 통합 마켓플레이스.

하나의 마켓플레이스로 모든 플러그인을 설치할 수 있습니다.

## 시작하기

**1. 마켓플레이스 등록**

```
/plugin marketplace add jeongph/claude-plugins
```

**2. 원하는 플러그인 설치**

```
/plugin install <플러그인명>@jeongph-claude-plugins
```

끝. 플러그인마다 별도의 마켓플레이스를 등록할 필요 없습니다.

## 플러그인 목록

### why-is-my-claude-dumb

> 당신의 Claude Code에 부족한 플러그인이 있을지도 모릅니다.

로컬 환경(OS, 언어, 설치된 플러그인, MCP 서버, 프로젝트 컨텍스트)을 분석하고, 워크플로우에 맞는 공식 마켓플레이스 플러그인을 추천합니다. Claude에 불만을 표현하면 자동으로 트리거되기도 합니다.

```
/plugin install why-is-my-claude-dumb@jeongph-claude-plugins
```

**사용법:**

```
/why-is-my-claude-dumb:why-dumb
```

| 분석 항목 | 상세 |
|-----------|------|
| 시스템 | OS, 플랫폼, 아키텍처 |
| 언어 | Node, Python, Java, Go, Rust 등 |
| 플러그인 | 설치된 플러그인 vs. 공식 카탈로그 |
| 설정 | Claude Code 설정, hooks, 권한 |
| 통합 | 연결된 MCP 서버 |
| 프로젝트 | 프로젝트 타입, CLAUDE.md 유무 |

[레포 보기 →](https://github.com/jeongph/why-is-my-claude-dumb)

---

### claude-telemetry

> Claude Code 전용 커스터마이징 가능한 멀티라인 상태바 — 실시간 세션 텔레메트리.

남은 컨텍스트 윈도우, 요청 제한, git 상태, 세션 시간, 토큰 사용량 등을 컴팩트한 컬러 상태바로 표시합니다. OAuth/API 키 사용자를 자동 감지합니다.

```
/plugin install claude-telemetry@jeongph-claude-plugins
```

**사용법:**

```
/claude-telemetry:setup
```

| 라인 | 표시 항목 |
|------|-----------|
| 1 | 모델명, 경과 시간, git (브랜치, push/pull, 변경사항, stash, worktree) |
| 2 | 컨텍스트 잔량 %, 요청 제한 카운트다운, 비용, 변경 라인 수 |
| 3 | 활성 에이전트, vim 모드 |

[레포 보기 →](https://github.com/jeongph/claude-telemetry)

## 왜 통합 마켓플레이스인가?

Claude Code 플러그인은 마켓플레이스를 통해 설치됩니다. 이 레포가 없으면 각 플러그인마다 마켓플레이스를 개별 등록해야 합니다:

```
# 통합 마켓플레이스 없이 (플러그인별 등록)
/plugin marketplace add jeongph/why-is-my-claude-dumb
/plugin marketplace add jeongph/claude-telemetry
/plugin install why-is-my-claude-dumb@jeongph-why-is-my-claude-dumb
/plugin install claude-telemetry@jeongph-claude-telemetry
```

```
# 통합 마켓플레이스 사용 (한 번만 등록)
/plugin marketplace add jeongph/claude-plugins
/plugin install why-is-my-claude-dumb@jeongph-claude-plugins
/plugin install claude-telemetry@jeongph-claude-plugins
```

마켓플레이스는 한 번만 등록하면 됩니다. 이후 어떤 플러그인이든 바로 설치하세요.

## 라이선스

[MIT](LICENSE)
