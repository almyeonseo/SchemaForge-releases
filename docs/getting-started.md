# 1. 시작하기

[목차](README.md) · 다음: [1. 화면 구성](getting-started-screen.md)

- **설치**
  - [1.1 설치](#11-설치)
- **화면 구성** ([getting-started-screen.md](getting-started-screen.md))
  - [1.2 화면 구성](getting-started-screen.md#12-화면-구성)
- **DB 연결 만들기** ([getting-started-connect.md](getting-started-connect.md))
  - [1.3 DB 연결 만들기](getting-started-connect.md#13-db-연결-만들기)
- **DB 탐색기** ([getting-started-explorer.md](getting-started-explorer.md))
  - [1.4 DB 탐색기 쓰기](getting-started-explorer.md#14-db-탐색기-쓰기)
- **연결 정리와 검색** ([getting-started-search.md](getting-started-search.md))
  - [1.5 연결 정리와 검색](getting-started-search.md#15-연결-정리와-검색)
- **MariaDB·MySQL 연결** ([getting-started-dbms.md](getting-started-dbms.md))
  - [1.6 MariaDB 연결](getting-started-dbms.md#16-mariadb-연결)
  - [1.7 MySQL 연결](getting-started-dbms.md#17-mysql-연결)
- **PostgreSQL·Oracle 연결** ([getting-started-postgresql-oracle.md](getting-started-postgresql-oracle.md))
  - [1.8 PostgreSQL 연결](getting-started-postgresql-oracle.md#18-postgresql-연결)
  - [1.9 Oracle 연결](getting-started-postgresql-oracle.md#19-oracle-연결)

## 1.1 설치

[최신 릴리스](https://github.com/almyeonseo/SchemaForge-releases/releases/latest)의 **Assets**에서 OS에 맞는
파일을 받는다. .NET 런타임이 들어 있어 따로 설치할 것이 없다.

| OS | 받을 파일 | 설치 |
|---|---|---|
| Windows (x64) | `SchemaForge-<버전>-win-x64-setup.exe` | 실행하면 관리자 권한 없이 설치되고 시작 메뉴에 등록된다. 제거는 설정 > 앱 |
| macOS (Apple Silicon) | `SchemaForge-<버전>-osx-arm64.dmg` | dmg를 열어 앱을 Applications로 끌어 넣는다 |
| macOS (Intel) | `SchemaForge-<버전>-osx-x64.dmg` | 위와 같다 |
| Linux (x64) | `SchemaForge-<버전>-x86_64.AppImage` | 실행 권한을 주고(`chmod +x`) 실행한다 |

설치 없이 쓰려면 같은 버전의 zip을 받는다.

- **Windows zip** — 압축을 풀고 `SchemaForge.UI.exe`를 실행한다.
- **macOS zip** — Finder에서 더블클릭해 푼다. 터미널 `unzip`으로 풀면 앱 서명이 깨져 실행이 막힌다.
- **Linux zip** — 압축을 푼 자리에서 처음 한 번 `sh install.sh`를 실행한다. 실행 권한이 붙고 앱 메뉴에 등록된다.

macOS에서 처음 실행이 막히면 시스템 설정 > 개인정보 보호 및 보안에서 **그래도 열기**를 누른다.
서명·공증을 하지 않은 앱이라 한 번은 이 단계를 거친다.
