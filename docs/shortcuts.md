# 5. 설정과 단축키 — 단축키

[목차](README.md) · 이전: [5.1 설정](settings-shortcuts.md) · 다음: [6.1 설치와 연결](troubleshooting.md)

- [5.1 설정](settings-shortcuts.md#51-설정)
- [5.2 단축키](#52-단축키)

## 5.2 단축키

앱 안에서는 **도움말 > 단축키 목록**으로 지금 OS에 맞는 표를 볼 수 있다.
macOS에서는 대개 `Ctrl` 자리를 `Cmd`로 누른다. 다른 점은 아래 표의 macOS 칸에 적었다.

- 종료는 `Cmd+Q`, 바꾸기는 `Cmd+Option+F`다(`Cmd+H`는 macOS에서 앱 숨기기다).
- `Alt`는 `Option`이다.
- `Tab`이 든 키는 macOS에서도 `Control`이다. `Cmd+Tab`은 macOS가 앱 전환에 쓴다.
- `Ctrl+K, Ctrl+C`처럼 쉼표로 이은 키는 앞 키를 누른 뒤 뒤 키를 누르는 두 번 누르기다.

### 어디서나

| 동작 | Windows·Linux | macOS |
|---|---|---|
| 새 쿼리 — DB 탐색기에서 고른 연결 | `Ctrl+N` | `Cmd+N` |
| 쿼리 파일 열기 — DB 탐색기에서 고른 연결 | `Ctrl+O` | `Cmd+O` |
| 새 DB 연결 | `Ctrl+Shift+N` | `Cmd+Shift+N` |
| 지금 탭 저장 — 코멘트 문서는 DB에, SQL 편집기는 파일에 | `Ctrl+S` | `Cmd+S` |
| 모두 저장 — 열린 탭의 코멘트 문서와 SQL 편집기 | `Ctrl+Shift+S` | `Cmd+Shift+S` |
| 현재 탭 닫기 | `Ctrl+W` | `Cmd+W` |
| 라이트·다크 테마 바꾸기 | `Ctrl+T` | `Cmd+T` |
| 설정 | `Ctrl+,` | `Cmd+,` |
| 사용 설명서 열기 | `F1` | `F1` |
| SQL 편집기 탭에서는 실행, DB 탐색기 안에서는 연결 프로필 새로고침 | `F5` | `F5` |
| SQL 실행 — DB 탐색기에 포커스가 있어도 실행 | `Ctrl+Enter` | `Cmd+Enter` |
| 커서가 있는 일괄 처리(`GO` 줄 사이)만 실행 | `Ctrl+Shift+Enter` | `Cmd+Shift+Enter` |
| 예상 규모 확인 — 실행 계획만 묻고 실행하지 않는다([4.3](sql-editor-estimate.md#43-예상-규모-줄)) | `Ctrl+L` | `Cmd+L` |
| SQL 실행 중단 — 변경은 되돌려진다 | `Ctrl+.` | `Cmd+.` |
| SQL 편집기의 결과 창 숨기기·펼치기 | `Ctrl+R` | `Cmd+R` |
| 이름이 비어 있는 다음 / 이전 항목 (코멘트 문서) | `F8` / `Shift+F8` | `F8` / `Shift+F8` |
| 종료 | `Alt+F4` | `Cmd+Q` |

### SQL 편집기

| 동작 | Windows·Linux | macOS |
|---|---|---|
| 실행 취소 / 다시 실행 | `Ctrl+Z` / `Ctrl+Y` | `Cmd+Z` / `Cmd+Y` |
| 잘라내기 / 복사 / 붙여넣기 | `Ctrl+X` / `Ctrl+C` / `Ctrl+V` | `Cmd+X` / `Cmd+C` / `Cmd+V` |
| 찾기 — 결과 그리드에 포커스가 있으면 결과에서 찾기 | `Ctrl+F` | `Cmd+F` |
| 바꾸기 — 찾기 칸을 바꾸기 모드로 연다 | `Ctrl+H` | `Cmd+Option+F` |
| 다음 / 이전 찾기 | `F3` / `Shift+F3` | `F3` / `Shift+F3` |
| 검색창 닫기 | `Esc` | `Esc` |
| 줄로 이동 — 줄 번호(줄:열)를 넣어 그 자리로 | `Ctrl+G` | `Cmd+G` |
| 고른 줄 주석 처리 | `Ctrl+K, Ctrl+C` | `Cmd+K, Cmd+C` |
| 고른 줄 주석 해제 | `Ctrl+K, Ctrl+U` | `Cmd+K, Cmd+U` |
| 커서 줄에 책갈피 넣기·빼기 — 줄 번호 왼쪽 칸을 눌러도 같다 | `Ctrl+K, Ctrl+K` | `Cmd+K, Cmd+K` |
| 다음 / 이전 책갈피 | `Ctrl+K, Ctrl+N` / `Ctrl+K, Ctrl+P` | `Cmd+K, Cmd+N` / `Cmd+K, Cmd+P` |
| 책갈피 모두 지우기 | `Ctrl+K, Ctrl+L` | `Cmd+K, Cmd+L` |
| 커서의 개체 이름으로 코멘트 문서 열기 | `F12` | `F12` |
| 모두 접기 — 가장 바깥 블록만 | `Ctrl+M, Ctrl+O` | `Cmd+M, Cmd+O` |
| 모두 펴기 | `Ctrl+M, Ctrl+L` | `Cmd+M, Cmd+L` |
| 대문자로 / 소문자로 — 고른 글자, 없으면 커서가 있는 단어 | `Ctrl+Shift+U` / `Ctrl+Shift+L` | `Cmd+Shift+U` / `Cmd+Shift+L` |
| 짝 괄호로 이동 | `Ctrl+]` | `Cmd+]` |
| 줄 복제 — 커서 줄이나 고른 줄들을 바로 아래에 | `Ctrl+D` | `Cmd+D` |
| 줄 위로 / 아래로 이동 | `Alt+↑` / `Alt+↓` | `Option+↑` / `Option+↓` |
| 줄 삭제 — 클립보드는 건드리지 않는다 | `Ctrl+Shift+K` | `Cmd+Shift+K` |
| 결과에서 고른 셀의 값 보기 — 셀 더블클릭과 같다 | `Shift+Enter` | `Shift+Enter` |
| 결과에서 고른 셀의 행을 세로로 보기 | `Alt+Enter` | `Option+Enter` |

결과 그리드에서는 아래 키도 쓴다([4.5](sql-editor-handling.md#45-결과-다루기)).

| 동작 | Windows·Linux | macOS |
|---|---|---|
| 고른 셀 복사 / 열 이름까지 복사 | `Ctrl+C` / `Ctrl+Shift+C` | `Cmd+C` / `Cmd+Shift+C` |
| 전체 선택 | `Ctrl+A` | `Cmd+A` |
| 셀 더하기·빼기 | `Ctrl`+클릭 | `Cmd`+클릭 |
| 결과에서 찾기의 다음 / 이전 | `Enter`·`F3` / `Shift+Enter`·`Shift+F3` | 같다 |

### 코멘트 그리드·입력칸에서

| 동작 | Windows·Linux | macOS |
|---|---|---|
| 고른 셀 편집 시작 — 같은 셀을 다시 눌러도 같다. 글자를 바로 쳐서는 시작되지 않는다 | `F2` | `F2` |
| Excel에서 복사한 이름(과 설명) 열을 고른 행부터 붙여넣기 — 셀을 편집하는 중에는 그 칸에 넣는다 | `Ctrl+V` | `Cmd+V` |
| 보이는 행에서 찾아 바꾸기 — 셀을 편집하는 중에는 입력칸이 먼저 받는다 | `Ctrl+H` | `Cmd+Option+F` |
| 고른 행 하나의 설명을 큰 창에서 편집 | `Shift+F2` | `Shift+F2` |
| 편집 중 값을 넣고 옆 칸으로 (편집 상태 유지) | `Tab` | `Tab` |
| 편집을 끝내고 아래 행으로 — 다음 행은 `F2`로 다시 편집한다 | `Enter` | `Enter` |
| 셀 편집 취소 — 편집 전 값으로 돌아간다 | `Esc` | `Esc` |
| 입력칸·셀 편집에서 실행 취소 — 한 글자(음절)씩 되돌린다 | `Ctrl+Z` | `Cmd+Z` |
| 입력칸·셀 편집에서 다시 실행 — 되돌린 글자를 한 글자씩 다시 넣는다 | `Ctrl+Y` | `Cmd+Shift+Z` |

### 정의서 내보내기 창

| 동작 | Windows·Linux | macOS |
|---|---|---|
| 고른 줄의 체크 바꾸기 — 여러 줄을 고르면 함께 | `Space` | `Space` |
| 검색 칸에서 검색 | `Enter` | `Enter` |
| 검색 칸의 검색어 지우기 — 비어 있으면 창 닫기 | `Esc` | `Esc` |
| 다음 / 이전 분류 탭 | `Ctrl+Tab` / `Ctrl+Shift+Tab` | `Control+Tab` / `Control+Shift+Tab` |

### DB 탐색기

| 동작 | Windows·Linux | macOS |
|---|---|---|
| 연결 목록 새로고침 | `F5` | `F5` |
| 오른쪽 클릭 메뉴 | 메뉴 키 · `Shift+F10` | `Shift+F10` |
| 개체의 코멘트 문서 열기 — 더블클릭과 같다 | `Enter` | `Enter` |
