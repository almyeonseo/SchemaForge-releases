# SchemaForge 사용 설명서

SchemaForge로 MS SQL Server·MariaDB·MySQL·PostgreSQL·Oracle 개체에 이름과 설명을 달고 정의서를 뽑고 SQL을 실행하는 방법을
하려는 일 순서로 정리했다. 처음이면 1장부터 읽는다. DBMS마다 무엇을 저장하고 무엇을 읽기만 하는지는 [README의 지원 표](../README.md#dbms별-지원-범위)에 있다. 앱에서는 **도움말 > 사용 설명서**로 이 페이지를 연다.

| 장 | 내용 |
|---|---|
| [1. 시작하기](getting-started.md) | 설치(받는 파일과 처음 실행) |
| [1. 화면 구성](getting-started-screen.md) | 화면 영역, 메뉴마다 하는 일, 문서 하단의 연결 정보, 레이아웃 초기화 |
| [1. DB 연결 만들기](getting-started-connect.md) | 연결 창 입력, 연결 고치기와 지우기 |
| [1. DB 탐색기](getting-started-explorer.md) | 트리 구조, 펼치기와 열기, 탐색기 툴바, 우클릭 메뉴 |
| [1. 연결 정리와 검색](getting-started-search.md) | 연결 순서 바꾸기, SQL 편집기로 끌어 놓기, 개체·컬럼 검색 |
| [1. MariaDB·MySQL 연결](getting-started-dbms.md) | MariaDB·MySQL 연결 만들기, 트리, 저장할 수 있는 것, 테이블마다 저장 |
| [1. PostgreSQL·Oracle 연결](getting-started-postgresql-oracle.md) | PostgreSQL·Oracle 연결 만들기, 트리, 저장 |
| [2. 코멘트 달기](comments.md) | 코멘트가 저장되는 자리와 `이름§설명` 형식, 구분자 바꾸기 |
| [2. 편집 화면](comments-screen.md) | 분류 목록 문서, 개체 문서(인덱스·제약조건 탭), 툴바 |
| [2. 값 입력](comments-input.md) | 이름·설명 입력과 지킬 것 |
| [2. 채울 곳만 보기](comments-filter.md) | 미작성만·변경만 보기 |
| [2. 저장](comments-save.md) | 저장, 저장 로그, 저장하지 않은 편집을 지키는 장치 |
| [2. 저장 충돌](comments-conflict.md) | 불러온 뒤 다른 사람이 저장했을 때 남길 값 고르기 |
| [2. 행 되돌리기](comments-revert.md) | 고친 행과 머리글을 불러온 값으로 되돌리기 |
| [2. Excel에서 붙여넣기](comments-fill.md) | Excel에서 복사한 이름·설명 열을 그리드에 붙여넣기 |
| [2. 이름 제안](comments-suggest.md) | 같은 컬럼명에 쓰인 이름 제안으로 채우기 |
| [2. 같은 컬럼명 이름 맞추기](comments-match.md) | 여러 테이블의 같은 컬럼명 이름을 한 화면에서 맞추기 |
| [2. 찾아 바꾸기와 설명 편집](comments-replace.md) | 보이는 행의 이름·설명 찾아 바꾸기, 여러 줄 설명 편집 |
| [2. 작성률](comments-review.md) | 작성률과 미작성 개체, 품질 점검·추이, Excel 보고서, 미작성 컬럼 채우기 |
| [2. 다른 DB·파일과 비교](comments-compare.md) | 다른 DB나 내보낸 파일을 기준으로 다르거나 빈 항목 맞추기 |
| [2. 저장 이력](comments-history.md) | 저장 이력과 이전 값으로 되돌리기 |
| [2. 변경분 스크립트](comments-script.md) | 고친 값을 DB에 쓰지 않고 SQL 스크립트로 내보내기 |
| [3. 파일로 주고받기](import-export.md) | 두 파일 기능의 차이, CSV·Excel 내보내기(보이는 행만 포함) |
| [3. 가져오기](import.md) | 엑셀에서 고친 파일을 그리드에 채우고 확인한 뒤 저장하기 |
| [3. 정의서 내보내기](definition-export.md) | 개체를 골라 표제부를 갖춘 제출용 엑셀 정의서 만들기 |
| [4. SQL 편집기](sql-editor.md) | 편집기 여는 방법, `상위 1000개 행 선택`, 화면 구성 |
| [4. 실행하기](sql-editor-run.md) | 실행, 오류 표시, `GO` 일괄 처리 |
| [4. 예상 규모](sql-editor-estimate.md) | 실행 전에 보는 예상 규모 줄과 `규모 확인` |
| [4. 결과 보기](sql-editor-results.md) | 결과 탭과 `메시지` 탭, 결과 탭 고정 |
| [4. 결과 다루기](sql-editor-handling.md) | 셀 고르기, 복사, 값 보기, 행 세로로 보기, 결과에서 찾기 |
| [4. 정렬·거르기·열 정리](sql-editor-arrange.md) | 정렬, 거르기, 열 숨기기·고정·폭 맞추기, 고른 셀 요약 |
| [4. 결과 저장](sql-editor-save.md) | 결과를 엑셀·CSV로 저장 |
| [4. 편집 기능](sql-editor-editing.md) | 찾기·바꾸기, 세로 선택, 주석 처리, 책갈피, 코드 접기 등 |
| [4. 개체와 코멘트 연결](sql-editor-objects.md) | 이름 툴팁, 코멘트 문서 열기, 정의 열기, 실행문 만들기 |
| [4. 파일로 저장·지난 탭](sql-editor-files.md) | 쿼리 파일 열기·저장, 앱을 켤 때 지난 탭 다시 열기 |
| [4. MariaDB 연결](sql-editor-dbms.md) | MariaDB·MySQL 편집기의 조회 전용, 쓰기 허용, 문법 |
| [4. PostgreSQL 연결](sql-editor-postgresql.md) | PostgreSQL 편집기의 조회 전용과 쓰기 허용 |
| [4. Oracle 연결](sql-editor-oracle.md) | Oracle 편집기의 조회 전용, 쓰기 허용, PL/SQL 블록, 결과 칸 |
| [5. 설정과 단축키](settings-shortcuts.md) | 설정 창(테마, 화면·코드 글꼴과 글자 크기 등) |
| [5. 단축키](shortcuts.md) | Windows·macOS 단축키 표 |
| [6. 문제 해결](troubleshooting.md) | macOS 첫 실행, 연결 테스트의 인증서·TLS·SSL 오류, 빈 루틴 폴더 |
| [6. DB 탐색기](troubleshooting-explorer.md) | 폴더 불러오기 실패, DB 목록이 안 보일 때, 검색에 개체가 안 나올 때 |
| [6. 코멘트 입력과 저장](troubleshooting-editing.md) | 저장되지 않을 때, 붙여넣기·저장 이력 |
| [6. SQL 편집기](troubleshooting-sql.md) | 단축키, 조회 전용 오류, `GO`, 예상 규모 줄, 큰 결과 |
| [6. 업데이트·데이터·문의](troubleshooting-info.md) | 업데이트, 데이터 저장 위치, 오류 로그, 지원하지 않는 것, 문의 |

## 5분 만에 써 보기

1. [최신 릴리스](https://github.com/almyeonseo/SchemaForge-releases/releases/latest)에서 OS에 맞는 파일을 받아 설치한다.
2. 앱을 켜고 시작 페이지의 **새 DB 연결**을 눌러 서버를 등록한다.
3. 왼쪽 DB 탐색기에서 연결, 그 아래 DB, `테이블` 폴더를 차례로 더블클릭해 펼친다.
4. 테이블 하나를 더블클릭하고 컬럼의 `이름` 칸을 두 번 클릭해 입력한다.
5. Windows `Ctrl+S` / macOS `Cmd+S`로 저장한다. 바꾼 값은 아래 출력 창에 이전 값→새 값으로 남는다.

> 저장하면 바로 그 DB의 `MS_Description` 확장 속성(MariaDB·MySQL은 개체의 `COMMENT`, PostgreSQL·Oracle은 `COMMENT ON`)이 바뀐다. 처음에는 개발·테스트용 DB로
> 연습하는 것이 좋다.

이 설명서는 1.13.0 기준이다. 화면이 설명과 다르면 [Issues](https://github.com/almyeonseo/SchemaForge-releases/issues)에 알려 주면 고친다.
