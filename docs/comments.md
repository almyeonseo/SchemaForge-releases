# 2. 코멘트 달기

[목차](README.md) · 이전: [1. Oracle 연결](getting-started-oracle.md) · 다음: [2. 편집 화면](comments-screen.md)

이 장은 SchemaForge 1.13.0 기준이다. MariaDB·MySQL·PostgreSQL·Oracle 연결에서 달라지는 점은 [1.6](getting-started-dbms.md#16-mariadb-연결)~[1.9](getting-started-oracle.md#19-oracle-연결)에 모아 두었다.

- **코멘트 저장 위치**
  - [2.1 코멘트는 어디에 저장되나](#21-코멘트는-어디에-저장되나)
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

## 2.1 코멘트는 어디에 저장되나

SchemaForge는 개체마다 **이름**과 **설명**을 받아 코멘트 값 하나에 `§`로 이어 붙여 저장한다.
저장하는 자리는 DBMS가 원래 코멘트를 두는 곳이다. MS SQL Server는 `MS_Description` 확장 속성이고 MariaDB·MySQL은 개체의 `COMMENT`, PostgreSQL·Oracle은 `COMMENT ON`이다.

```
주문내역§고객이 주문한 상품의 내역을 보관하는 테이블
└ 이름 ┘└──────────── 설명 ────────────────────┘
```

다른 DB 도구에서 그 개체의 코멘트를 보면 이 모양 그대로 보인다. 같은 DB를 쓰는 기존 프로그램과 맞추려고 정한 형식이다.

### 구분자 바꾸기

`§`는 기본값이다. 이 DB가 `|`·`::` 같은 다른 구분자로 코멘트를 관리해 왔으면, 연결 편집에서 `코멘트 구분자`를 그 글자로 바꾼다.
그 연결로 여는 모든 화면(트리, 코멘트 문서, 작성률, 같은 컬럼명 문서, 정의서, SQL 편집기)이 그 구분자로 읽고 저장한다.

- 1~3글자이고 공백·글자·숫자는 쓸 수 없다. 쓸 수 없는 값이면 연결 창의 `저장`이 꺼지고 이유가 보인다.
- 연결마다 따로 정한다. `§` DB와 `|` DB를 오가도 다시 바꿀 필요가 없다.
- 이미 저장된 값을 새 구분자로 바꿔 주지는 않는다. 구분자 설정은 읽고 쓰는 방식만 바꾼다.
- [다른 DB와 비교](comments-compare.md#213-다른-db와-비교해-맞추기)는 두 DB를 각자 연결의 구분자로 읽는다. `§` DB의 값을 `|` DB에 맞춰 넣을 수 있다.

**구분자가 맞지 않아 보이면 알린다.** 코멘트 문서를 열었는데 설명이 있는 값이 하나도 없고 이름 안에 다른 구분자가 자주 보이면,
문서 맨 위에 `이 DB의 코멘트는 '|'로 나뉜 것으로 보입니다. 연결 설정의 구분자('§')를 확인하세요.`가 나온다.
그 상태로 저장하면 `이 DB는 '|' 형식으로 보입니다. '§'로 나눠 저장할까요?`를 한 번 더 묻는다. 취소하면 아무것도 쓰지 않고 편집은 남는다.
잘못된 구분자로 저장하면 값이 다른 형식으로 굳기 때문이다.

다룰 수 있는 개체는 DBMS마다 다르다.

- **MS SQL Server** — 테이블, 컬럼, 뷰, 뷰 컬럼, 저장 프로시저, 스칼라·테이블 함수, 파라미터, 인덱스,
  트리거, 제약조건(CHECK·DEFAULT·FK), 사용자 정의 테이블 타입과 그 컬럼.
- **MariaDB** — 테이블, 컬럼, 프로시저, 함수. 인덱스·파라미터와 `STORED` 계산 컬럼의 코멘트는 읽기만 한다.

형식(`이름§설명`)과 구분자를 바꾸는 법은 두 DBMS가 같다.
