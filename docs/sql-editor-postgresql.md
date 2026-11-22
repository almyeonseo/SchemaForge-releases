# 4. SQL 편집기 — PostgreSQL 연결

[목차](README.md) · 이전: [4. MariaDB 연결](sql-editor-dbms.md) · 다음: [4. Oracle 연결](sql-editor-oracle.md)

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
- **편집 기능** ([sql-editor-editing.md](sql-editor-editing.md))
  - [4.8 편집 기능](sql-editor-editing.md#48-편집-기능)
- **개체와 코멘트 연결** ([sql-editor-objects.md](sql-editor-objects.md))
  - [4.9 개체와 코멘트 연결](sql-editor-objects.md#49-개체와-코멘트-연결)
- **파일로 저장·지난 탭** ([sql-editor-files.md](sql-editor-files.md))
  - [4.10 파일로 저장·지난 탭](sql-editor-files.md#410-파일로-저장지난-탭)
- **MariaDB 연결** ([sql-editor-dbms.md](sql-editor-dbms.md))
  - [4.11 MariaDB 연결](sql-editor-dbms.md#411-mariadb-연결)
- **PostgreSQL 연결**
  - [4.12 PostgreSQL 연결](#412-postgresql-연결)
- **Oracle 연결** ([sql-editor-oracle.md](sql-editor-oracle.md))
  - [4.13 Oracle 연결](sql-editor-oracle.md#413-oracle-연결)

## 4.12 PostgreSQL 연결

PostgreSQL 연결에서도 같은 편집기를 쓴다. 기본은 [4.11](sql-editor-dbms.md#411-mariadb-연결)처럼 조회만 한다. 다른 점만 적는다.

- 조회 전용 탭에서 쓰기·DDL·`COMMENT`는 서버가 거부하고 `조회 전용 연결이라 쓰기·DDL·COMMENT는 실행하지 않았습니다.`가 보인다.
- `쓰기 허용`을 켜면 SQL 전체를 트랜잭션으로 감싸 성공하면 커밋, 실패하면 **DDL까지 모두 되돌린다.** SQL 안의 `COMMIT`·`ROLLBACK`이 트랜잭션을 끝냈으면 그 사실을 알린다.
- `VACUUM`·`CREATE INDEX CONCURRENTLY`처럼 트랜잭션 안에서 쓸 수 없는 문장은 실행하지 않는다.
- 이름은 큰따옴표(`"스키마"."표"`)로 감싸고, `$$ … $$`·`$body$ … $body$`는 함수 본문 문자열이다. 구문 강조와 괄호 짝이 이 규칙을 따른다.
- `;`로 이은 여러 문장을 한 번에 보낸다. 오류가 난 줄은 칠하지 않는다.
- 드라이버가 읽지 못하는 형식(`regclass` 등)은 그 칸만 `::text로 바꿔 조회하세요`라는 안내로 채운다. 배열은 `{1,2}`로 보인다.
- `상위 1000개 행 선택 ▸ 모든 컬럼 (*)`은 `SELECT * FROM "스키마"."표" LIMIT 1000;`을 채운다.
