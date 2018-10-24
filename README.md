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
>- 무시해야 하는 바이너리 파일 등을 .gitignore 파일에 기술하면 커밋에서 제외된다.

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

### git branch
```bash
1. branch 생성(HEAD 에 생김)
$ git branch [브랜치이름]  

1-1. 특정 위치에 branch 생성
$ git branch -f [브랜치이름] [커밋아이디]

2. 로컬 브랜치 확인
$ git branch
$ git branch -v (해당 브랜치의 commit ID도 보임)

3. 원격 브랜치 확인
$ git branch -r 

4. master로 이동 후 merge
$ git checkout -f master
$ git merge [브랜치이름]
```

### git push
```bash
$ git push origin master 
$ git push --force 
```

### git pull
>$ git pull
>- pull = fetch + merge
>- fetch : 원격에서 local 저장소로 가져옴
>- merge : local 저장소로 가져온 내용을 Working Directory에 반영 및 Index에 적용하는 것 (그리하여 git status 명령어로 확인시에 변경사항이 체크되지 않는 것임)

### git clone
>$ git clone [깃 원격 저장소 주소] [로컬 원격 저장소 경로]
>- remote 주소 설정이 자동으로 세팅됨

### git tag
```bash
$ git tag [태깅] [커밋아이디]
$ git push origin [태깅] 
```
>- 실 배포버전을 위한 용도
>- 태깅하고 push하면 github의 release에 올라감
>- 태깅하고 commit해도 HEAD위치가 갱신되지 않는다.

## Markdown 문법
### 제목
```bash
해시태그(#) 뒤에 글자를 붙이면 제목이 됩니다. 해시태그를 여러개(##, ###, ...)를 붙이면 차차로 글자 크기가 줄어듭니다.
    ex) # 제목1
        ## 제목2
        ### 제목3
```        
>- Visual Studio Code의 Markdown Preview 기준으로 확인할 때 최대 6개의 해시태그(#)를 붙이는 것이 가능합니다.
>- 제목 수준으로 크기를 키우고 싶은 글자의 다음 라인에 '='을 넣으면 글자가 제목 수준으로 지정됩니다. ('='를 여러개 넣어도 무방)

### 진하게(Bold)
```bash
    혹은 언더스코어 두개(__), 별표 두 개(**)를 글자의 양 끝에 붙이면 글자를 진하게 지정 가능합니다.
    ex) **진하게**
        __진하게__
```
>- **실제로 Bold가 적용된 모습입니다.**
>- __언더스코어로 적용한 모습__

### 기울이기(Italic)
```bash
    언더스코어 한 개, 혹은 별표 한 개(_, *)를 글자의 양 끝에 붙이면 글자에 기울이기를 적용 가능합니다.
    ex) _기울이기_
        *기울이기*
```
>- _언더스코어로 적용한 기울이기_
>- *별표로 적용한 기울이기*

### 숫자 목록
```bash
    숫자 목록은 항목으로 지정하고 싶은 내용의 앞에 숫자와 닷(.)을 붙이면 적용됩니다.
    따로 들여쓰기를 하지 않더라도 적절히 들여쓰기가 지정됩니다.
    ex) 1. 일
        2. 이
        3. 삼
```
>1. 이렇게 지정됩니다.
>2. 이렇게 지정됩니다.

### 글 머리 기호
```bash
숫자가 아닌 기호로 항목 지정을 할 경우에는 항목으로 지정하고 싶은 항목 앞에 
별표(*) 혹은 하이픈(-), 또는 더하기(+) 기호를 붙입니다.
해당 에디터 기준으로는 별표(*)와 하이픈(-) 더하기(+) 뒤에 공백이 필요합니다. 
그러나 기호들을 혼용하면 문단이 구분되어 간격이 생기므로 통일하는 편이 좋습니다.
ex) * 첫 번째
    * 두 번째
    * 세 번째
```
>- 별표로 지정한 첫번째 항목
>- 별표로 지정한 두번째 항목
>
>- 하이픈으로 지정한 첫번째 항목
>- 하이픈으로 지정한 두번째 항목
>
>- 별표로지정한 항목
>- 더하기로 지정한 항목

### 인용문
```bash
인용문의 경우에는 오른쪽 꺾쇠(>)를 이용합니다.
ex) > 인용문구
```
>- 인용문은 이렇게 지정됩니다.

### 이메일 링크
```bash
이메일 링크는 양쪽을 꺾쇠 괄호(<>)로 묶어 사용합니다.
ex) <test@test.com>
```
>- <test@test.com>

### URL 링크
```bash
URL 링크의 경우도 양쪽을 꺾쇠 괄호(<>)로 묶어 사용합니다. 만일 URL 대신 다른 내용을 링크 내용으로 사용하고 싶다면 링크 앞에 대괄호([]) 안에 사용하고자 하는 내용을, 뒤쪽에 소괄호(()) 안에 링크 주소를 입력합니다.
 ex) <https://github.com>
     [깃허브](https://github.com)
```
>- <https://github.com>
>- [깃허브](https://github.com)

### 이미지 넣기
```bash
이미지의 경우 소괄호(()) 안에 이미지의 URL을 넣으면 적용됩니다.
캡션을 넣으시고 싶은 경우에는 파일 링크 앞에 느낌표와 대괄호를 이용하여 적습니다(![])
ex) ![테스트이미지](https://github.com/cliche90/markdown_tutorial/blob/master/github_logo.png?raw=true)
```
>- ![깃허브 이미지](https://github.com/cliche90/markdown_tutorial/blob/master/github_logo.png?raw=true)

