# Claude Code Plugins by jeongph

[English](README.en.md)

직접 만들어 사용하는 Claude Code 플러그인을 모았습니다.

각 플러그인의 기능, 설치 방법, 필요한 도구는 아래 저장소 링크에서 확인할 수 있습니다.

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
| [agentic-devflow](https://github.com/jeongph/agentic-devflow) | GitHub 이슈를 바탕으로 구현, 리뷰, PR 생성을 진행합니다. 중단된 작업도 이어서 진행할 수 있습니다. | productivity |
| [claude-intent](https://github.com/jeongph/claude-intent) | 코드를 왜 이렇게 작성했는지, 어떤 대안을 검토했는지 기록하고 나중에 찾아볼 수 있습니다. | productivity |
| [claude-mbti](https://github.com/jeongph/claude-mbti) | Claude의 말투와 행동 성향을 16가지 MBTI 유형 중 하나로 설정합니다. | fun |
| [claude-telemetry](https://github.com/jeongph/claude-telemetry) | 남은 컨텍스트와 사용 한도, 추론 수준, Git 상태, 토큰 수를 터미널 하단에 표시합니다. | productivity |
| [claude-tidy](https://github.com/jeongph/claude-tidy) | 작업을 마칠 때 빠진 커밋, 문서, 이슈 처리를 확인하고 다음 세션에 넘길 내용을 정리합니다. | productivity |
| [claude-wiki](https://github.com/jeongph/claude-wiki) | 코드와 문서를 바탕으로 위키를 작성하고, 내용을 점검하거나 위키에서 답을 찾습니다. | productivity |
| [git-flow](https://github.com/jeongph/git-flow) | Git Flow에 따라 브랜치를 만들고 PR로 병합합니다. 잘못된 분기나 태그 생성도 확인합니다. | productivity |
| [pdf-scan-audit](https://github.com/jeongph/pdf-scan-audit) | 스캔한 PDF에서 빠진 페이지, 잘못된 순서와 회전, 잘림, 해상도 문제를 찾아 결과를 정리합니다. | utility |
| [pdf-toolkit](https://github.com/jeongph/pdf-toolkit) | PDF 페이지를 회전하거나 삭제하고, 문서를 합치거나 나눕니다. 기본적으로 원본은 그대로 둡니다. | utility |
| [why-is-my-claude-dumb](https://github.com/jeongph/why-is-my-claude-dumb) | 개발 환경과 설치된 도구를 살펴보고, 작업에 도움이 될 공식 마켓플레이스 플러그인을 추천합니다. | productivity |

## 기여

플러그인을 추가하거나 수정할 때 무엇을 어디에 반영해야 하는지는 [CONTRIBUTING.md](CONTRIBUTING.md)를 따릅니다.

## 라이선스

각 플러그인의 라이선스는 해당 저장소를 확인하세요.
