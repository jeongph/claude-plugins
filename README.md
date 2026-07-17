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
| [claude-okf](#claude-okf) | OKF 기반 LLM-wiki 자동 활성화 | productivity |
| [git-flow](#git-flow) | Git Flow 브랜치 모델 PR 기반 자동화 | productivity |
| [pdf-scan-audit](#pdf-scan-audit) | 스캔 PDF 품질 정밀 진단 | utility |
| [pdf-toolkit](#pdf-toolkit) | 범용 PDF 수정 도구 | utility |
| [claude-mbti](#claude-mbti) | Claude에게 MBTI 성격 주입 | fun |

---

### why-is-my-claude-dumb

> Why is my Claude so dumb? Let's find out.

로컬 환경(OS·언어·플러그인·MCP·프로젝트 컨텍스트)을 분석하고 공식 마켓플레이스에서 누락된 플러그인을 추천하는 플러그인.

[저장소 →](https://github.com/jeongph/why-is-my-claude-dumb)

---

### claude-telemetry

> Customizable multi-line status line for Claude Code.

남은 컨텍스트, 요청 제한, effort 레벨, git 상태·PR 뱃지, 세션 시간, 토큰 사용량을 컴팩트한 컬러 상태바로 표시하는 플러그인. OAuth/API 키 자동 감지, 바이너리 자동 동기화, 제거 시 자가 정리.

[저장소 →](https://github.com/jeongph/claude-telemetry)

---

### claude-intent

> 코드는 의도의 그림자다.

작업 사이클의 의도·대안·트레이드오프를 `docs/intent/`에 기록하고 코드의 "왜"를 역추적하는 플러그인.

[저장소 →](https://github.com/jeongph/claude-intent)

---

### claude-okf

> 코드는 무엇을, 위키는 왜를 기억한다.

OKF(Open Knowledge Format) 기반 LLM-wiki를 자동 활성화하는 플러그인. 코드에서 지식 노드 초안 생성(enrichment), 노드 작성 시 자동 검증·`index` 갱신, 모순·stale·orphan 점검(lint), 위키 기반 grounded 답변(ask). Karpathy의 LLM-wiki 패턴과 OKF 표준 포맷을 융합.

[저장소 →](https://github.com/jeongph/claude-okf)

---

### git-flow

> 실수는 브랜치를 만들 때가 아니라 끝낼 때 난다.

Git Flow 브랜치 모델을 PR 기반으로 자동화하는 플러그인. 올바른 분기점에서 브랜치를 만들고(`/git-flow:feature`·`release`·`hotfix`), 마지막 태그 이후 커밋을 Conventional Commits로 분석해 다음 버전을 계산하며, 완료 절차를 멱등적으로 한 단계씩 진행한다(`/git-flow:finish`). 훅이 `main` 직접 커밋·`--squash` 머지·`develop`발 hotfix 분기·비-`main` 태그를 차단한다. 아카이브된 `git flow` CLI와 달리 로컬 직접 머지가 아닌 PR 경로로 동작.

[저장소 →](https://github.com/jeongph/git-flow)

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

---

### claude-mbti

> Claude에게 성격을 준다. 🎭

Claude Code 세션에 16가지 MBTI 성격(**말투 + 행동 성향**)을 주입하는 플러그인. `/mbti intj`로 켜면 이후 모든 응답이 해당 유형의 말투·성향을 따르고, `/mbti off`로 평소 Claude로 복귀한다. 정답의 정확성·안전·프로젝트 컨벤션은 성격과 무관하게 항상 유지된다.

**설치**

```
/plugin marketplace add jeongph/claude-plugins
/plugin install claude-mbti@jeongph-claude-plugins
```

**사용법**

| 명령 | 동작 |
|------|------|
| `/mbti intj` | 해당 유형으로 성격 켜기 (16개 유형 지원) |
| `/mbti off` | 성격 해제 (평소 Claude 복귀) |
| `/mbti` | 현재 활성 유형 확인 |
| `/mbti list` | 16개 유형 목록 |
| `/mbti random` | 무작위 유형 배정 |

**라이선스:** MIT

[저장소 →](https://github.com/jeongph/claude-mbti)

## 라이선스

각 플러그인의 라이선스는 해당 저장소를 확인하세요.
