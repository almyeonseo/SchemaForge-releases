# SchemaForge 사용 설명서

SchemaForge로 MS SQL Server·MariaDB·MySQL·PostgreSQL·Oracle 개체에 이름과 설명을 달고 정의서를 뽑고 SQL을 실행하는 방법을
하려는 일 순서로 정리했다. 처음이면 1장부터 읽는다. DBMS마다 무엇을 저장하고 무엇을 읽기만 하는지는 [README의 지원 표](../README.md#dbms별-지원-범위)에 있다. 앱에서는 **도움말 > 사용 설명서**로 이 페이지를 연다.

| 장 | 내용 |
|---|---|
| [1. 시작하기](getting-started.md) | 설치, 화면 구성, DB 연결 만들기 |
| [1. DB 탐색기](getting-started-explorer.md) | 트리 구조, DB 노드, 우클릭 메뉴, 연결 순서, 개체·컬럼 검색 |
| [1. DBMS별 연결](getting-started-dbms.md) | MariaDB·MySQL·PostgreSQL·Oracle 연결 만들기와 저장할 수 있는 것 |
| [2. 코멘트 달기](comments.md) | 코멘트 저장 위치와 구분자, 편집 화면(분류 목록·개체 문서·툴바) |
| [2. 값 입력과 보기](comments-input.md) | 이름·설명 입력, 미작성만·변경만 보기 |
| [2. 저장과 되돌리기](comments-save.md) | 저장과 저장 로그, 저장 충돌, 행 되돌리기 |
| [2. 여러 행 한꺼번에 채우기](comments-fill.md) | Excel 붙여넣기, 이름 제안, 같은 컬럼명 이름 맞추기, 찾아 바꾸기·설명 편집 |
| [2. 작성률](comments-review.md) | 작성률과 미작성 개체, 품질 점검·추이, Excel 보고서, 미작성 컬럼 채우기 |
| [2. 다른 DB·파일과 비교](comments-compare.md) | 다른 DB나 내보낸 파일을 기준으로 다르거나 빈 항목 맞추기 |
| [2. 이력·스크립트](comments-history.md) | 저장 이력과 이전 값으로 되돌리기, 변경분 스크립트 |
| [3. 파일로 주고받기](import-export.md) | CSV·Excel 내보내기(보이는 행만 포함)와 가져오기, 엑셀 정의서 만들기 |
| [4. SQL 편집기](sql-editor.md) | 열기, 실행과 `GO` 일괄 처리, 예상 규모 |
| [4. 결과 보기와 저장](sql-editor-results.md) | 결과 탭, 셀 고르기·복사·정렬·거르기·열 고정, 엑셀·CSV 저장 |
| [4. 편집 기능](sql-editor-editing.md) | 찾기·바꾸기, 세로 선택, 주석 처리, 책갈피, 코드 접기 등 |
| [4. 개체 연결·파일](sql-editor-objects.md) | 이름 툴팁·코멘트 문서 열기·정의 열기·실행문 만들기, 쿼리 파일과 지난 탭 |
| [4. DBMS별 차이](sql-editor-dbms.md) | MariaDB·MySQL·PostgreSQL·Oracle 연결의 조회 전용과 쓰기 허용 |
| [5. 설정과 단축키](settings-shortcuts.md) | 설정 창(테마, 화면·코드 글꼴과 글자 크기 등), Windows·macOS 단축키 표 |
| [6. 문제 해결](troubleshooting.md) | 자주 겪는 문제, 업데이트, 데이터 저장 위치, 오류 로그, 문의 |

## 5분 만에 써 보기

1. [최신 릴리스](https://github.com/almyeonseo/SchemaForge-releases/releases/latest)에서 OS에 맞는 파일을 받아 설치한다.
2. 앱을 켜고 시작 페이지의 **새 DB 연결**을 눌러 서버를 등록한다.
3. 왼쪽 DB 탐색기에서 연결, 그 아래 DB, `테이블` 폴더를 차례로 더블클릭해 펼친다.
4. 테이블 하나를 더블클릭하고 컬럼의 `이름` 칸을 두 번 클릭해 입력한다.
5. Windows `Ctrl+S` / macOS `Cmd+S`로 저장한다. 바꾼 값은 아래 출력 창에 이전 값→새 값으로 남는다.

> 저장하면 바로 그 DB의 `MS_Description` 확장 속성(MariaDB·MySQL은 개체의 `COMMENT`, PostgreSQL·Oracle은 `COMMENT ON`)이 바뀐다. 처음에는 개발·테스트용 DB로
> 연습하는 것이 좋다.

이 설명서는 1.13.0 기준이다. 화면이 설명과 다르면 [Issues](https://github.com/almyeonseo/SchemaForge-releases/issues)에 알려 주면 고친다.
