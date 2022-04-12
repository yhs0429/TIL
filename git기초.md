# git 기초

[1] Git 초기 설정

​		(0)Git 설치가이드

[2]Git 기본 명령어

​		(0)로컬 저장소

​		(1)git init

​		(2)git status

​		(3)git add

​		(4)git commit

​		(5)git log

​		(6)Git 명령어

## [1]Git 초기 설정

### Git 설치가이드

[링크](https://git-scm.com/) < 접속

**설치할때 Git 경로를 변경하지 않는다 !**

설치 완료 후 터미널에서 **git --version** 입력하여 설치된 git 버전 정보 확인 

### 초기 설정

- 최초 한번만 설정 

  - 누가 커밋 기록을 남겼는지 확인할수있도록 이메일,이름 설정

    $git config --global user.name "이름"

    $git config --global user.email "메일이름"

  - 작성자 수정 할땐 이름,메일 주소만 다르게 하여 동일하게 입력

## [2]Git 기본 명령어

### (0)로컬 저장소

![Untitled](C:\Users\TEST\Desktop\Github\TIL\png\Untitled.png)

- Git은 Working Directory → Staging Area → Repository 과정으로 버전 관리를 수행
- Working Directory (= Working Tree) : 사용자의 일반적인 작업이 일어나는 곳
- Staging Area (= Index) : 커밋을 위한 파일 및 폴더가 추가되는 곳
- Repository : Staging area에 있던 파일 및 폴더의 변경사항(커밋)을 저장하는곳

## (1)git init

$ git init
Initialized empty Git repository in C:/Users/TEST/Desktop/git init/.git/

1@sunny MINGW64 ~/Desktop/git init (master)

- 현재 작업중인 디렉토리를 Git으로 관리한다는 명령어
- .git 이라는 숨긴 폴더를 생성 , 터미널에는 (master = main) 라고 표기 

```!주의사항
!주의 사항
1. 이미 git 저장소인 폴더 내에 또 다른 Git 저장소를 만들지 않는다 (중첩금지)
   터미널에 master가 있다면 git init을 절대 입력하지말것
2.절대로 홈 디렉토리에서 git init 을 하지 않는다. 터미널의 경로가 ~ 인지 확인 필수!!
```

## (2)git status

$ git status
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)

1@sunny MINGW64 ~/Desktop/git init (master)

- Working Directory와 Staging Area에 있는 파일의 현재 상태를 알려주는 명령어

- 작업을 시행하기 전 수시로 status로 확인하면 좋다

- 상태

  1. Untracked : Git이 관리하지 않는 파일 (한번도 Staging Area에 올라간 적 없는파일)

  2. Tracked : Git이 관리하는 파일

     a.  Unmodified : 최신상태

     b. Modified : 수정되었지만 아직 Staging Area에는 반영하지 않은 상태

     c. Staged : Staging Area에 올라간 상태![Untitled](C:\Users\TEST\Desktop\Github\TIL\png\Untitled.png)

### (3)git add

```#특정 파일```

$git add a.txt

```#특정 폴더```

$git add my_folder/

```현재 디렉토리에 속한 파일/폴더 전부```

$git add.



- Working Directory에 있는 파일을 Staging Area로 올리는 명령어

- Git이 해당 파일을 추적(관리)할 수 있도록 만든다

- Untracked, Modified → Staged 로 상태를 변경

- 예시

  ```$ touch a.txt b.txt
  $ touch a.txt b.txt
  
  
  $ git status
  
  On branch master
  
  No commits yet
  
  Untracked files:   ```#트래킹 되고 있지 않는 파일 목록```
    (use "git add <file>..." to include in what will be committed)
          a.txt
  
  		b.txt
  
  nothing added to commit but untracked files present (use "git add" to track)
  ```

  

  ------

  ```
         $ git add a.txt
         
  		$ git status
  		
  		On branch master
  
  		No commits yet
  
  		Changes to be committed:  ```#커밋 예정인 변경사항(Staging Area)```
  		  (use "git rm --cached <file>..." to unstage)
    		      new file:   a.txt
  
  		Untracked files: ```#트래킹 되고 있지 않은 파일```
  		  (use "git add <file>..." to include in what will be committed)
  		       b.txt



### (4)git commit

```$ git commit -m '커밋해'
[master (root-commit) a703f39] 커밋해
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 a.txt
```

- Staging Area에 올라온 파일의 변경사항을 하나의 버전(커밋)으로 저장하는 명령어
- 커밋메세지는 변경사항을 잘 나타낼수있도록 작성한다
- 각각의 커밋은 고유의 해시 값을 ID로 갖는다
- root-commit 은 해당 커밋의 최초에만 뜬다



### (5)git log

``` 
$ git log
commit a703f391e94255b6abc4b65416fe5bb6465edbc1 (HEAD -> master)
Author: yhs0429 <gyensdl2@gmail.com>
Date:   Tue Apr 12 22:36:03 2022 +0900

    커밋해
```

- 커밋의 내역(```ID, 작성자, 시간, 메세지 등```)을 조회할 수 있는 명령어
- 옵션
  - ```--oneline``` : 한줄로 축약해서 보여준다
  - ```--graph```: 브랜치와 머지내역을 그래프로 보여준다
  - ```--all``` : 현재 브런치를 포함한 모든 브랜치의 내역을 보여준다
  - ```--reverse``` : 커밋 내역의 순서를 반대로 보여준다 (최신이 가장 아래)
  - ```-p``` : 파일의 변경 내용도 같이 보여준다
  - ```-숫자``` : 원하는 갯수만큼의 내역을 보여준다 

### (6)한눈에 보는 Git 명령어

![Untitled (3)](C:\Users\TEST\Desktop\Github\TIL\png\Untitled (3).png)