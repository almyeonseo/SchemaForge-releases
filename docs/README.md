# SchemaForge 사용 설명서

SchemaForge로 MS SQL Server·MariaDB 개체에 한글명과 설명을 달고 정의서를 뽑고 SQL을 실행하는 방법을
하려는 일 순서로 정리했다. 처음이면 1장부터 읽는다. 앱에서는 **도움말 > 사용 설명서**로 이 페이지를 연다.

| 장 | 내용 |
|---|---|
| [1. 시작하기](getting-started.md) | 설치, 화면 구성, DB 연결 만들기, DB 탐색기(DB 노드, 우클릭 메뉴, 연결 순서, 개체·컬럼 검색), MariaDB 연결 |
| [2. 코멘트 달기](comments.md) | 한글명·설명 입력, 미작성·변경만 보기, 저장과 저장 로그, 저장 충돌, 행 되돌리기, Excel 붙여넣기, 같은 이름 컬럼 맞추기, 저장 이력, 작성률, 한글명 제안, 찾아 바꾸기·설명 편집, 다른 DB와 비교, 변경분 스크립트 |
| [3. 파일로 주고받기](import-export.md) | CSV·Excel 내보내기(보이는 행만 포함)와 가져오기, 엑셀 정의서 만들기 |
| [4. SQL 편집기](sql-editor.md) | 열기, 실행과 예상 규모, 결과 보기·다루기·저장, 편집 기능, 개체와 코멘트 연결, 쿼리 파일과 지난 탭 |
| [5. 설정과 단축키](settings-shortcuts.md) | 설정 창(테마, 화면·코드 글꼴과 글자 크기 등), Windows·macOS 단축키 표 |
| [6. 문제 해결](troubleshooting.md) | 자주 겪는 문제, 업데이트, 데이터 저장 위치, 오류 로그, 문의 |

## 5분 만에 써 보기

1. [최신 릴리스](https://github.com/almyeonseo/SchemaForge-releases/releases/latest)에서 OS에 맞는 파일을 받아 설치한다.
2. 앱을 켜고 시작 페이지의 **새 DB 연결**을 눌러 서버를 등록한다.
3. 왼쪽 DB 탐색기에서 연결, 그 아래 DB, `테이블` 폴더를 차례로 더블클릭해 펼친다.
4. 테이블 하나를 더블클릭하고 컬럼의 `한글명` 칸을 두 번 클릭해 입력한다.
5. Windows `Ctrl+S` / macOS `Cmd+S`로 저장한다. 바꾼 값은 아래 출력 창에 이전 값→새 값으로 남는다.

> 저장하면 바로 그 DB의 `MS_Description` 확장 속성(MariaDB는 개체의 `COMMENT`)이 바뀐다. 처음에는 개발·테스트용 DB로
> 연습할 것.

이 설명서는 1.6.0 기준이다. 화면이 설명과 다르면 [Issues](https://github.com/almyeonseo/SchemaForge-releases/issues)에 알려 주면 고친다.
