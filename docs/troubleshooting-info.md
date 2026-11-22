# 6. 문제 해결 — 업데이트·데이터·문의

[목차](README.md) · 이전: [6. SQL 편집기](troubleshooting-sql.md)

- **설치와 연결** ([troubleshooting.md](troubleshooting.md))
  - [6.1 설치와 연결](troubleshooting.md#61-설치와-연결)
- **DB 탐색기** ([troubleshooting-explorer.md](troubleshooting-explorer.md))
  - [6.2 DB 탐색기](troubleshooting-explorer.md#62-db-탐색기)
- **코멘트 입력과 저장** ([troubleshooting-editing.md](troubleshooting-editing.md))
  - [6.3 코멘트 입력과 저장](troubleshooting-editing.md#63-코멘트-입력과-저장)
- **SQL 편집기** ([troubleshooting-sql.md](troubleshooting-sql.md))
  - [6.4 SQL 편집기](troubleshooting-sql.md#64-sql-편집기)
- **업데이트·데이터·문의**
  - [6.5 업데이트](#65-업데이트)
  - [6.6 데이터 저장 위치](#66-데이터-저장-위치)
  - [6.7 오류 로그](#67-오류-로그)
  - [6.8 지원하지 않는 것](#68-지원하지-않는-것)
  - [6.9 문의·버그 제보](#69-문의버그-제보)

## 6.5 업데이트

앱을 켤 때 새 버전이 있는지 확인하고, 있으면 상태바에 링크가 나타난다. **도움말 > 업데이트 확인**으로
직접 확인할 수도 있다. 켤 때 확인하지 않으려면 설정에서 끈다([5장](settings-shortcuts.md)). 자동으로 내려받지는 않으므로 링크에서 새 파일을 받아 설치한다.

Windows 설치판은 새 setup.exe를 실행하면 덮어 설치된다. 연결 프로필과 저장된 비밀번호는 그대로 남는다.

## 6.6 데이터 저장 위치

연결 프로필(연결 순서 포함), 설정, 정의서 표제부, 최근 쿼리 파일 목록, 저장 이력은 아래 폴더의 `SchemaForge.db` 한 파일에 있다.

| OS | 폴더 |
|---|---|
| Windows | 사용자 AppData(Roaming) 폴더 아래 `SchemaForge` |
| macOS | `~/Library/Application Support/SchemaForge` (Finder에서 `Cmd+Shift+G`로 이 경로를 넣는다) |
| Linux | `~/.config/SchemaForge` |

비밀번호는 AES-256-GCM으로 암호화하고 키는 설치마다 무작위로 만들어 DB 파일 옆에 둔다. DB 파일만
실수로 새어 나갔을 때 비밀번호가 그대로 보이지 않게 하는 수준이다. 이 PC의 파일에 접근할 수 있는 사람은
키 파일과 함께 풀 수 있다. OS 보안 저장소(Keychain 등)를 쓰지는 않는다.

저장 이력도 이 파일에 있으므로 이 파일을 지우거나 다른 PC로 옮기지 않으면 이력은 그 PC에만 남는다. 1년이 지난 이력은 기록할 때 지워진다.

## 6.7 오류 로그

예상하지 못한 오류는 위 폴더의 `logs/error.log`에 남는다. **도움말 > 오류 로그 폴더 열기**로 바로 연다.
연결 문자열의 비밀번호는 지운 뒤 기록한다.

화면 쪽에서 오류가 나면 앱은 꺼지지 않고 `계속 / 종료`를 묻는다. **계속**을 고른 뒤 저장하지 않은 편집을 먼저 저장한다.

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

## 6.9 문의·버그 제보

[Issues](https://github.com/almyeonseo/SchemaForge-releases/issues)에 남긴다. 다음을 함께 적으면 빨리 찾는다.

- 앱 버전 (**도움말 > SchemaForge 정보**)과 OS
- 무엇을 했고 무엇을 기대했고 실제로 무엇이 일어났는지
- 오류가 났다면 `logs/error.log`
