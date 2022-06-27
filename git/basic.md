# GIT 이란? 무엇인가
> `git`이란 분산 버전 관리 시스템으로 컴퓨터 파일의 변경사항을 추적하고 여러 파일 작업들을 조율하는데 사용한다

>`github`란 ? git을 사용하는 프로젝트를 지원하는 웹 호스팅 서비스

---

### git 프로젝트 올리기
1. 리퍼지토리를 만든다 + 주소 기억하기
<br/><br/>


2. 초기 설정을 한다.
```
git config --global user.name "NAME"
git config --global user.email "EMAIL"
```

3. 파일 준비를한다

```
git init  // git파일 생성
git add . // 선택한 프로젝트 폴더 내의 모든 파일 관리
git status // 상태확인
git commit -m '내용' // 커밋하기
```

4. 업로드를 한다
```
git remote add origin 리퍼지토리주소
git push -u origin master
```

5. 끝

___

## git 명령어 모음 ((몇개만))

위에 나온건 생략했습니다
<br/>
### clone
```
git clone URL //저장소 복제 , 다운로드
git clone /로컬/저장소/경로  //로컬 저장소 복제
```

### commit
```
$ git add <파일명>
$ git add *   // 커밋에 단일 파일의 변경 사항을 포함
```

### branch
```
$ git branch // 브랜치 목록
$ git branch // <브랜치이름>	새 브랜치 생성 (local로 만듦)
$ git checkout -b // <브랜치이름>	브랜치 생성 & 이동
$ git checkout master	// master branch로 되돌아 옴
```

### push
```
$ git push origin master // 변경사항 원격 서버에 업로드
$ git push < remote > // <브랜치이름>	커밋을 원격 서버에 업로드
$ git push -u < remote > // <브랜치이름>	커밋을 원격 서버에 업로드
```