# SchemaForge 사용 설명서

SchemaForge로 MS SQL Server 개체에 한글명과 설명을 달고, 정의서를 뽑고, SQL을 실행하는 방법을
하려는 일 순서로 정리했다. 처음이면 1장부터 읽는다. 앱에서는 **도움말 > 사용 설명서**로 이 페이지를 연다.

| 장 | 내용 |
|---|---|
| [1. 시작하기](getting-started.md) | 설치, 첫 실행, DB 연결 만들기, 화면 구성, DB 탐색기 |
| [2. 코멘트 달기](comments.md) | 한글명·설명 입력, 저장, 미작성 찾기, 저장 충돌 |
| [3. 파일로 주고받기](import-export.md) | CSV·Excel 내보내기와 가져오기, 엑셀 정의서 만들기 |
| [4. SQL 편집기](sql-editor.md) | 쿼리 실행, 결과 확인·저장, 쿼리 파일 |
| [5. 설정과 단축키](settings-shortcuts.md) | 설정 창, 테마, 단축키 표 |
| [6. 문제 해결](troubleshooting.md) | 자주 겪는 문제, 데이터 저장 위치, 오류 로그, 문의 |

## 5분 만에 써 보기

1. [최신 릴리스](https://github.com/almyeonseo/SchemaForge-releases/releases/latest)에서 OS에 맞는 파일을 받아 설치한다.
2. 앱을 켜고 시작 페이지의 **새 DB 연결**을 눌러 서버를 등록한다.
3. 왼쪽 DB 탐색기에서 서버와 `테이블` 폴더를 더블클릭해 펼친다.
4. 테이블 하나를 더블클릭하고, 컬럼의 `한글명` 칸을 두 번 클릭해 입력한다.
5. `Ctrl+S`(macOS는 `Cmd+S`)로 저장한다. 결과는 아래 출력 창에 남는다.

> 저장하면 바로 그 DB의 `MS_Description` 확장 속성이 바뀐다. 처음에는 개발·테스트용 DB로
> 연습할 것.

이 설명서는 1.0.0 기준이다. 화면이 설명과 다르면 [Issues](https://github.com/almyeonseo/SchemaForge-releases/issues)에 알려 주면 고친다.
