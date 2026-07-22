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

플러그인 이름을 클릭하면 저장소로 이동합니다. 설치·사용법·상세 문서는 각 저장소의 README에 있습니다.

| 플러그인 | 설명 | 카테고리 |
|----------|------|----------|
| [claude-intent](https://github.com/jeongph/claude-intent) | 코드는 의도의 그림자다 — 작업 사이클의 의도·대안·트레이드오프를 `docs/intent/`에 기록하고 코드의 "왜"를 역추적 | productivity |
| [claude-mbti](https://github.com/jeongph/claude-mbti) | Claude에게 성격을 준다 🎭 — 16가지 MBTI 성격(말투+행동 성향)을 주입, `/mbti`로 켜고 끄고 전환 | fun |
| [claude-okf](https://github.com/jeongph/claude-okf) | 코드는 무엇을, 위키는 왜를 기억한다 — OKF 기반 LLM-wiki 자동 활성화. 노드 초안 생성·자동 검증·lint·grounded 답변 | productivity |
| [claude-telemetry](https://github.com/jeongph/claude-telemetry) | 남은 컨텍스트·요청 제한·effort·git 상태·토큰 사용량을 컴팩트한 컬러 상태바로 표시 | productivity |
| [claude-tidy](https://github.com/jeongph/claude-tidy) | 컨텍스트가 사라지면 빠뜨렸다는 사실도 사라진다 — 세션 마무리 정리(커밋·히스토리·문서·이슈·잊힌 작업 검사)와 핸드오프 | productivity |
| [git-flow](https://github.com/jeongph/git-flow) | 실수는 브랜치를 만들 때가 아니라 끝낼 때 난다 — Git Flow 브랜치 모델을 PR 기반으로 자동화하고 위반을 차단 | productivity |
| [pdf-scan-audit](https://github.com/jeongph/pdf-scan-audit) | 스캔 PDF의 페이지 누락·순서·회전·잘림·해상도 결함을 자동 검출하고 표로 보고 | utility |
| [pdf-toolkit](https://github.com/jeongph/pdf-toolkit) | 범용 PDF 수정 도구 — 회전·삭제·순서변경·추출·병합·분할·메타데이터 편집을 비파괴 방식으로 | utility |
| [why-is-my-claude-dumb](https://github.com/jeongph/why-is-my-claude-dumb) | Why is my Claude so dumb? Let's find out — 로컬 환경을 분석해 공식 마켓플레이스의 누락 플러그인을 추천 | productivity |

## 기여

플러그인을 추가하거나 수정할 때 무엇을 어디에 반영해야 하는지는 [CONTRIBUTING.md](CONTRIBUTING.md)를 따릅니다.

## 라이선스

각 플러그인의 라이선스는 해당 저장소를 확인하세요.
