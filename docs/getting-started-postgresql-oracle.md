# 1. 시작하기 — PostgreSQL 연결

[목차](README.md) · 이전: [1.7 MySQL 연결](getting-started-mysql.md) · 다음: [1.9 Oracle 연결](getting-started-oracle.md)

- [1.1 설치](getting-started.md#11-설치)
- [1.2 화면 구성](getting-started-screen.md#12-화면-구성)
- [1.3 DB 연결 만들기](getting-started-connect.md#13-db-연결-만들기)
- [1.4 DB 탐색기 쓰기](getting-started-explorer.md#14-db-탐색기-쓰기)
- [1.5 연결 정리와 검색](getting-started-search.md#15-연결-정리와-검색)
- [1.6 MariaDB 연결](getting-started-dbms.md#16-mariadb-연결)
- [1.7 MySQL 연결](getting-started-mysql.md#17-mysql-연결)
- [1.8 PostgreSQL 연결](#18-postgresql-연결)
- [1.9 Oracle 연결](getting-started-oracle.md#19-oracle-연결)

## 1.8 PostgreSQL 연결

PostgreSQL 17에 연결한다. 코멘트는 같은 `이름§설명` 형식으로 `COMMENT ON`에 저장한다. 트리와 코멘트 문서는 SQL Server와 같고
SQL 편집기는 MariaDB처럼 기본으로 조회만 한다([4.12](sql-editor-postgresql.md#412-postgresql-연결)).

### 연결 만들기

| 칸 | PostgreSQL에서 |
|---|---|
| 포트 | `5432`가 된다 |
| 기본 데이터베이스 | **필수다** |
| Windows 통합 인증 | 숨는다 |
| 서버 인증서 신뢰 | 끄면 서버 인증서와 호스트 이름을 검증하고, 켜면 검증하지 않고 암호화만 한다 |

- 연결은 늘 암호화한다. 서버에 SSL이 꺼져 있으면 `서버에서 SSL을 켜야 붙습니다. 이 앱은 암호화 없이 연결하지 않습니다.`가 보인다.
- 읽기만 할 때는 그 DB에 접속할 수 있으면 된다. 권한 없는 스키마의 개체와 코멘트도 보인다.
- 코멘트는 **그 개체의 소유자만** 바꿀 수 있다. 다른 계정이 만든 개체는 소유자 계정으로 연결해 저장한다.

### DB 탐색기

- 개체는 SQL Server처럼 `스키마.이름`으로 보인다. `template0`·`template1` DB와 `pg_catalog`·`information_schema` 같은 시스템 스키마는 보이지 않는다.
- 폴더는 `테이블`·`뷰`·`저장 프로시저`·`스칼라 함수`·`테이블 함수`·`복합 타입`이다. 구체화 뷰는 `뷰` 폴더에 함께 들어간다. 파티션 테이블은 부모만 보인다.
- 같은 이름 함수가 여럿일 수 있어 프로시저·함수는 `f(integer)`처럼 인자 형식을 붙인 이름으로 보인다.
- `실행문 만들기`는 프로시저를 `CALL "스키마"."이름"(NULL, …)`로, 함수를 `SELECT "스키마"."이름"(…)`로 채운다.
- `정의 열기`는 뷰·구체화 뷰·프로시저·함수의 본문을 읽기 전용 문서로 연다. 테이블의 `CREATE` 문은 열지 않는다.

### 저장

- SQL Server처럼 편집한 항목 전부를 **한 트랜잭션**으로 저장한다. 하나라도 실패하면 아무것도 반영하지 않고 모든 항목이 변경 표시를 단 채 남는다.
- 파라미터는 코멘트 자리가 없어 읽기만 한다. 제약조건 탭에는 CHECK·FK만 있다.
- 길이 한도는 없다.
- 소유자가 아니면 `개체 소유자만 코멘트를 바꿀 수 있습니다. 아무것도 반영하지 않았습니다`, 다른 작업이 표를 잡고 있으면 10초 뒤
  `다른 작업이 표를 잠가 10초 안에 저장하지 못했습니다`가 보인다.
