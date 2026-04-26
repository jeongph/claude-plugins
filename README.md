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
| [pdf-scan-audit](#pdf-scan-audit) | 스캔 PDF 품질 정밀 진단 | utility |

---

### why-is-my-claude-dumb

> Why is my Claude so dumb? Let's find out.

로컬 환경(OS, 언어, 설치된 플러그인, MCP 서버, 프로젝트 컨텍스트)을 분석하고, 워크플로우에 맞는 공식 마켓플레이스 플러그인을 추천합니다.

```
/plugin install why-is-my-claude-dumb@jeongph-claude-plugins
```

#### 기능

- **환경 분석** — OS, 설치된 런타임, Claude Code 설정, MCP 서버를 스캔
- **맞춤 추천** — 공식 카탈로그(80+ 플러그인)에서 누락된 플러그인을 찾아 추천
- **자동 트리거** — Claude에 불만을 표현하면 `dumb-doctor` 에이전트가 자동으로 환경 점검을 제안
- **원클릭 설치** — 추천된 플러그인을 대화 중 바로 설치

#### 분석 항목

| 항목 | 상세 |
|------|------|
| 시스템 | OS, 플랫폼, 아키텍처 |
| 언어 | Node, Python, Java, Go, Rust 등 설치된 런타임 |
| 플러그인 | 설치된 플러그인 vs. 공식 카탈로그 |
| 설정 | Claude Code 설정, hooks, 권한 |
| 통합 | 연결된 MCP 서버 |
| 프로젝트 | 프로젝트 타입, CLAUDE.md 유무 |

[저장소 →](https://github.com/jeongph/why-is-my-claude-dumb)

---

### claude-telemetry

> Customizable multi-line status line for Claude Code.

남은 컨텍스트 윈도우, 요청 제한, git 상태, 세션 시간, 토큰 사용량 등을 컴팩트한 컬러 상태바로 표시합니다. OAuth/API 키 사용자를 자동 감지합니다.

```
/plugin install claude-telemetry@jeongph-claude-plugins
```

#### 기능

- **잔량 표시** — 모든 바가 사용량이 아닌 잔량을 표시 (배터리처럼)
- **자동 사용자 감지** — OAuth 사용자는 요청 제한, API 키 사용자는 비용 표시
- **Git 통합** — 브랜치, push/pull, 변경사항, stash, worktree 표시
- **컬러 코딩** — 잔량에 따라 초록 → 노랑 → 빨강 자동 전환
- **적응형 너비** — 터미널 폭에 맞춰 자동 조절
- **다국어** — 영어, 한국어, 일본어, 중국어 자동 감지

#### 표시 항목

| 라인 | 항목 |
|------|------|
| 1 | 모델명, 경과 시간, git (브랜치, push/pull, 변경사항, stash, worktree) |
| 2 | 컨텍스트 잔량 %, 요청 제한 카운트다운, 비용, 변경 라인 수 |
| 3 | 활성 에이전트, vim 모드 (데이터 있을 때만 표시) |

[저장소 →](https://github.com/jeongph/claude-telemetry)

---

### pdf-scan-audit

> 스캔 PDF의 페이지 누락·순서·회전·잘림·해상도 결함을 자동 검출.

종이책을 스캐너로 읽은 PDF의 품질을 정밀 진단합니다. 메타데이터만 훑지 않고, 회전 의심·페이지번호 연속성·이미지 잘림까지 검사한 뒤 의심 페이지만 골라 시각 검증해 가독성 좋은 표로 보고합니다.

```
/plugin install pdf-scan-audit@jeongph-claude-plugins
```

#### 기능

- **페이지 메타 검사** — 크기 분포, 회전, 방향, DPI 일관성 확인
- **빈 페이지·잘림 검출** — 텍스트·이미지 모두 없는 페이지, 페이지 경계 밖으로 잘린 이미지 검출
- **회전 의심 자동 추출** — 텍스트 줄 종횡비로 회전 페이지 추정 후 시각 검증
- **페이지번호 연속성 분석** — 헤더/푸터에서 추출한 시퀀스로 누락·중복 검출, OCR 오인식 자동 분류
- **PDF↔책 페이지 오프셋 자동 추정** — 본문 시작 위치 자동 감지
- **임시 디렉토리 자동 정리** — 작업 디렉토리에 흔적 남기지 않음

#### 검사 항목

| 항목 | 상세 |
|------|------|
| 페이지 메타 | 크기 분포·회전·portrait/landscape 방향 |
| 해상도(DPI) | 페이지별 임베디드 이미지 기준 DPI 추정 |
| 빈 페이지 | 이미지·텍스트 모두 거의 없는 페이지 |
| 회전 의심 | 텍스트 줄 종횡비 기반 추정 + 시각 검증 |
| 페이지번호 연속성 | 헤더/푸터 시퀀스의 갭 분석, OCR 오인식 자동 분류 |
| 의심 페이지 시각 검증 | PNG 추출 후 Claude가 직접 보고 판정 |

#### 사용 예

```
이 PDF 스캔 검사해줘
/audit-pdf book1.pdf book2.pdf
```

#### 의존성

- Python 3.8+
- PyMuPDF (`pip install pymupdf`)

[저장소 →](https://github.com/jeongph/pdf-scan-audit)

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
