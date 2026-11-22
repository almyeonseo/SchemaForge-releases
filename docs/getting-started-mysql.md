# 1. 시작하기 — MySQL 연결

[목차](README.md) · 이전: [1.6 MariaDB 연결](getting-started-dbms.md) · 다음: [1.8 PostgreSQL 연결](getting-started-postgresql-oracle.md)

- [1.1 설치](getting-started.md#11-설치)
- [1.2 화면 구성](getting-started-screen.md#12-화면-구성)
- [1.3 DB 연결 만들기](getting-started-connect.md#13-db-연결-만들기)
- [1.4 DB 탐색기 쓰기](getting-started-explorer.md#14-db-탐색기-쓰기)
- [1.5 연결 정리와 검색](getting-started-search.md#15-연결-정리와-검색)
- [1.6 MariaDB 연결](getting-started-dbms.md#16-mariadb-연결)
- [1.7 MySQL 연결](#17-mysql-연결)
- [1.8 PostgreSQL 연결](getting-started-postgresql-oracle.md#18-postgresql-연결)
- [1.9 Oracle 연결](getting-started-oracle.md#19-oracle-연결)

## 1.7 MySQL 연결

MySQL 8.4에 연결한다. **화면과 동작은 [1.6 MariaDB 연결](getting-started-dbms.md#16-mariadb-연결)과 같다.** 폴더, 읽기만 하는 칸, 저장 방식, 조회 전용 SQL 편집기가 모두 같고
문구의 DBMS 이름만 `MySQL`로 보인다. 다른 점만 적는다.

- **DB 종류**에서 `MySQL`을 고른다. 포트는 `3306`, 기본 이름은 `New MySQL`이 되고 기본 데이터베이스가 필수다.
- MySQL은 서버가 스스로 만든 인증서를 쓰는 일이 많아 처음에는 연결 테스트가 인증서 오류로 실패하기 쉽다. 그때는 `서버 인증서 신뢰`를 켠다.
  오류 문구 끝에도 그 안내가 붙는다.
- 연결 테스트는 붙은 서버의 종류를 본다. 고른 종류와 다르면(예: MySQL을 골랐는데 서버가 MariaDB) `연결 성공. 단, 서버가 MariaDB입니다. DB 종류를 MariaDB로 바꾸세요.`가 보인다.
- 관리자 계정이 만든 프로시저·함수는 일반 계정으로 코멘트를 바꿀 수 없다. 바이너리 로그가 켜진 서버에서 함수 코멘트를 바꾸려면
  `SUPER` 권한이나 서버 설정 `log_bin_trust_function_creators`가 필요하다. 둘 다 권한이 없다는 안내와 함께 멈춘다.
- 컬럼 기본값은 MariaDB와 같은 표기(`'일반'`)로 보인다.
