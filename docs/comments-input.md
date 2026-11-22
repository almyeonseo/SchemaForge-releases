# 2. 코멘트 달기 — 값 입력

[목차](README.md) · 이전: [2. 편집 화면](comments-screen.md) · 다음: [2. 채울 곳만 보기](comments-filter.md)

이 장은 SchemaForge 1.13.0 기준이다. MariaDB·MySQL·PostgreSQL·Oracle 연결에서 달라지는 점은 [1.6](getting-started-dbms.md#16-mariadb-연결)~[1.9](getting-started-postgresql-oracle.md#19-oracle-연결)에 모아 두었다.

- **코멘트 저장 위치** ([comments.md](comments.md))
  - [2.1 코멘트는 어디에 저장되나](comments.md#21-코멘트는-어디에-저장되나)
- **편집 화면** ([comments-screen.md](comments-screen.md))
  - [2.2 편집 화면 열기](comments-screen.md#22-편집-화면-열기)
- **값 입력**
  - [2.3 값 입력하기](#23-값-입력하기)
- **채울 곳만 보기** ([comments-filter.md](comments-filter.md))
  - [2.4 채울 곳만 보기](comments-filter.md#24-채울-곳만-보기)
- **저장과 충돌** ([comments-save.md](comments-save.md))
  - [2.5 저장하기](comments-save.md#25-저장하기)
  - [2.6 저장 충돌](comments-save.md#26-저장-충돌)
- **행 되돌리기** ([comments-revert.md](comments-revert.md))
  - [2.7 행 되돌리기](comments-revert.md#27-행-되돌리기)
- **Excel에서 붙여넣기** ([comments-fill.md](comments-fill.md))
  - [2.8 Excel에서 붙여넣기](comments-fill.md#28-excel에서-붙여넣기)
- **이름 제안** ([comments-suggest.md](comments-suggest.md))
  - [2.9 이름 제안으로 채우기](comments-suggest.md#29-이름-제안으로-채우기)
- **이름 맞추기와 찾아 바꾸기** ([comments-match.md](comments-match.md))
  - [2.10 같은 컬럼명 이름 맞추기](comments-match.md#210-같은-컬럼명-이름-맞추기)
  - [2.11 찾아 바꾸기와 설명 편집](comments-match.md#211-찾아-바꾸기와-설명-편집)
- **작성률** ([comments-review.md](comments-review.md))
  - [2.12 작성률 보기](comments-review.md#212-작성률-보기)
- **다른 DB·파일과 비교** ([comments-compare.md](comments-compare.md))
  - [2.13 다른 DB와 비교해 맞추기](comments-compare.md#213-다른-db와-비교해-맞추기)
- **저장 이력** ([comments-history.md](comments-history.md))
  - [2.14 저장 이력](comments-history.md#214-저장-이력)
- **변경분 스크립트** ([comments-script.md](comments-script.md))
  - [2.15 변경분을 SQL 스크립트로 내보내기](comments-script.md#215-변경분을-sql-스크립트로-내보내기)

## 2.3 값 입력하기

1. 고칠 칸을 한 번 클릭해 고른다.
2. **같은 칸을 한 번 더 클릭하거나 `F2`**를 누르면 입력 상태가 된다. 칸을 고른 채 바로 타이핑해서는 입력이 시작되지 않는다.
3. 입력한 뒤 `Tab`을 누르면 값이 들어가고 옆 칸도 입력 상태로 이어진다. `Enter`는 값을 넣고 아래 행의 같은 칸을 입력 상태로 연다. 이름을 위에서 아래로 이어 채울 때 `F2`를 다시 누르지 않아도 된다. 마지막 행에서는 입력이 끝난다. `Esc`는 편집을 취소하고 편집 전 값으로 돌아간다.

입력하는 중에 `Ctrl+Z`(macOS `Cmd+Z`)를 누르면 **한 글자(음절)씩** 되돌리고 `Ctrl+Y`(macOS `Cmd+Shift+Z`)로 다시 넣는다. 그리드 셀뿐 아니라 검색 칸, 문서 머리글의 입력칸도 같다. macOS에서도 한글이 자모 단위로 되돌아가지 않는다.

**칸 폭은 끌어서 바꾼다.** 칸 머리글 사이의 선을 끌어 처음보다 좁히거나 넓힌다. 칸 폭의 합이 창보다 넓어지면 가로 스크롤바가 생긴다.

편집하면 이렇게 표시된다.

- 그 행의 `변경` 칸에 체크가 생긴다.
- 툴바에 `변경 항목: N개`가 보인다.
- 탭 제목 앞에 `●`가 붙는다.
- 메인 툴바의 **모두 저장** 버튼에 변경이 남은 문서 수가 붙는다. 예: `모두 저장 (2)`

값을 원래대로 고치면 표시도 사라진다. 한 번에 원래 값으로 돌리려면 [2.7절](comments-revert.md#27-행-되돌리기)의 행 되돌리기를 쓴다.

### 지킬 것

- **이름에는 `§`(그 연결의 코멘트 구분자)를 넣을 수 없다.** 이름과 설명을 가르는 문자라서다. 설명에는 넣어도 된다.
- 이름과 설명을 합쳐 **7,500바이트(한글 약 3,750자)**를 넘으면 저장하지 않는다. MariaDB는 한도가 다르고 글자 수로 센다([1.6 MariaDB 연결](getting-started-dbms.md#16-mariadb-연결)).
- 이름과 설명을 모두 비우고 저장하면 그 개체의 코멘트를 지운다.

위반한 값이 있으면 저장을 시작하지 않고 상태줄에 `저장 취소: …`로 어느 항목이 문제인지 알려 준다. 하나라도 걸리면 아무것도 저장하지 않는다.
