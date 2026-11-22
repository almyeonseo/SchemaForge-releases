# 6. 문제 해결 — 데이터 저장 위치

[목차](README.md) · 이전: [6.5 업데이트](troubleshooting-info.md) · 다음: [6.7 오류 로그](troubleshooting-log.md)

- [6.1 설치와 연결](troubleshooting.md#61-설치와-연결)
- [6.2 DB 탐색기](troubleshooting-explorer.md#62-db-탐색기)
- [6.3 코멘트 입력과 저장](troubleshooting-editing.md#63-코멘트-입력과-저장)
- [6.4 SQL 편집기](troubleshooting-sql.md#64-sql-편집기)
- [6.5 업데이트](troubleshooting-info.md#65-업데이트)
- [6.6 데이터 저장 위치](#66-데이터-저장-위치)
- [6.7 오류 로그](troubleshooting-log.md#67-오류-로그)
- [6.8 지원하지 않는 것](troubleshooting-unsupported.md#68-지원하지-않는-것)
- [6.9 문의·버그 제보](troubleshooting-contact.md#69-문의버그-제보)

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
