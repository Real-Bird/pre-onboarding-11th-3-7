# pre-onboarding-11th-3-7

원티드 프리온보딩 인터십 7팀의 3주 차 과제 팀 레포

팀원 : 김진영, 김동주, 박서희, 윤지현, 조영민, 한주연

## 1. 최종 구현 화면

### 1-1. Landing -> Issues List -> An Issue -> Back
[complete-video.webm](https://github.com/Real-Bird/pre-onboarding-11th-3-7/assets/83404864/9c92278f-4ddf-4f88-a0da-fc66601a4ec9)

## 2. 설치, 환경설정 및 실행 방법

```
npm ci
npm start
```
## 3. 구현 요구 사항 목록

### 3-1. 필수 요구 사항

- [x] 이슈 목록 및 상세 화면 기능 구현
   - GitHub REST API로 `issues`와 `an issue` 정보를 요청하여 렌더링했습니다.
- [x] Context API를 활용한 API 연동
   - 베이스 파일에서 생성한 `instance`들을 각각의 `context`에 연결하여 필요한 서비스에서 호출하였습니다.
- [x] 데이터 요청 중 로딩 표시
   - fetch 중일 때 `loading` 상태를 변경하여 로딩 중임을 알 수 있는 UI를 구현했습니다.
- [x] 에러 화면 구현
   - `ErrorBoundary`로 에러가 발생할 수 있는 컴포넌트를 감싸 대응했습니다.
   - 에러가 발생하면 해당 에러 메세지를 알려주는 페이지를 렌더링합니다.

[error-complete-video.webm](https://github.com/Real-Bird/pre-onboarding-11th-3-7/assets/83404864/9549579b-d6c7-4f1a-b544-4436c02575b6)

   - 예시 영상은 존재하지 않는 아무 레포지토리를 요청한 결과입니다.
- [x] 지정된 조건(open 상태, 코멘트 많은 순)에 맞게 데이터 요청 및 표시
   - `open`과 `comments sort`는 default로 원하는 정보를 제공하여 필요한 `comments`와 `page`만 쿼리에 추가해 요청했습니다.

### 3-2. 이슈 목록 화면

- [x] 이슈 목록 가져오기 API 활용
- [x] open 상태의 이슈 중 코멘트가 많은 순으로 정렬
- [x] 각 행에는 ‘이슈번호, 이슈제목, 작성자, 작성일, 코멘트수’를 표시
- [x] 다섯번째 셀에는 광고 이미지 출력
- [x] 광고 이미지 클릭 시 https://www.wanted.co.kr/ 로 이동
- [x] 화면을 아래로 스크롤 할 시 이슈 목록 추가 로딩(인피니티 스크롤)

### 3-3. 이슈 상세 화면

- [x] 이슈의 상세 내용 표시
- [x] ‘이슈번호, 이슈제목, 작성자, 작성일, 코멘트 수, 작성자 프로필 이미지, 본문' 표시
- [ ] 
### 3-4. 공통 헤더

- [x] 두 페이지는 공통 헤더를 공유합니다.
- [x] 헤더에는 Organization Name / Repository Name이 표시됩니다.

## 4. 사용한 프레임워크 및 라이브러리

선택사항으로 사용한 라이브러리 목록입니다.

- `react-markdown`, `react-syntax-highlighter`, `remark-gfm` : 마크다운 렌더링 용도
- `tailwindcss`, `postcss`, `autoprefixer` : 퍼블리싱 용도

## 5. 과제 진행 시 주안점

### 5-1. class 적극 사용
- 사용해 본 적 없는 `class` 문법을 적극 활용하여 프로젝트를 구현하는데 집중했습니다.
- 다소 어려웠지만, 프로젝트 시작점에서 인스턴스를 생성하고, 수정 사항이 필요할 때마다 각 `class`만 손대면 되는 것이 장점으로 다가왔습니다.

### 5-2. 관심사 분리

- 가능한 한 하나의 로직이 하나의 도메인만 담당하도록 구현했습니다.

### 5-3. 의사 코드 작성 후 실제 코드 구현

- 코드부터 작성하고 오류를 수정하던 버릇을 고쳐보고자 코드 작성 전 의사 코드를 작성했습니다.
- 실제 코드와 많은 차이가 있었지만, 코드 흐름을 정리하는 데에 큰 도움을 받았습니다.
- `$thought_logs`라는 폴더에 정리했습니다.

## 6. 한계점 및 개선 사항

### 6-1. 많이 부족한 UI

- 기능 구현에 많은 시간을 소모하여 UI를 대강 구현했습니다.
- 추가 구현 및 개선 사항
   - `Skeleton`과 `Spinner`를 이용한 로딩 화면
   - `theme` 설정과 뒤로가기 버튼 등 편의성 UI
   - `Octocat SVG`를 추가해 깃허브 이슈임을 강조

### 6-2. type 설정의 어려움
- 실수를 방지하고자 `TypeScript`를 선호하지만, 세세한 타입에 대해서 하드 코딩합니다.
- 이론적인 공부를 조금 더 깊이하여 개선점을 찾아볼 예정입니다.
