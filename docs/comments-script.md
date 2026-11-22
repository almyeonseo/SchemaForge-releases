# 2. 코멘트 달기 — 변경분 스크립트

[목차](README.md) · 이전: [2. 저장 이력](comments-history.md) · 다음: [3. 파일로 주고받기](import-export.md)

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
- **행 되돌리기** ([comments-revert.md](comments-revert.md))
  - [2.7 행 되돌리기](comments-revert.md#27-행-되돌리기)
- **붙여넣기와 이름 제안** ([comments-fill.md](comments-fill.md))
  - [2.8 Excel에서 붙여넣기](comments-fill.md#28-excel에서-붙여넣기)
  - [2.9 이름 제안으로 채우기](comments-fill.md#29-이름-제안으로-채우기)
- **이름 맞추기와 찾아 바꾸기** ([comments-match.md](comments-match.md))
  - [2.10 같은 컬럼명 이름 맞추기](comments-match.md#210-같은-컬럼명-이름-맞추기)
  - [2.11 찾아 바꾸기와 설명 편집](comments-match.md#211-찾아-바꾸기와-설명-편집)
- **작성률** ([comments-review.md](comments-review.md))
  - [2.12 작성률 보기](comments-review.md#212-작성률-보기)
- **다른 DB·파일과 비교** ([comments-compare.md](comments-compare.md))
  - [2.13 다른 DB와 비교해 맞추기](comments-compare.md#213-다른-db와-비교해-맞추기)
- **저장 이력** ([comments-history.md](comments-history.md))
  - [2.14 저장 이력](comments-history.md#214-저장-이력)
- **변경분 스크립트**
  - [2.15 변경분을 SQL 스크립트로 내보내기](#215-변경분을-sql-스크립트로-내보내기)

## 2.15 변경분을 SQL 스크립트로 내보내기

저장하지 않은 변경을 DB에 쓰지 않고, 코멘트를 바꾸는 SQL 스크립트(`.sql`)로 내보낸다. 운영 DB처럼 직접 저장할 권한이 없는 곳에
DBA가 대신 넣거나, 반영 절차에 스크립트를 첨부할 때 쓴다.

1. 코멘트 문서에서 값을 고친다. 변경이 없으면 버튼이 꺼져 있다.
2. 툴바 `저장` 오른쪽의 스크립트 아이콘(`변경분 스크립트`)을 누르거나 **문서 > 변경분 스크립트...**.
3. 저장 창에서 파일을 고른다. 기본 이름은 `{DB}_{탭 제목}_코멘트변경_{날짜_시각}`이다.
4. 상태줄에 `N건을 스크립트로 내보냈습니다. DB에는 반영하지 않았습니다: {경로}`가 보인다.

- **DB에는 아무것도 쓰지 않고, 그리드의 변경 표시도 그대로 남는다.** 이 DB에도 넣으려면 따로 `저장`을 누른다.
- 담기는 항목과 값은 그 순간 `저장`을 눌렀을 때 보낼 것과 같다. 걸러져 안 보이는 변경도 들어간다.
- 이름의 `§`·길이 한도 검사는 저장과 같다. 걸리면 파일을 만들지 않는다.

MS SQL Server 연결의 스크립트는 이렇게 생겼다.

```sql
-- SchemaForge 코멘트 변경 스크립트
-- 원본: {서버} / {DB}   만든 시각: 2026-10-17 14:30   항목: 1건
-- 대상 DB에서 실행할 것(USE 문을 넣지 않았다). 이전 값은 원본 DB 기준이다.
SET XACT_ABORT ON;
BEGIN TRANSACTION;

-- dbo.CUSTOMER.CUST_NO : 고객번호 → 고객 번호
IF EXISTS (SELECT 1 FROM sys.fn_listextendedproperty(N'MS_Description', N'SCHEMA', N'dbo', N'TABLE', N'CUSTOMER', N'COLUMN', N'CUST_NO'))
    EXEC sys.sp_updateextendedproperty @name = N'MS_Description', @value = N'고객 번호', ...;
ELSE
    EXEC sys.sp_addextendedproperty @name = N'MS_Description', @value = N'고객 번호', ...;

COMMIT TRANSACTION;
```

- **`USE` 문이 없다.** 실행할 도구에서 대상 DB를 고른 뒤 실행한다.
- 실행하는 DB에 속성이 있든 없든 끝까지 돈다. 같은 스크립트를 두 번 돌려도 된다.
- 한 트랜잭션이라 하나라도 실패하면 아무것도 반영되지 않는다.
- **MariaDB 연결에서는 `ALTER` 문으로 나온다.** 문장마다 바로 커밋되어, 중간에 실패하면 그 앞 문장은 이미 반영되어 있다.
- 항목마다 위에 `이전 값 → 새 값` 주석이 붙는다. 이전 값은 이 앱이 읽은 DB 기준이다.
- 연결 문자열과 계정은 파일에 남기지 않는다. 파일은 UTF-8(BOM)이라 SSMS에서 한글이 깨지지 않는다.
- 스크립트 실행은 저장 충돌 확인과 저장 이력을 거치지 않는다. 받는 쪽은 주석의 이전 값과 대상 DB의 지금 값을 견주어 본 뒤 실행한다.
