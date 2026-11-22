# 4. SQL 편집기 — 예상 규모

[목차](README.md) · 이전: [4. 실행하기](sql-editor-run.md) · 다음: [4. 결과 보기](sql-editor-results.md)

이 장의 단축키는 Windows·Linux 기준으로 적고 괄호에 macOS 키를 붙인다. 전체 표는 [5.2 단축키](settings-shortcuts.md#52-단축키)에 있다.

- **열기** ([sql-editor.md](sql-editor.md))
  - [4.1 열기](sql-editor.md#41-열기)
- **실행하기** ([sql-editor-run.md](sql-editor-run.md))
  - [4.2 실행하기](sql-editor-run.md#42-실행하기)
- **예상 규모**
  - [4.3 예상 규모 줄](#43-예상-규모-줄)
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
- **PostgreSQL 연결** ([sql-editor-postgresql.md](sql-editor-postgresql.md))
  - [4.12 PostgreSQL 연결](sql-editor-postgresql.md#412-postgresql-연결)
- **Oracle 연결** ([sql-editor-oracle.md](sql-editor-oracle.md))
  - [4.13 Oracle 연결](sql-editor-oracle.md#413-oracle-연결)

## 4.3 예상 규모 줄

툴바 바로 아래 줄은 실행하기 전에 무슨 일이 일어날지 알려 준다. 툴바 `규모 확인`, `Ctrl+L`(macOS `Cmd+L`), 문서 메뉴
`규모 확인`을 누르면 서버에 실행 계획만 물어볼 뿐 실제로 실행하지는 않는다. 입력하는 동안에는 서버에 묻지 않는다.

| 표시 | 뜻 |
|---|---|
| `예상 규모: SQL을 입력한 뒤 규모 확인으로 조사합니다.` | 아직 아무것도 입력하지 않았다 |
| `예상 규모를 확인하지 않았습니다 — 규모 확인(Ctrl+L)` | SQL이나 선택이 바뀐 뒤 아직 확인하지 않았다. 확인하지 않고도 실행할 수 있다 |
| `규모 확인 중...` | 조사하는 중 |
| `예상 규모: 약 32,000행 변경 · 약 10행 조회 (추정값)` | 실행 계획으로 추정한 행 수. 바꾸는 문장과 조회 문장을 나눠 적는다. 실제와 다를 수 있다 |
| `… · 일부 일괄 처리는 알 수 없음 (추정값)` | `GO`로 나뉜 스크립트에서 앞 부분이 만드는 개체를 쓰는 부분은 미리 알 수 없다 |
| `예상 규모를 알 수 없습니다` | 동적 SQL이거나 계정에 `SHOWPLAN` 권한이 없다. 0행이라는 뜻이 아니다 |
| `구문 오류(줄 3, 오류 번호 102): …` | 실행하기 전에 찾은 오타 |

- 선택 영역이 있으면 문구 앞에 `선택 영역 ·`이 붙고, 선택한 부분만 추정한다. 선택을 바꾸면 옛 숫자를 지우고 `확인하지 않았습니다`로 바뀐다.
  이미 확인한 범위로 돌아오면(선택을 풀거나 같은 범위를 다시 고르면) 그 결과를 다시 보인다. 실행이 끝나면 결과를 버린다.
- 실행 중에는 `규모 확인`이 꺼진다.
- 행 수가 많아도 실행을 막지 않는다.
- **MariaDB 연결에는 규모 확인이 없다.** `규모 확인`이 꺼져 있고, 이 줄에는 `조회 전용 — 쓰기·DDL·CALL은 서버가 막습니다.`가 늘 보인다.
  `쓰기 허용`을 켜면 `쓰기 허용 — DDL·COMMIT이 있으면 그 앞까지 바로 반영됩니다`로 바뀐다.
- 계획 조사를 받지 않는 연결(DB 접근 게이트웨이 등)에서는 한 번 실패하면 조사를 멈췄다고 적는다. 그 뒤로는 앱을 끌 때까지 다시 묻지 않는다.
