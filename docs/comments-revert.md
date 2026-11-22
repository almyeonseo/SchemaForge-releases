# 2. 코멘트 달기 — 행 되돌리기

[목차](README.md) · 이전: [2. 저장과 충돌](comments-save.md) · 다음: [2. Excel에서 붙여넣기](comments-fill.md)

이 장은 SchemaForge 1.13.0 기준이다. MariaDB·MySQL·PostgreSQL·Oracle 연결에서 달라지는 점은 [1.6](getting-started-dbms.md#16-mariadb-연결)~[1.9](getting-started-postgresql-oracle.md#19-oracle-연결)에 모아 두었다.

- **코멘트 저장 위치** ([comments.md](comments.md))
  - [2.1 코멘트는 어디에 저장되나](comments.md#21-코멘트는-어디에-저장되나)
- **편집 화면** ([comments-screen.md](comments-screen.md))
  - [2.2 편집 화면 열기](comments-screen.md#22-편집-화면-열기)
- **값 입력** ([comments-input.md](comments-input.md))
  - [2.3 값 입력하기](comments-input.md#23-값-입력하기)
- **채울 곳만 보기** ([comments-filter.md](comments-filter.md))
  - [2.4 채울 곳만 보기](comments-filter.md#24-채울-곳만-보기)
- **저장과 충돌** ([comments-save.md](comments-save.md))
  - [2.5 저장하기](comments-save.md#25-저장하기)
  - [2.6 저장 충돌](comments-save.md#26-저장-충돌)
- **행 되돌리기**
  - [2.7 행 되돌리기](#27-행-되돌리기)
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

## 2.7 행 되돌리기

잘못 고친 행을 원래 값으로 되돌린다. 다른 행의 편집은 그대로 둔다.

**원래 값**은 그 문서가 **마지막으로 DB에서 읽었거나 저장한 값**이다. 되돌릴 때 DB를 다시 읽지 않는다.
이미 저장한 값을 그 전 값으로 돌릴 때는 이 기능 대신 [2.14절](comments-history.md#214-저장-이력)의 저장 이력을 쓴다.

### 그리드의 행

1. 되돌릴 행을 고른다. 여러 행이면 `Shift`+클릭 등으로 함께 고른다.
2. 고른 행 위에서 오른쪽 클릭 > `원래 값으로 되돌리기`.
3. 고른 행 중 변경된 행이 모두 원래 값으로 돌아간다. 상태줄에 `N개 항목을 원래 값으로 되돌렸습니다.`가 보인다.

- 고르지 않은 행을 오른쪽 클릭하면 그 행을 먼저 고른 뒤 메뉴가 뜬다.
- 고른 행 중 변경된 것이 없으면 메뉴 항목이 꺼져 있다.
- 되돌리면 `변경` 체크가 풀리고 `변경 항목: N개`와 탭의 `●`도 따라 줄어든다.
- 확인 창 없이 화면 안의 값만 바꿀 뿐 DB나 파일에는 쓰지 않는다.
- 분류 목록, 컬럼·인덱스·트리거, 파라미터, 타입 컬럼, 같은 컬럼명 문서 그리드에서 모두 같다.

### 머리글(개체 자신)

개체 문서의 머리글은 **설명 입력칸 오른쪽의 되돌리기 아이콘 버튼**으로 되돌린다. 머리글이 바뀌지 않았으면 버튼이 꺼져 있다.

셀을 입력하는 중에 오른쪽 클릭하면 입력칸 메뉴(잘라내기·복사·붙여넣기)가 뜬다. 되돌리려면 먼저 `Enter`로 입력을 끝낸다.
