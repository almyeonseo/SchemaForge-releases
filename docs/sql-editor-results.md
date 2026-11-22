# 4. SQL 편집기 — 결과 보기

[목차](README.md) · 이전: [4. 예상 규모](sql-editor-estimate.md) · 다음: [4. 결과 다루기](sql-editor-handling.md)

이 장의 단축키는 Windows·Linux 기준으로 적고 괄호에 macOS 키를 붙인다. 전체 표는 [5.2 단축키](shortcuts.md#52-단축키)에 있다.

- **열기** ([sql-editor.md](sql-editor.md))
  - [4.1 열기](sql-editor.md#41-열기)
- **실행하기** ([sql-editor-run.md](sql-editor-run.md))
  - [4.2 실행하기](sql-editor-run.md#42-실행하기)
- **예상 규모** ([sql-editor-estimate.md](sql-editor-estimate.md))
  - [4.3 예상 규모 줄](sql-editor-estimate.md#43-예상-규모-줄)
- **결과 보기**
  - [4.4 결과 보기](#44-결과-보기)
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

## 4.4 결과 보기

- 결과 집합이 여럿이면 `결과 1`, `결과 2` 탭으로 나뉜다. 실행이 끝나면 결과 탭으로 넘어간다. 결과가 없는 문장(`UPDATE`, `CREATE TABLE`)은 `메시지` 탭만 생긴다.
- 결과 탭에 마우스를 올리면 그 실행의 정보가 보인다: 행·칸 수, 받은 시각과 걸린 시간, DB(서버), 실행한 SQL 앞부분.
- 왼쪽 행 머리글에 1부터 시작하는 순번이 있다. 순번은 복사와 결과 저장에 들어가지 않는다.
- NULL은 흐린 기울임꼴 `NULL`로 보인다. 빈 문자열(`''`)은 빈칸이다.
- 바이너리는 `0x…` 16진수로 보인다. 화면에는 앞 64바이트만 보이고, 복사·값 보기·결과 저장은 자르지 않는다.
- 숫자 타입 칸(`int`, `decimal`, `money`, `float` 등)은 값이 오른쪽에 붙는다. 글자 타입의 숫자 코드(`00123`)는 왼쪽이다.
- 열 이름에 마우스를 올리면 타입과 NULL 허용 여부(`decimal(18,2) · NULL 허용`), 몇 번째 칸인지가 뜬다.
- 기본으로 **모든 행을** 보여 준다. 수백만 행짜리 테이블을 통째로 조회하면 앱이 멈추거나 메모리 부족으로 꺼질 수 있으니, 그럴 때는 **중단**으로 멈춘다.
  [설정](settings-shortcuts.md#51-설정)에서 행 상한을 걸면 그만큼만 보여 주고, 더 있으면 표 아래에 `상위 N행 표시 · 더 있음`이 적힌다.
- 행 상한을 걸지 않아도 한 번의 실행이 받는 결과에는 한도가 있다.
  - 결과 집합은 100개까지 받는다. 넘으면 `메시지` 탭에 `결과 집합이 100개를 넘어 나머지 N개는 받지 않았습니다. SQL은 끝까지 실행되었습니다.`가 나온다.
  - 받은 결과가 500MB를 넘으면 거기서 자르고 `받은 결과가 크기 상한(500MB)을 넘어 일부 결과가 잘렸습니다. 칸을 줄이거나 조건을 좁혀 다시 실행하세요.`가 나온다.
- 실행 시간 제한도 기본은 없다. 설정에서 걸면 그 시간을 넘긴 실행은 멈추고 되돌린다.

### `메시지` 탭

- 맨 위에 서버 메시지가 온 순서대로 나온다. 문장마다의 `(N행 영향)`과 `PRINT` 출력이다. 그 아래에 합계·걸린 시간·커밋 여부가 온다.
- 조회 문장의 행 수는 행 상한에 걸려 잘려도 실제 전체 행 수다.
- `SET NOCOUNT ON`이면 행 수 줄은 오지 않는다.
- 메시지가 1,000건을 넘으면 앞뒤 500건씩만 남기고 가운데는 `… 중간 메시지 N건 생략 …` 한 줄로 줄인다.

### 결과 탭 고정

결과 탭을 오른쪽 클릭해 `탭 고정`을 고르면 다음 실행이 그 탭을 바꾸지 않는다. `UPDATE` 전과 후의 결과를 탭을 오가며 견주려면 이렇게 한다.

- 고정한 탭의 이름은 `고정 · 결과 · 14:03:12`처럼 결과를 받은 시각이 붙는다.
- 다시 실행하면 고정한 탭은 그대로 두고 새 결과를 그 오른쪽에 연다. 실행이 오류로 끝나거나 중단돼도 남는다.
- 고정한 탭만 닫을 수 있다(탭의 ×, 오른쪽 클릭 `닫기`). `고정 해제`를 고르면 다음 실행이 그 탭을 바꾼다.
- `메시지` 탭은 고정하지 않는다. 앱을 다시 켜면 고정한 탭은 남지 않는다.
