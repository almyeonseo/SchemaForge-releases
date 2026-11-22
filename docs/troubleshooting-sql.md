# 6. 문제 해결 — SQL 편집기

[목차](README.md) · 이전: [6. 코멘트 입력과 저장](troubleshooting-editing.md) · 다음: [6. 업데이트](troubleshooting-info.md)

- **설치와 연결** ([troubleshooting.md](troubleshooting.md))
  - [6.1 설치와 연결](troubleshooting.md#61-설치와-연결)
- **DB 탐색기** ([troubleshooting-explorer.md](troubleshooting-explorer.md))
  - [6.2 DB 탐색기](troubleshooting-explorer.md#62-db-탐색기)
- **코멘트 입력과 저장** ([troubleshooting-editing.md](troubleshooting-editing.md))
  - [6.3 코멘트 입력과 저장](troubleshooting-editing.md#63-코멘트-입력과-저장)
- **SQL 편집기**
  - [6.4 SQL 편집기](#64-sql-편집기)
- **업데이트** ([troubleshooting-info.md](troubleshooting-info.md))
  - [6.5 업데이트](troubleshooting-info.md#65-업데이트)
- **데이터 저장 위치** ([troubleshooting-data.md](troubleshooting-data.md))
  - [6.6 데이터 저장 위치](troubleshooting-data.md#66-데이터-저장-위치)
- **오류 로그** ([troubleshooting-log.md](troubleshooting-log.md))
  - [6.7 오류 로그](troubleshooting-log.md#67-오류-로그)
- **지원하지 않는 것** ([troubleshooting-unsupported.md](troubleshooting-unsupported.md))
  - [6.8 지원하지 않는 것](troubleshooting-unsupported.md#68-지원하지-않는-것)
- **문의·버그 제보** ([troubleshooting-contact.md](troubleshooting-contact.md))
  - [6.9 문의·버그 제보](troubleshooting-contact.md#69-문의버그-제보)

## 6.4 SQL 편집기

**`Ctrl+N`(macOS `Cmd+N`, 새 쿼리)을 눌러도 아무 일이 없다.**
DB 탐색기에서 연결이나 그 아래 노드(DB·폴더·개체)를 먼저 골라야 한다. 상태바에 안내가 뜬다. `Ctrl+O`(macOS `Cmd+O`), 정의서 내보내기도 같다.
새 쿼리는 고른 노드의 DB에 붙는다(연결을 골랐으면 기본 DB).

**`F5`를 눌렀더니 쿼리가 아니라 트리가 새로고쳐졌다.**
포커스가 DB 탐색기에 있었다. 편집기를 한 번 클릭한 뒤 누르거나 `Ctrl+Enter`(macOS `Cmd+Enter`)를 쓴다.

**MariaDB SQL 편집기에서 `조회 전용 연결이라 쓰기·DDL·CALL은 실행하지 않았습니다.`가 뜬다.**
MariaDB 탭은 기본으로 조회만 한다. 쓰려면 탭 툴바의 `쓰기 허용`을 켜고 다시 실행한다. DDL과 `COMMIT`은 그 앞까지 바로 반영되니 확인하고 실행한다([4.11](sql-editor-dbms.md#411-mariadb-연결)).

**Oracle SQL 편집기에서 `조회 전용 연결이라 쓰기·DDL·COMMIT은 실행하지 않았습니다.`가 뜬다.**
Oracle 탭은 기본으로 조회만 한다. 쓰려면 탭 툴바의 `쓰기 허용`을 켜고 다시 실행한다.

**`상위 1000개 행 선택`을 눌렀는데 결과가 없다.**
조회문을 새 탭에 채우기만 하고 실행하지 않는다. `F5`나 `Ctrl+Enter`(macOS `Cmd+Enter`)로 실행한다.

**`GO 5`가 들어 있다며 실행되지 않는다.**
`GO` 뒤의 반복 횟수는 지원하지 않는다. 숫자를 지우고 실행한다. `GO`만 있는 줄은 그대로 쓸 수 있다([4.2](sql-editor-run.md#42-실행하기)).

**`ALTER DATABASE`·`BACKUP` 같은 문장이 실패한다.**
트랜잭션 안에서 쓸 수 없는 문장이다. 이 편집기는 실행 전체를 트랜잭션으로 감싸므로 실행할 수 없다. SSMS 같은 도구를 쓴다.

**예상 규모 줄이 늘 `알 수 없습니다`이거나 `조사를 멈췄습니다`라고 나온다.**
DB 접근 게이트웨이(중계 프로그램)를 거치는 연결은 실행 계획 조사를 받지 않는 경우가 있다. 앱은 한 번 실패하면 앱을 끌 때까지
그 연결에 다시 묻지 않는다. 실행에는 영향이 없다. 이런 연결에서는 실행이 실패했을 때 되돌려졌는지 가릴 수 없는 경우가 있다. 그때는 오류 아래에 `실패하기 전에 트랜잭션이 이미 끝나 있었습니다. … 데이터를 확인하세요.`가 나온다.

**SQL 결과가 중간에서 끊긴다.**
설정에 행 상한이 걸려 있다(기본은 무제한). 표 아래에 `· 더 있음`이 붙어 있으면 잘린 것이다. 조건을 좁히거나 설정에서 상한을 올린다.

**큰 테이블을 조회했더니 앱이 멈춘 것 같다.**
기본은 모든 행을 받는다. **중단**(`Ctrl+.`, macOS `Cmd+.`)으로 멈추고, `TOP`이나 조건으로 좁히거나 설정에서 행 상한을 건다.
