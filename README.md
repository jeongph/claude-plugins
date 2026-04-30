# Claude Code Plugins by jeongph

[English](README.en.md)

Claude Code를 위한 플러그인 디렉토리입니다.

> **참고:** 플러그인을 설치하기 전에 각 플러그인의 저장소를 확인하세요. 각 플러그인에 포함된 MCP 서버, 파일, 기타 소프트웨어는 개별 저장소에서 관리됩니다. 자세한 내용은 각 플러그인의 홈페이지를 참조하세요.

## 설치

**1. 마켓플레이스 등록** (최초 1회)

```
/plugin marketplace add jeongph/claude-plugins
```

**2. 플러그인 설치**

```
/plugin install <플러그인명>@jeongph-claude-plugins
```

또는 `/plugin > Discover`에서 탐색할 수 있습니다.

## 플러그인 목록

| 플러그인 | 설명 | 카테고리 |
|----------|------|----------|
| [why-is-my-claude-dumb](#why-is-my-claude-dumb) | 환경 분석 및 플러그인 추천 | productivity |
| [claude-telemetry](#claude-telemetry) | 실시간 세션 텔레메트리 상태바 | productivity |
| [claude-intent](#claude-intent) | 작업 사이클의 의도·대안·트레이드오프 기록 | productivity |
| [pdf-scan-audit](#pdf-scan-audit) | 스캔 PDF 품질 정밀 진단 | utility |
| [pdf-toolkit](#pdf-toolkit) | 범용 PDF 수정 도구 | utility |

---

### why-is-my-claude-dumb

> Why is my Claude so dumb? Let's find out.

로컬 환경(OS·언어·플러그인·MCP·프로젝트 컨텍스트)을 분석하고 공식 마켓플레이스에서 누락된 플러그인을 추천하는 플러그인.

[저장소 →](https://github.com/jeongph/why-is-my-claude-dumb)

---

### claude-telemetry

> Customizable multi-line status line for Claude Code.

남은 컨텍스트, 요청 제한, git 상태, 세션 시간, 토큰 사용량을 컴팩트한 컬러 상태바로 표시하는 플러그인. OAuth/API 키 사용자 자동 감지.

[저장소 →](https://github.com/jeongph/claude-telemetry)

---

### claude-intent

> 코드는 의도의 그림자다.

작업 사이클의 의도·대안·트레이드오프를 `docs/intent/`에 기록하고 코드의 "왜"를 역추적하는 플러그인.

[저장소 →](https://github.com/jeongph/claude-intent)

---

### pdf-scan-audit

> 스캔 PDF의 페이지 누락·순서·회전·잘림·해상도 결함을 자동 검출.

종이책을 스캐너로 읽은 PDF의 품질을 정밀 진단하는 플러그인. 회전 의심·페이지번호 연속성·이미지 잘림까지 검사 후 의심 페이지를 시각 검증해 표로 보고.

[저장소 →](https://github.com/jeongph/pdf-scan-audit)

---

### pdf-toolkit

> 범용 PDF 수정 도구 — 페이지 회전·삭제·순서변경·추출, PDF 병합·분할, 메타데이터 편집.

PyMuPDF 기반의 비파괴 PDF 수정 플러그인. 자연어 또는 슬래시 명령으로 호출, 원본은 항상 보존.

[저장소 →](https://github.com/jeongph/pdf-toolkit)

## 플러그인 구조

각 플러그인은 아래 구조를 따릅니다:

```
plugin-name/
├── .claude-plugin/
│   └── plugin.json      # 플러그인 메타데이터 (필수)
├── .mcp.json            # MCP 서버 설정 (선택)
├── commands/            # 슬래시 커맨드 (선택)
├── agents/              # 에이전트 정의 (선택)
├── skills/              # 스킬 정의 (선택)
└── README.md            # 문서
```

## 문서

Claude Code 플러그인 개발에 대한 자세한 내용은 [공식 문서](https://code.claude.com/docs/en/plugins)를 참조하세요.

## 라이선스

각 플러그인의 라이선스는 해당 저장소를 확인하세요.
