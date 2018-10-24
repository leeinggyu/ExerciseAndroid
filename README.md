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
