# 6. 문제 해결 — DB 탐색기

[목차](README.md) · 이전: [6. 문제 해결](troubleshooting.md) · 다음: [6. 코멘트 입력과 저장](troubleshooting-editing.md)

- **설치와 연결** ([troubleshooting.md](troubleshooting.md))
  - [6.1 설치와 연결](troubleshooting.md#61-설치와-연결)
- **DB 탐색기**
  - [6.2 DB 탐색기](#62-db-탐색기)
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

## 6.2 DB 탐색기

**트리 폴더에 `불러오기 실패: …`가 뜬다.**
출력 창의 `[오류]` 줄에 원인이 있고 자세한 내용은 오류 로그에 남는다([6.7](troubleshooting-info.md#67-오류-로그)). 폴더를 오른쪽 클릭해 **새로고침**으로 다시 읽는다.

**연결을 펼쳤는데 기본 DB 하나만 보인다.**
DB 목록을 읽지 못했다. 앱은 기본 DB로 목록을 묻고, 기본 DB에 붙지 못하면(오프라인, 복원 중, 권한 없음) `master`로 다시 묻는다.
둘 다 실패하면 기본 DB만 남기고 출력 창에 이유를 적는다. 계정에 다른 DB 접근 권한이 있는지 확인한 뒤 연결을 오른쪽 클릭해 **새로고침**한다.

**방금 만든 DB가 트리에 없다.**
DB 목록은 연결을 처음 펼칠 때 한 번 읽는다. 연결을 오른쪽 클릭해 **새로고침**한다. DB 노드의 **새로고침**은 그 DB의 폴더만 다시 읽어 DB 목록은 바뀌지 않는다.

**기본 DB가 아닌 DB를 열었는데 연결 대화상자에서 DB를 바꿔야 하나?**
아니다. 연결 하나로 같은 서버의 접근 가능한 DB를 모두 본다. 연결을 펼쳐 그 DB 노드 아래에서 열면 그 DB에서 읽고 그 DB에 저장한다.
**운영 DB도 같은 트리에 함께 보일 수 있으므로** 저장 전에 탭 도구 설명이나 출력 창의 DB 이름을 확인한다.

**검색했는데 있는 개체가 나오지 않는다.**
검색은 검색 패널 맨 위 콤보에서 고른 DB 하나만 본다. 콤보의 범위를 확인한다. 패널을 연 뒤 트리에서 다른 DB를 눌러도 범위는 따라가지 않는다.
컬럼을 찾으려면 `개체`가 아니라 `컬럼`을 고른다([1.5](getting-started-search.md#검색)).

**컬럼 검색 결과를 더블클릭했는데 문서에서 그 컬럼이 골라지지 않았다.**
그 문서에 검색어나 `미작성만`이 걸려 있어 행이 가려진 경우다. 앱은 필터를 대신 풀지 않고 문서 아래 상태 문구로 알린다. 필터를 풀고 다시 연다.
