# 4. SQL 편집기 — 결과 다루기

[목차](README.md) · 이전: [4. 결과 보기](sql-editor-results.md) · 다음: [4. 정렬·거르기·열 정리](sql-editor-arrange.md)

이 장의 단축키는 Windows·Linux 기준으로 적고 괄호에 macOS 키를 붙인다. 전체 표는 [5.2 단축키](settings-shortcuts.md#52-단축키)에 있다.

- **열기** ([sql-editor.md](sql-editor.md))
  - [4.1 열기](sql-editor.md#41-열기)
- **실행하기** ([sql-editor-run.md](sql-editor-run.md))
  - [4.2 실행하기](sql-editor-run.md#42-실행하기)
- **예상 규모** ([sql-editor-estimate.md](sql-editor-estimate.md))
  - [4.3 예상 규모 줄](sql-editor-estimate.md#43-예상-규모-줄)
- **결과 보기** ([sql-editor-results.md](sql-editor-results.md))
  - [4.4 결과 보기](sql-editor-results.md#44-결과-보기)
- **결과 다루기**
  - [4.5 결과 다루기](#45-결과-다루기)
- **정렬·거르기·열 정리** ([sql-editor-arrange.md](sql-editor-arrange.md))
  - [4.6 정렬·거르기·열 정리](sql-editor-arrange.md#46-정렬거르기열-정리)
- **결과 저장** ([sql-editor-save.md](sql-editor-save.md))
  - [4.7 결과 저장](sql-editor-save.md#47-결과-저장)
- **편집 기능** ([sql-editor-editing.md](sql-editor-editing.md))
  - [4.8 편집 기능](sql-editor-editing.md#48-편집-기능)
- **개체와 코멘트 연결** ([sql-editor-objects.md](sql-editor-objects.md))
  - [4.9 개체와 코멘트 연결](sql-editor-objects.md#49-개체와-코멘트-연결)
- **파일로 저장·지난 탭** ([sql-editor-files.md](sql-editor-files.md))
  - [4.10 파일로 저장·지난 탭](sql-editor-files.md#410-파일로-저장지난-탭)
- **DBMS별 차이** ([sql-editor-dbms.md](sql-editor-dbms.md))
  - [4.11 MariaDB 연결](sql-editor-dbms.md#411-mariadb-연결)
  - [4.12 PostgreSQL 연결](sql-editor-dbms.md#412-postgresql-연결)
  - [4.13 Oracle 연결](sql-editor-dbms.md#413-oracle-연결)

## 4.5 결과 다루기

결과 표는 읽기 전용이다. 값을 고치지는 않지만 받은 결과를 다시 실행하지 않고도 화면에서 고르고 늘어놓고 거르고 꺼낼 수 있다.

### 셀 고르기

SSMS·엑셀처럼 셀 단위로 고른다.

| 조작 | 고르는 범위 |
|---|---|
| 셀 클릭 | 그 셀 하나 |
| `Ctrl`+클릭(macOS `Cmd`+클릭) | 셀을 더하거나, 이미 고른 셀이면 뺀다 |
| `Shift`+클릭, 끌기 | 기준 셀부터 사각형 |
| 왼쪽 순번 클릭 / 끌기 | 줄 전체 / 여러 줄 |
| 위쪽 열 이름 클릭 | 열 전체 |
| 왼쪽 위 모서리 클릭, `Ctrl+A`(macOS `Cmd+A`) | 전체 |
| 방향키, `Home`·`End`, `PageUp`·`PageDown` | 현재 셀을 옮긴다. `Shift`를 함께 누르면 사각형으로 늘린다 |

- 끌다가 그리드 밖으로 나가면 그 방향으로 굴리며 선택을 늘린다.
- 고른 셀이 걸친 순번과 열 이름도 칠해진다.

### 복사

| 방법 | 복사되는 것 |
|---|---|
| `Ctrl+C`(macOS `Cmd+C`), 오른쪽 클릭 `복사` | 고른 셀을 탭으로 나눈 줄들로 |
| `Ctrl+Shift+C`(macOS `Cmd+Shift+C`), 오른쪽 클릭 `머리글과 함께 복사` | 위와 같고 맨 위에 열 이름 줄을 붙인다 |
| 오른쪽 클릭 `IN 목록으로 복사` | 고른 값을 `(값, 값, …)`로. `WHERE X IN ` 뒤에 그대로 붙인다 |
| 열 이름 오른쪽 클릭 `열 이름 복사` | 열 이름들을 `[Id], [Order Date], [Status]`처럼 쉼표로 이어서(MariaDB 연결은 역따옴표로 감싼다) |

- 고른 셀이 떨어져 있으면 그 셀들이 걸친 줄과 열의 사각형으로 복사하고, 고르지 않은 칸은 빈칸이다.
- 값은 화면 표기 그대로이고 NULL은 `NULL`이다. 값에 탭·줄바꿈·큰따옴표가 있을 때만 큰따옴표로 감싸, 엑셀에 붙여 넣어도 칸이 밀리지 않는다.
- `IN 목록으로 복사`는 SQL 리터럴로 바꾼다 — 숫자는 그대로, 문자열은 `N'…'`(MariaDB 연결은 `'…'`), 날짜는 `'2024-03-02T13:05:09.120'`, bit는 `1`/`0`. NULL과 중복 값은 빼고, 뺀 개수를 상태바에 알린다.
- `열 이름 복사`는 열을 골라 두고 그 안의 열 이름을 오른쪽 클릭하면 고른 칸만, 아니면 모든 칸이다. 이름은 모두 `[ ]`로 감싼다(MariaDB 탭은 역따옴표).
- 고른 곳을 오른쪽 클릭하면 선택을 그대로 두고, 고르지 않은 곳을 오른쪽 클릭하면 그곳만 고른다.

### 값 보기

셀을 더블클릭하거나 `Shift+Enter`, 오른쪽 클릭 `값 보기`로 그 값을 따로 창에 연다. 칸 폭에서 잘린 긴 문자열이나 여러 줄 정의는 이 창에서 본다.

- 줄바꿈을 살린 원문을 고정폭 글꼴로 보인다. `줄 바꿈`을 끄면 가로로 스크롤한다.
- 제목에 열 이름과 순번, 그 아래에 글자 수·줄 수가 적힌다.
- 읽기 전용이다. 일부를 골라 복사하거나 `복사`로 전체를 복사한다.

### 행 세로로 보기

셀을 오른쪽 클릭해 `행 세로로 보기`를 고르거나 `Alt+Enter`(macOS `Option+Enter`)를 누르면 그 행을 `열 이름 | 값`으로 펼친 창이 열린다. 칸이 수십 개인 테이블의 한 행을 읽을 때 쓴다.

- `이전 행`·`다음 행` 단추나 `PageUp`·`PageDown`으로 행을 옮긴다. 행 순서는 화면 순서(정렬·거르기 뒤)를 따른다.
- `열 이름 찾기`에 글자를 넣으면 이름에 그 글자가 든 칸만 남는다.
- 값을 더블클릭하면 값 보기 창이 열린다. `Ctrl+C`(macOS `Cmd+C`)는 고른 줄을 `열 이름 ⇥ 값`으로 복사한다.
- 숨긴 열도 여기서는 보인다. `Esc`로 닫는다.

### 결과에서 찾기

결과 그리드에 포커스를 두고 `Ctrl+F`(macOS `Cmd+F`)를 누르면 그리드 위에 `결과에서 찾기` 줄이 열린다. 편집기에서 누르면 편집기 찾기다.

- 치는 대로 찾아 첫 셀을 고른다. `Enter`·`F3`은 다음, `Shift`를 더하면 이전이다. 끝에 닿으면 반대쪽 끝으로 돌아간다.
- 몇 번째인지 `3 / 27개`처럼 표시된다. `대소문자 구분`·`셀 전체 일치`를 켤 수 있다.
- 화면 표기로 찾는다. NULL은 `NULL`로 찾는다.
- `Esc`나 `닫기`로 닫는다. 찾은 셀은 선택된 채 남아 바로 복사할 수 있다.
