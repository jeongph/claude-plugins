# 기여 가이드

이 저장소는 **카탈로그**다. 플러그인의 코드와 문서는 각 플러그인 저장소에 있고, 여기에는 마켓플레이스 정의와 목록만 둔다.

## 경계

| 이 저장소 (claude-plugins) | 각 플러그인 저장소 |
|---|---|
| 마켓플레이스 정의 (`.claude-plugin/marketplace.json`) | 플러그인 manifest (`.claude-plugin/plugin.json`) |
| 목록 표 (`README.md` · `README.en.md`) | 코드 (`skills/`·`hooks/`·`agents/`) |
| 마켓플레이스 설치 안내 | 설치·사용법·옵션·예시 (`README.md`) |

**상세를 여기 복제하지 않는다.** 사용법·명령 목록·설정 옵션은 각 플러그인 저장소의 README가 단일 진실(SSOT)이다. 복제하면 한쪽만 고쳐져 어긋난다. 이 저장소의 목록 표는 *어떤 플러그인이 있고 어디로 가면 되는지*까지만 담는다.

---

## 새 플러그인 추가

### 1. 플러그인 저장소 준비

플러그인 저장소가 **public**이고 `main`에 푸시되어 있어야 한다. 마켓플레이스는 URL과 커밋 SHA로 참조한다.

```sh
claude plugin validate .    # 플러그인 저장소에서 실행
```

### 2. marketplace.json 등록

`.claude-plugin/marketplace.json`의 `plugins` 배열 끝에 추가한다.

```json
{
  "name": "<플러그인명>",
  "description": "<한 줄 설명>",
  "source": {
    "source": "url",
    "url": "https://github.com/jeongph/<플러그인명>.git",
    "sha": "<원격 HEAD SHA>"
  }
}
```

`name`은 플러그인의 `plugin.json`의 `name`과 **반드시 일치**해야 한다. 이 값이 설치 이름(`<name>@jeongph-claude-plugins`)이자 호출 네임스페이스(`/<name>:<skill>`)가 된다.

초기 SHA는 실제 원격 HEAD를 넣는다.

```sh
git ls-remote https://github.com/jeongph/<플러그인명>.git HEAD | cut -f1
```

### 3. README 두 곳 갱신

`README.md`(한글)와 `README.en.md`(영문)의 목록 표에 각각 한 행씩 추가한다. **한쪽만 고치지 않는다.**

```markdown
| [<플러그인명>](https://github.com/jeongph/<플러그인명>) | <캐치프레이즈> — <기능 요약> | <카테고리> |
```

- **행은 플러그인명 알파벳 순으로 정렬한다.** 끝에 붙이지 않는다
- 링크는 저장소로 직접 건다 (페이지 내 앵커 아님)
- 카테고리는 `productivity` · `utility` · `fun` 중 하나. 새 카테고리는 꼭 필요할 때만 만든다

### 4. 검증·커밋·푸시

```sh
claude plugin validate .
```

```sh
git add .claude-plugin/marketplace.json README.md README.en.md
git commit -m "feat: <플러그인명> 플러그인 등록"
git pull --rebase origin main    # CI 자동 커밋 위로 얹는다 (아래 참조)
git push origin main
```

`pull --rebase`는 **커밋한 뒤에** 실행한다. 미커밋 변경이 남아 있으면 rebase가 거부된다.

---

## 기존 플러그인 수정

### description 변경

**두 곳을 함께 고친다.**

1. 이 저장소의 `marketplace.json`
2. 플러그인 저장소의 `plugin.json`

두 값은 자동 동기화되지 않는다. 한쪽만 고치면 마켓플레이스와 플러그인 관리자의 설명이 어긋난다.

README 표의 설명도 함께 볼 것. 세 곳이 같은 대상을 가리킨다.

### SHA 변경

**건드리지 않는다.** CI가 자동으로 갱신한다 (아래 참조).

즉시 반영이 필요하면 워크플로를 수동 실행하거나(`workflow_dispatch`), 직접 수정한다.

### 플러그인 제거

`marketplace.json` 항목과 README 두 곳의 행을 함께 지운다.

---

## 자동화 (CI)

`.github/workflows/sync-plugins.yml`

- **주기**: 매일 KST 00:00 (`cron: 0 15 * * *`). `workflow_dispatch`로 수동 실행 가능
- **동작**: `marketplace.json`의 각 항목에 대해 `git ls-remote <url> HEAD`로 최신 SHA를 조회해 갱신
- **범위**: `source.sha` **만** 갱신한다. `name`·`description`·`url`은 사람이 관리한다
- **커밋**: 변경이 있으면 `chore: 플러그인 SHA 자동 갱신`으로 자동 커밋·푸시

**커밋한 뒤 push 전에 `git pull --rebase`를 습관화한다.** CI가 이 저장소에 직접 커밋하므로, 로컬이 뒤처져 있으면 push가 거부된다. 대개 다른 항목의 SHA만 바뀌어 충돌 없이 리베이스된다.

플러그인 저장소에 커밋을 푸시하면 다음 자정에 SHA가 자동으로 따라온다. 즉 **플러그인 코드를 고친 뒤 이 저장소를 손댈 필요는 없다.**

---

## 규칙

- 표는 **플러그인명 알파벳 순**
- README는 **한글·영문 쌍으로** 갱신
- 상세 문서는 각 플러그인 저장소에 둔다 (여기에 복제 금지)
- 커밋 메시지는 한글 + [Conventional Commits](https://www.conventionalcommits.org/ko/v1.0.0/) 접두어
  - `feat:` 플러그인 등록·제거
  - `docs:` README·이 문서 수정
  - `chore:` SHA·설정
- 브랜치는 `main` 하나를 쓴다
