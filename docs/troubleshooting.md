# 6. 문제 해결

[목차](README.md) · 이전: [5. 단축키](shortcuts.md) · 다음: [6. DB 탐색기](troubleshooting-explorer.md)

- **설치와 연결**
  - [6.1 설치와 연결](#61-설치와-연결)
- **DB 탐색기** ([troubleshooting-explorer.md](troubleshooting-explorer.md))
  - [6.2 DB 탐색기](troubleshooting-explorer.md#62-db-탐색기)
- **코멘트 입력과 저장** ([troubleshooting-editing.md](troubleshooting-editing.md))
  - [6.3 코멘트 입력과 저장](troubleshooting-editing.md#63-코멘트-입력과-저장)
- **SQL 편집기** ([troubleshooting-sql.md](troubleshooting-sql.md))
  - [6.4 SQL 편집기](troubleshooting-sql.md#64-sql-편집기)
- **업데이트·데이터·문의** ([troubleshooting-info.md](troubleshooting-info.md))
  - [6.5 업데이트](troubleshooting-info.md#65-업데이트)
  - [6.6 데이터 저장 위치](troubleshooting-info.md#66-데이터-저장-위치)
  - [6.7 오류 로그](troubleshooting-info.md#67-오류-로그)
  - [6.8 지원하지 않는 것](troubleshooting-info.md#68-지원하지-않는-것)
  - [6.9 문의·버그 제보](troubleshooting-info.md#69-문의버그-제보)

## 6.1 설치와 연결

**macOS에서 앱이 열리지 않는다.**
시스템 설정 > 개인정보 보호 및 보안에서 **그래도 열기**를 누른다. zip을 받았다면 터미널 `unzip`이 아니라 Finder에서 풀어야 한다.

**연결 테스트가 인증서 오류로 실패한다.**
서버가 자체 서명 인증서를 쓴다. 연결 대화상자에서 **서버 인증서 신뢰**를 켠다.

**MariaDB 연결 테스트가 TLS 오류로 실패한다.**
MariaDB 연결은 늘 암호화한다. 서버에 TLS가 켜져 있지 않으면 붙지 못하니 DB 관리자에게 TLS 설정을 요청한다. 서버가 자체 서명
인증서를 쓰면 **서버 인증서 신뢰**를 켠다.

**MySQL 연결 테스트가 인증서 오류로 실패한다.**
서버가 스스로 만든 인증서를 쓰고 있다. 연결 창의 `서버 인증서 신뢰`를 켜고 다시 테스트한다.

**PostgreSQL 연결 테스트가 `서버에서 SSL을 켜야 붙습니다`로 실패한다.**
이 앱은 암호화 없이 연결하지 않는다. DB 관리자에게 서버의 SSL 설정을 요청한다.

**MariaDB 연결에서 저장 프로시저·함수 폴더가 비어 있다.**
계정에 그 DB의 `EXECUTE` 권한이 없다. MariaDB는 `SELECT`만 있는 계정에 루틴을 보여 주지 않는다. DB 관리자에게 `EXECUTE` 권한을 요청한다.

**Oracle 연결에서 저장 프로시저·함수 폴더가 비어 있다.**
다른 스키마의 프로시저·함수는 그 루틴의 `EXECUTE` 권한이 있어야 보인다. DB 관리자에게 권한을 요청한다.
