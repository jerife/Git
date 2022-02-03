# Git & GitHub
 개인적으로 Git & GitHub 사용법을 공부하고 정리해놓은 Repository 입니다.

### 1. Server & Client
Git : 로컬(local) 컴퓨터에서 실행되는 버전관리 프로그램<br/>
GitHub : 원격(remote) 컴퓨터에서 버전을 저장하는 저장소
<br/>

### 2. CLI기반 명령어
#### 2-1) Git 명령어
```bash
# 해당 파일을 깃으로 버전관리하겠다고 선언하는 명령어 (최초 1회만 사용)
$ git init 
```
```bash
# 수정되거나 추가된 파일들을 모아놓는 명령어
# [file] 부분에 . 을 입력할 경우 수정되거나 추가된 모든파일을 모아 놓음
$ git add [file]
```
```bash
# 파일들이 수정되거나 추가되거나 add되었는지 확인하는 명령어
$ git status 
```
```bash
# add 명령어로 모아놓은 수정되거나 추가된 모든 파일을 저장하는 명령어
$ git commit -m "write your commit message"
```
```bash
# commit된 기록들을 확인하는 명령어
$ git log
```
```bash
# 모든 커밋엔 고유한 커밋 코드가 있음. 그 커밋코드로 코드를 초기화하는 법
# [commit code]를 입력하지 않으면 최신 커밋버전으로 초기화 됨
$ git reset --hard [commit code]
```

#### 2-2) 원격 관리를 위한 GitHub 명령어 
```bash
# 원격의 레포지토리를 조정하겠다는 명령어 
$ git remote add origin [link]
```
```bash
# 원격의 레포지토리를 로컬로 받아오는 명령어
$ git clone [link]
```
```bash
# 원격 레포지토리의 업데이트 내용을 로컬로 가져와서 업데이트하는 명령어
$ git pull origin main
```
<br/>

### 3. 협업 방법
#### 3-1) 개발할때마다 원격 레포지토리에서 Pull 받고 Conflict 발생하면 직접 수정 후 Push
#### 3-2) Branch를 사용해 따로 개발 후 Merge
팀원들이 각자 branch를 생성하고 개발이 끝나면 PullRequest를 통해 approve를 받은 후 merge하는 것
#### 3-3) Fork로 레포지토리를 복제해 개발 후 Merge
팀의 레포지토리를 복제한 후 로컬에서 clone하고 개발이 PullRequest를 통해 approve를 받은 후 merge하는 것

##### [Branch 협업을 위한 명령어 ]
```bash
# 로컬 branch를 확인하는 명령어
# -a 를 추가할 경우 로컬과 원격 branch를 확인할 수 있음.
$ git branch
```
```bash
# 새로운 branch를 만드는 명령어
$ git branch [write your branch]
```
```bash
# branch를 삭제하는 명령어
$ git branch -D [write your branch]
```
```bash
# branch로 이동하는 명령어
$ git checkout [write your branch]
```
```bash
# branch로 push하는 명령어
$ git push origin [write your branch]
```
```bash
# branch로 pull하는 명령어
$ git pull origin [write your branch]
``````
<br/>


### 4. 추가적인 사용 팁
#### 4-1) .gitignore
원격 레포지토리에 올리고 싶지 않은것들을 제한할수 있음.
* Example) ip주소나 비번을 모아놓은 "account.config" 파일을 올지 않을때
```bash
*.config
```
.gitignore 파일에 위 코드를 추가하면 됨
> 추가로 [gitignore.io](gitignore.io) 라는 사이트에서 프로그램 언어마다 필요없는 파일들을 선언해 놓은 .gitignore 파일이 있음.

##### 4-2) Ocrotree 라는 크롬브라우저 확장 프로그램을 이용해 레포지토리를 편하게 확인할 수 있음.

##### 4-3) 협업시 레포지토리의 Insights 목록에서 팀원들의 활약도를 확인할 수 있음.
![noname](https://user-images.githubusercontent.com/68190553/152108985-4b38fa00-1f95-41cb-8ae5-01ae5cad316a.png)

##### 4-4) 팁 협업시 Slack을 이용해 PR(Pull Request)나 Issue 알림을 전달받을 수 있음.
![image](https://user-images.githubusercontent.com/68190553/152284966-85d2cf96-108c-42bc-b219-efec9c79b8ad.png)


##### 4-5) 협업에서 Commit할때에는 Message를 아래와 같이 남겨주면 좋음.
* feat : 새로운 기능의 추가
* fix: 버그 수정
* build : 빌드 관련 파일 수정
* docs: 문서 수정
* style: 코드 형식 관련한 수정
* refactor: 코드 리펙토링
* test: 테스트 코드 수정
* chore: 파일 관리같은 것(기타) 수정
