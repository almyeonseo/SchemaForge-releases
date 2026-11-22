# 4. SQL 편집기 — 편집 기능

[목차](README.md) · 이전: [4. 결과 저장](sql-editor-save.md) · 다음: [4. 개체와 코멘트 연결](sql-editor-objects.md)

이 장의 단축키는 Windows·Linux 기준으로 적고 괄호에 macOS 키를 붙인다. 전체 표는 [5.2 단축키](settings-shortcuts.md#52-단축키)에 있다.

- **열기** ([sql-editor.md](sql-editor.md))
  - [4.1 열기](sql-editor.md#41-열기)
- **실행하기** ([sql-editor-run.md](sql-editor-run.md))
  - [4.2 실행하기](sql-editor-run.md#42-실행하기)
- **예상 규모** ([sql-editor-estimate.md](sql-editor-estimate.md))
  - [4.3 예상 규모 줄](sql-editor-estimate.md#43-예상-규모-줄)
- **결과 보기** ([sql-editor-results.md](sql-editor-results.md))
  - [4.4 결과 보기](sql-editor-results.md#44-결과-보기)
- **결과 다루기** ([sql-editor-handling.md](sql-editor-handling.md))
  - [4.5 결과 다루기](sql-editor-handling.md#45-결과-다루기)
- **정렬·거르기·열 정리** ([sql-editor-arrange.md](sql-editor-arrange.md))
  - [4.6 정렬·거르기·열 정리](sql-editor-arrange.md#46-정렬거르기열-정리)
- **결과 저장** ([sql-editor-save.md](sql-editor-save.md))
  - [4.7 결과 저장](sql-editor-save.md#47-결과-저장)
- **편집 기능**
  - [4.8 편집 기능](#48-편집-기능)
- **개체와 코멘트 연결** ([sql-editor-objects.md](sql-editor-objects.md))
  - [4.9 개체와 코멘트 연결](sql-editor-objects.md#49-개체와-코멘트-연결)
- **파일로 저장·지난 탭** ([sql-editor-files.md](sql-editor-files.md))
  - [4.10 파일로 저장·지난 탭](sql-editor-files.md#410-파일로-저장지난-탭)
- **MariaDB 연결** ([sql-editor-dbms.md](sql-editor-dbms.md))
  - [4.11 MariaDB 연결](sql-editor-dbms.md#411-mariadb-연결)
- **PostgreSQL 연결** ([sql-editor-postgresql.md](sql-editor-postgresql.md))
  - [4.12 PostgreSQL 연결](sql-editor-postgresql.md#412-postgresql-연결)
- **Oracle 연결** ([sql-editor-oracle.md](sql-editor-oracle.md))
  - [4.13 Oracle 연결](sql-editor-oracle.md#413-oracle-연결)

## 4.8 편집 기능

**편집** 메뉴(SQL 편집기 탭에서만 켜진다)에 아래 기능이 모두 있다. 편집기를 오른쪽 클릭하면 잘라내기·복사·붙여넣기·모두 선택이 있다.

### 찾기·바꾸기

| 동작 | 키 |
|---|---|
| 찾기 | `Ctrl+F`(macOS `Cmd+F`), **편집 > 찾기...** |
| 바꾸기 | `Ctrl+H`(macOS `Cmd+Option+F`), **편집 > 바꾸기...** |
| 다음 / 이전 찾기 | `F3` / `Shift+F3` |
| 다음 바꾸기 / 모두 바꾸기 | 바꾸기 칸에서 `Alt+R` / `Alt+A` |
| 찾기 칸 닫기 | `Esc` |

- 모두 바꾸기는 실행 취소 한 번으로 통째로 되돌아간다.
- 찾기 칸 단추의 툴팁은 영어로 보인다.

### 세로(사각형) 선택

`Alt`를 누른 채 끌면(macOS는 `Control`을 누른 채 끌기) 여러 줄에 걸쳐 같은 열 범위를 고른다.

### 줄로 이동

`Ctrl+G`(macOS `Cmd+G`)나 **편집 > 줄로 이동...**을 누르면 편집기 위에 입력 줄이 열린다. 줄 번호를 넣고 `Enter`나 `이동`을 누른다.

- `128:5`처럼 넣으면 그 줄의 5번째 글자로 간다.
- 커서만 옮기고 줄을 고르지 않는다. 접힌 블록 안이면 펼쳐진다.
- 범위 밖이면 옮기지 않고 입력 줄에 범위가 뜬다. `Esc`로 닫는다.

### 주석 처리·해제

SSMS와 같은 두 번 누르기다.

| 동작 | 키 |
|---|---|
| 주석 처리 | `Ctrl+K` 다음 `Ctrl+C`(macOS `Cmd+K`, `Cmd+C`) |
| 주석 해제 | `Ctrl+K` 다음 `Ctrl+U`(macOS `Cmd+K`, `Cmd+U`) |

- 고른 줄들(고른 것이 없으면 커서가 있는 줄)에 `--`를 붙이거나 뗀다. `--`는 고른 줄 중 가장 얕은 들여쓰기 자리에 붙어 들여쓰기가 흐트러지지 않는다. 빈 줄은 건드리지 않는다.
  MariaDB 연결에서는 `-- `처럼 뒤에 공백을 하나 붙인다. MariaDB는 `--` 뒤에 공백이 있어야 주석으로 읽는다.
- `Ctrl+K`를 누르면 편집기 정보 줄에 `Ctrl+K 눌림 — 두 번째 키 대기 중`이 보인다(macOS는 `Cmd` 표기). 마우스를 누르거나 다른 곳을 누르면 대기가 풀린다. 두 번째 키가 다른 키면 그 키는 평소대로 동작한다.
- 처리한 줄은 선택된 채 남고, 실행 취소 한 번으로 되돌아간다.

### 대소문자 바꾸기

| 동작 | 키 |
|---|---|
| 대문자로 | `Ctrl+Shift+U`(macOS `Cmd+Shift+U`), **편집 > 대문자로** |
| 소문자로 | `Ctrl+Shift+L`(macOS `Cmd+Shift+L`), **편집 > 소문자로** |

- 고른 글자를 그대로 바꾼다. 문자열과 주석 안도 바뀐다.
- 고른 것이 없으면 커서가 있는 단어를 바꾼다.

### 줄 편집

커서 줄이나 고른 줄들에 적용한다. 모두 실행 취소 한 번으로 되돌아간다.

| 동작 | 키 |
|---|---|
| 줄 복제 — 바로 아래에 복사해 넣는다 | `Ctrl+D`(macOS `Cmd+D`) |
| 줄 위로 / 아래로 이동 | `Alt+↑` / `Alt+↓`(macOS `Option+↑` / `Option+↓`) |
| 줄 삭제 — 클립보드는 건드리지 않는다 | `Ctrl+Shift+K`(macOS `Cmd+Shift+K`) |

### 책갈피

긴 스크립트에서 자주 오가는 줄에 단다.

| 동작 | 키 |
|---|---|
| 커서 줄에 넣기·빼기 | `Ctrl+K` 다음 `Ctrl+K`, 또는 줄 번호 왼쪽 칸 클릭 |
| 다음 / 이전 책갈피 | `Ctrl+K` 다음 `Ctrl+N` / `Ctrl+K` 다음 `Ctrl+P` |
| 모두 지우기 | `Ctrl+K` 다음 `Ctrl+L` |

macOS는 `Ctrl`을 `Cmd`로 누른다. **편집** 메뉴에도 `책갈피 넣기/빼기`·`다음 책갈피`·`이전 책갈피`·`책갈피 모두 지우기`가 있다.

- 줄 번호 왼쪽에 파란 리본으로 보이고, 편집기 정보 줄에 `책갈피 N개`가 적힌다.
- 위에 줄을 넣거나 지워도 책갈피가 그 줄을 따라간다.
- 탭을 오가도 남지만 앱을 다시 켜면 남지 않는다.

### 코드 접기

줄 번호 오른쪽의 `−`·`+`를 누르면 블록을 첫 줄만 남기고 접는다. 접힌 자리에는 `N줄 접힘`이 보인다.

| 동작 | 키 |
|---|---|
| 모두 접기 — 가장 바깥 블록만 | `Ctrl+M` 다음 `Ctrl+O`(macOS `Cmd+M`, `Cmd+O`) |
| 모두 펴기 | `Ctrl+M` 다음 `Ctrl+L`(macOS `Cmd+M`, `Cmd+L`) |

- 접는 블록은 `BEGIN … END`(`TRY`·`CATCH` 포함), 여러 줄 블록 주석, `GO`로 나뉜 일괄 처리다.
- **접기는 보이는 것만 바꾼다.** 접힌 줄도 실행·찾기·복사에 그대로 들어간다.
- 탭을 오가도 접힌 채 남지만, 앱을 다시 켜면 모두 펼친 채 열린다.

### 괄호 짝과 같은 낱말 강조

- 커서 바로 앞이나 뒤에 `(`·`)`가 있으면 그 괄호와 짝이 칠해진다. 짝이 없으면 그 괄호만 빨강으로 칠해진다. 문자열·주석 안의 괄호는 세지 않는다.
- `Ctrl+]`(macOS `Cmd+]`)는 짝 괄호로 간다.
- 커서가 놓인 낱말(별칭 `o`, 변수 `@id`, 임시 테이블 `#t`)이 다른 곳에도 나오면 모두 연한 노랑으로 칠해지고, 편집기 정보 줄에 `같은 낱말 N곳`이 적힌다.
  - 대소문자를 가리지 않는다. 키워드·숫자·문자열·주석 안은 칠하지 않는다.
  - 선택 영역이 있으면 칠하지 않는다.
