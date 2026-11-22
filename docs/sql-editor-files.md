# 4. SQL 편집기 — 파일로 저장·지난 탭

[목차](README.md) · 이전: [4. 개체와 코멘트 연결](sql-editor-objects.md) · 다음: [4. MariaDB 연결](sql-editor-dbms.md)

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
- **파일로 저장·지난 탭**
  - [4.10 파일로 저장·지난 탭](#410-파일로-저장지난-탭)
- **MariaDB 연결** ([sql-editor-dbms.md](sql-editor-dbms.md))
  - [4.11 MariaDB 연결](sql-editor-dbms.md#411-mariadb-연결)
- **PostgreSQL 연결** ([sql-editor-postgresql.md](sql-editor-postgresql.md))
  - [4.12 PostgreSQL 연결](sql-editor-postgresql.md#412-postgresql-연결)
- **Oracle 연결** ([sql-editor-oracle.md](sql-editor-oracle.md))
  - [4.13 Oracle 연결](sql-editor-oracle.md#413-oracle-연결)

## 4.10 파일로 저장·지난 탭

- SQL 편집기 탭에서 `Ctrl+S`(macOS `Cmd+S`)는 DB가 아니라 **`.sql` 파일로 저장**한다. 파일로 연 탭은 그 파일에 덮어쓰고, 새 탭은 처음 저장할 때 저장할 곳을 묻는다(기본 이름 `SQLQuery1.sql`).
- 저장하다 디스크가 차거나 오류가 나도 원래 파일은 그대로 남는다. 새 내용을 다 쓴 뒤에 바꿔 넣기 때문이다.
- 다른 이름으로 저장하려면 **파일 > 다른 이름으로 저장...**을 쓴다. 저장하면 탭이 새 파일을 가리킨다.
- 예전 SSMS가 저장한 한글 ANSI(CP949) 파일도 깨지지 않고 열리고, 연 인코딩 그대로 저장한다. 새 파일은 UTF-8(BOM 포함)로 저장한다. 저장될 형식은 편집기 정보 줄 오른쪽에 보인다.
- 저장하지 않은 채 탭이나 앱을 닫으면 저장할지 묻는다.
- 실행 중인 탭을 닫으려 하면 `중단하고 닫기 / 취소`를 묻는다. 중단하면 그 실행은 되돌려진다.

### 지난 탭 다시 열기

앱을 다시 켜면 지난번에 열려 있던 SQL 편집기 탭을 다시 연다. [설정](settings-shortcuts.md#51-설정)의 `앱을 켤 때 지난번 SQL 편집기 탭 다시 열기`로 끄고 켠다(기본은 켬).

- **파일로 저장한 탭만** 다시 연다. 본문은 파일에서 다시 읽고, 연결·커서 위치·탭 순서·마지막으로 보던 탭을 되살린다.
- 저장하지 않은 새 탭은 다시 열리지 않는다.
- 다시 열어도 실행하지 않고 결과도 되살리지 않는다.
- 연결 프로필이 지워졌거나 파일을 읽지 못하면 그 탭은 열지 않고 출력 창에 `[탭 복원]`으로 이유를 남긴다.
- 코멘트 문서 탭은 다시 열지 않는다.
