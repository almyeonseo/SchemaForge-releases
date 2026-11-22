# 2. 코멘트 달기 — 채울 곳만 보기

[목차](README.md) · 이전: [2. 값 입력](comments-input.md) · 다음: [2. 저장](comments-save.md)

이 장은 SchemaForge 1.13.0 기준이다. MariaDB·MySQL·PostgreSQL·Oracle 연결에서 달라지는 점은 [1.6](getting-started-dbms.md#16-mariadb-연결)~[1.9](getting-started-postgresql-oracle.md#19-oracle-연결)에 모아 두었다.

- **코멘트 저장 위치** ([comments.md](comments.md))
  - [2.1 코멘트는 어디에 저장되나](comments.md#21-코멘트는-어디에-저장되나)
- **편집 화면** ([comments-screen.md](comments-screen.md))
  - [2.2 편집 화면 열기](comments-screen.md#22-편집-화면-열기)
- **값 입력** ([comments-input.md](comments-input.md))
  - [2.3 값 입력하기](comments-input.md#23-값-입력하기)
- **채울 곳만 보기**
  - [2.4 채울 곳만 보기](#24-채울-곳만-보기)
- **저장** ([comments-save.md](comments-save.md))
  - [2.5 저장하기](comments-save.md#25-저장하기)
- **저장 충돌** ([comments-conflict.md](comments-conflict.md))
  - [2.6 저장 충돌](comments-conflict.md#26-저장-충돌)
- **행 되돌리기** ([comments-revert.md](comments-revert.md))
  - [2.7 행 되돌리기](comments-revert.md#27-행-되돌리기)
- **Excel에서 붙여넣기** ([comments-fill.md](comments-fill.md))
  - [2.8 Excel에서 붙여넣기](comments-fill.md#28-excel에서-붙여넣기)
- **이름 제안** ([comments-suggest.md](comments-suggest.md))
  - [2.9 이름 제안으로 채우기](comments-suggest.md#29-이름-제안으로-채우기)
- **같은 컬럼명 이름 맞추기** ([comments-match.md](comments-match.md))
  - [2.10 같은 컬럼명 이름 맞추기](comments-match.md#210-같은-컬럼명-이름-맞추기)
- **찾아 바꾸기와 설명 편집** ([comments-replace.md](comments-replace.md))
  - [2.11 찾아 바꾸기와 설명 편집](comments-replace.md#211-찾아-바꾸기와-설명-편집)
- **작성률** ([comments-review.md](comments-review.md))
  - [2.12 작성률 보기](comments-review.md#212-작성률-보기)
- **다른 DB·파일과 비교** ([comments-compare.md](comments-compare.md))
  - [2.13 다른 DB와 비교해 맞추기](comments-compare.md#213-다른-db와-비교해-맞추기)
- **저장 이력** ([comments-history.md](comments-history.md))
  - [2.14 저장 이력](comments-history.md#214-저장-이력)
- **변경분 스크립트** ([comments-script.md](comments-script.md))
  - [2.15 변경분을 SQL 스크립트로 내보내기](comments-script.md#215-변경분을-sql-스크립트로-내보내기)

## 2.4 채울 곳만 보기

툴바 오른쪽의 세 가지로 보이는 행을 좁힌다.

| 기능 | 쓰는 법 | 남기는 행 |
|---|---|---|
| `미작성만` | 체크를 켜고 끈다 | 이름이 빈 행 |
| `변경만` | 체크를 켜고 끈다 | `변경`이 체크된 행(저장하지 않은 변경이 있는 행) |
| 검색 | 검색 칸에 쓰고 `Enter` 또는 돋보기. `✕`로 지운다 | 검색어가 든 행 |

따로 `F8`을 누르면 거르지 않고 이름이 빈 다음 칸으로 간다(이전은 `Shift+F8`). 탭이 여럿이면 지금 탭 안에서만 움직인다.

- **함께 켜면 모두 만족하는 행만 남는다(AND).** 예: 검색어 `주문` + `미작성만` + `변경만`이면 "`주문`이 들어 있고, 이름이 비었고, 고친 행"만 남는다.
- 검색어는 분류 목록 문서에서는 개체를, 개체 문서에서는 컬럼·파라미터 같은 하위 항목을 거른다. `미작성만`과 `변경만`은 개체와 하위 항목 모두에 걸린다.
- 개체 문서의 머리글(개체 자신)은 거르지 않고 늘 보인다.
- 거르기는 DB를 다시 읽지 않으므로 편집하던 값은 사라지지 않는다.
- 거른 뒤 상태줄에 보이는 수와 전체 수가 나온다. 예: `'주문' 검색 + 미작성만 + 변경만: 3개 / 전체 120개.`
- 걸러져 안 보이는 변경이 있으면 상태줄에 `화면에 보이지 않는 변경 항목 N개도 저장 대상입니다.`가 붙는다. 저장은 화면에 보이는 것과 상관없이 문서 전체의 변경을 저장한다.

### 행이 바로 사라지지 않는 이유

`미작성만`을 켠 뒤 이름을 채워도, `변경만`을 켠 뒤 값을 되돌리거나 저장해도 그 행은 바로 사라지지 않는다.
방금 넣은 값을 확인할 수 있게 하려고 이렇게 했다. 토글이나 검색을 다시 누르면 그때 빠진다.

### 저장 전에 바뀐 것만 확인하기

1. 툴바의 `변경만`을 켠다. 고친 행만 남는다.
2. 행마다 이름·설명을 훑어본다. 잘못 고친 행은 오른쪽 클릭 > `원래 값으로 되돌리기`로 되돌린다([2.7절](comments-revert.md#27-행-되돌리기)).
3. `저장`을 누른다.
4. `변경만`을 다시 눌러 끄면 전체 목록으로 돌아온다.
