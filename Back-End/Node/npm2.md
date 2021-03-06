# 기타 명령어

### npm -version
- npm 자체의 버전 체크
> npm -v 로 축약 가능

<br>

### npm install -g npm
- npm 자체의 버전 업그레이드
> 맥 리눅스의 경우에는 sudo를 붙여야 할 수도있다.

<br>

### npm outdated
- 업데이트 가능한 패키지가 있는지 체크

<br>

### npm update 패키지명
- 패키지를 최신 버전으로 업데이트

<br>

### npm info 패키지명
- 패키지의 상세 정보 파악

<br>

### npm search 검색어
- npm 서버의 패키지 검색

<br>

### npm help
- 명령어 목록 확인

<br>

### npm ls
- 설치된 패키지들의 구조를 보여준다.
> npm ls 패키지명 : 패키지와 관련된 구조만 노출
> npm ll : 더 상세한 패키지 구조 정보 노출

<br>

### npx 패키지명 [옵션]
- 설치하지 않은 패키지를 전역처럼 콘솔에서도 사용할 수 있도록 해주는 명령어
- 즉, node_modules/bin 폴도에서 해당 패키지의 바이너리 파일을 찾아서 실행시켜 준다.
- 만약 해당 패키지가 없다면 임시로 다운로드 받아 설치하여 실행시킨다.
> npx에 대한 내용은 길어질 수 있으므로 생략
> 사용예시 : npx pm2 list


<br><br>

## Node.js가 패키지를 참조하는 방식
- node.js 에서 외부모듈을 사용하면, 아래와 같은 순서로 패키지를 찾아간다.

  1. `현재 실행 중인 폴더`  에서 찾는다 (최우선 순위)
  2. `상위 폴더로 이동`해서 찾는다.
  3. `전역 패키지가 설치된 폴더`로 이동해서 찾는다.