# 2. 코멘트 달기 — 이름 제안

[목차](README.md) · 이전: [2. Excel에서 붙여넣기](comments-fill.md) · 다음: [2. 같은 컬럼명 이름 맞추기](comments-match.md)

이 장은 SchemaForge 1.13.0 기준이다. MariaDB·MySQL·PostgreSQL·Oracle 연결에서 달라지는 점은 [1.6](getting-started-dbms.md#16-mariadb-연결)~[1.9](getting-started-oracle.md#19-oracle-연결)에 모아 두었다.

- **코멘트 저장 위치** ([comments.md](comments.md))
  - [2.1 코멘트는 어디에 저장되나](comments.md#21-코멘트는-어디에-저장되나)
- **편집 화면** ([comments-screen.md](comments-screen.md))
  - [2.2 편집 화면 열기](comments-screen.md#22-편집-화면-열기)
- **값 입력** ([comments-input.md](comments-input.md))
  - [2.3 값 입력하기](comments-input.md#23-값-입력하기)
- **채울 곳만 보기** ([comments-filter.md](comments-filter.md))
  - [2.4 채울 곳만 보기](comments-filter.md#24-채울-곳만-보기)
- **저장** ([comments-save.md](comments-save.md))
  - [2.5 저장하기](comments-save.md#25-저장하기)
- **저장 충돌** ([comments-conflict.md](comments-conflict.md))
  - [2.6 저장 충돌](comments-conflict.md#26-저장-충돌)
- **행 되돌리기** ([comments-revert.md](comments-revert.md))
  - [2.7 행 되돌리기](comments-revert.md#27-행-되돌리기)
- **Excel에서 붙여넣기** ([comments-fill.md](comments-fill.md))
  - [2.8 Excel에서 붙여넣기](comments-fill.md#28-excel에서-붙여넣기)
- **이름 제안**
  - [2.9 이름 제안으로 채우기](#29-이름-제안으로-채우기)
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

## 2.9 이름 제안으로 채우기

빈 컬럼을 채울 때 다른 테이블의 같은 컬럼명이 이미 쓰는 이름(`CUST_NO` = `고객번호`)을 제안해, 같은 이름을 다시 치지 않게 한다.
테이블·뷰 문서의 컬럼 탭, 프로시저·함수 문서의 파라미터 그리드, 테이블 타입 문서의 컬럼 그리드, 테이블 문서의 `인덱스`·`제약조건` 탭에서 된다.

1. 제안이 있는 빈 행이 보이면 그리드 위에 `빈 이름 N개에 이름 제안이 있습니다.`와 `제안으로 채우기` 버튼이 나온다.
2. `제안으로 채우기`를 누르면 **보이는 행 중 이름이 빈 행에만** 제안이 들어간다. 검색·필터로 숨은 행은 바꾸지 않는다.
3. 들어간 행은 `변경`으로 표시된다. `변경만`을 켜서 확인하고, 아니다 싶은 행은 [되돌린다](comments-revert.md#27-행-되돌리기).
4. `저장`을 눌러야 DB에 반영된다.

어떤 값을 제안하나:

- 그 DB의 다른 테이블에서 이름이 같은 컬럼에 **가장 많이 쓰인 이름**이다. 같은 수면 가나다순으로 앞의 것이다. 뷰 컬럼과 이 개체 자신의 컬럼은 세지 않는다.
- **뷰 문서는 뷰 컬럼마다 실제로 가져오는 원본 테이블 컬럼을 찾아 그 이름을 먼저 제안한다.** 이름을 바꾼 컬럼(`o.Id AS OrderId`)도 원본을 따라간다.
  원본이 없거나(식으로 만든 컬럼) 원본에 이름이 없으면 같은 컬럼명 제안을 쓴다.
- **프로시저·함수의 파라미터는 앞의 `@`를 뺀 이름으로 맞춘다**(`@CUST_NO` ↔ `CUST_NO`). 맞는 테이블 컬럼이 없으면 다른 프로시저·함수의
  같은 파라미터명에 가장 많이 쓰인 이름을 제안한다.
- **테이블 컬럼은 외래키가 가리키는 컬럼의 이름을 먼저 제안한다.** 외래키가 없거나 가리키는 컬럼에 이름이 없으면 같은 컬럼명 제안을 쓴다.
- **테이블 타입의 컬럼도** 같은 컬럼명의 이름을 제안한다.
- **인덱스·제약조건 탭은 키 컬럼의 이름으로 지은 이름을 제안한다**(`주문일자 인덱스`, `고객 참조` 등). FK는 참조 테이블, DEFAULT는 대상 컬럼의 이름을 쓴다.
- 설명은 제안하지 않는다.
- 제안은 문서를 열 때 한 번 읽는다. 다른 문서에서 저장한 이름은 `새로고침`해야 제안에 반영된다.
