# 4. SQL 편집기 — 결과 저장

[목차](README.md) · 이전: [4. 정렬·거르기·열 정리](sql-editor-arrange.md) · 다음: [4. 편집 기능](sql-editor-editing.md)

이 장의 단축키는 Windows·Linux 기준으로 적고 괄호에 macOS 키를 붙인다. 전체 표는 [5.2 단축키](shortcuts.md#52-단축키)에 있다.

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
- **결과 저장**
  - [4.7 결과 저장](#47-결과-저장)
- **편집 기능** ([sql-editor-editing.md](sql-editor-editing.md))
  - [4.8 편집 기능](sql-editor-editing.md#48-편집-기능)
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

## 4.7 결과 저장

툴바의 **결과 저장**이나 **문서 > 결과 저장...**은 지금 보고 있는 결과 탭 하나를 파일로 저장한다. 파일 이름이 `.xlsx`로 끝나면 Excel, 그 밖은 CSV다.

- 다른 결과 탭은 함께 저장되지 않는다. 여러 개가 필요하면 탭을 옮겨 다시 저장한다.
- 엑셀 파일에서는 숫자·날짜가 글자가 아니라 숫자·날짜로 들어간다.
- NULL은 파일에서 빈 칸이다.
- 화면에서 거르거나 숨긴 것은 파일에서도 빠지고, 정렬한 순서로 저장된다. 완료 문구에 거른 행 수와 숨긴 열 수가 함께 나온다.
- 결과가 행 상한에 걸려 잘렸으면 파일을 고르기 전에 한 번 묻는다. 파일에는 잘렸다는 표시가 남지 않기 때문이다.
- 실행 전이거나 `메시지` 탭을 보고 있으면 꺼진다.
