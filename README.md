# git명령어

### 일반적인 작업시 사용하는 명령어
```bash
$ cd [깃 로컬 저장소 경로]
$ git checkout -b [브랜치 이름]
$ git add .
$ git commit -m "[커밋 메시지]"
$ git push origin [브랜치 이름]
- 웹에서 merge 요청
$ git merge master (내 branch로 받아오는 작업)
```
### 새로운 로컬 저장소 만들기
```bash
$ cd Desktop
$ mkdir sample
$ cd sample/
$ git init
git init을 잘못한 경우엔 .git을 삭제하면 된다.
```
### git 저장소 상태 보기
>$ git status

### 인덱스 추가
```bash
$ git add . 
or
$ git add [커밋할 파일명]
```
### Commit
>$ git commit -m "[커밋메시지]"
>- 의미있는(논리적인 한가지) 작업을 한가지 했으면 commit을 해라

### .gitignore
```bash
*.o 
*.sqlite 
*.bak 
*.old 
.DS_Store 
logs/
```
- 무시해야 하는 바이너리 파일 등을 .gitignore 파일에 기술하면 커밋에서 제외된다.

### Log 확인
> $ git log --oneline --decorate --graph

### 이전 상태로 변경 예
```bash
$ git reset -- [파일이름]
$ git reset --hard [커밋아이디]
$ git reset --hard -> 마지막 commit으로 돌아갈때
$ git reset --hard HEAD^ 한단계 앞
$ git reset --hard HEAD^^ 두단계 앞 (git reset --hard HEAD~2)
$ git reset --hard HEAD^2 (두번째 부모)
```
>- (파일 변경사항은 그대로 두고) add 혹은 commit을 뒤로 돌아가게 하는 용도

### 원격 저장소 연결
```bash
1. 원격 저장소 확인
$ git remote -v

2. github에서 repository 생성

3. local과 remote repository 연결 (일반적으로 원격저장소 이름은 origin으로 세팅함)
$ git remote add origin [깃 원격 저장소 주소]
```
