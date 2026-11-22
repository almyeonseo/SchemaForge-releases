# 6. 문제 해결 — 지원하지 않는 것

[목차](README.md) · 이전: [6.7 오류 로그](troubleshooting-log.md) · 다음: [6.9 문의·버그 제보](troubleshooting-contact.md)

- [6.1 설치와 연결](troubleshooting.md#61-설치와-연결)
- [6.2 DB 탐색기](troubleshooting-explorer.md#62-db-탐색기)
- [6.3 코멘트 입력과 저장](troubleshooting-editing.md#63-코멘트-입력과-저장)
- [6.4 SQL 편집기](troubleshooting-sql.md#64-sql-편집기)
- [6.5 업데이트](troubleshooting-info.md#65-업데이트)
- [6.6 데이터 저장 위치](troubleshooting-data.md#66-데이터-저장-위치)
- [6.7 오류 로그](troubleshooting-log.md#67-오류-로그)
- [6.8 지원하지 않는 것](#68-지원하지-않는-것)
- [6.9 문의·버그 제보](troubleshooting-contact.md#69-문의버그-제보)

## 6.8 지원하지 않는 것

- MS SQL Server·MariaDB·MySQL·PostgreSQL·Oracle 이외의 DBMS
- MariaDB·MySQL 인덱스·STORED 계산 컬럼 코멘트 저장(읽기만 한다), MariaDB·MySQL 제약조건·뷰·트리거 코멘트
- Oracle 인덱스·프로시저·함수 코멘트(코멘트 자리가 없어 읽기만 한다), Oracle 패키지 안의 프로시저·함수, Oracle 테이블의 `CREATE` 문 열기
- PostgreSQL 파라미터 코멘트(읽기만 한다), PostgreSQL 테이블의 `CREATE` 문 열기
- 서로 다른 종류의 DB 사이 코멘트 비교(같은 종류끼리만 비교한다)
- 테이블·컬럼 자체를 만들거나 바꾸는 일 (코멘트만 다룬다)
- 다른 사람의 편집을 막는 잠금 (저장할 때 충돌을 알려 주는 데까지만)
- 여러 사람의 변경 이력을 함께 보기. 저장 이력은 이 PC에서 이 앱으로 저장한 것만 남는다
- 저장 이력 화면에서 곧바로 DB 값을 되돌리기. 이전 값을 복사해 코멘트 문서에 붙여넣고 저장한다
- 여러 DB를 한 번에 검색하기
- 이름에 `§` 넣기
