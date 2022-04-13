# Github

- 원격 저장소 (Remote Repository)
  - 로컬 저장소와 원격 저장소 연결
  - 원격 저장소에 업로드

- Clone , pull
- Branch
- Branch Merge
- Git workflow

``` 
기본 브랜치 main > master 변경 하는법
1. 우측상단 프로필 클릭
2. Settings 클릭
3. Repositories 클랙
4. Repository default branch 입력 창에서 main 지우고 master 
```



## 원격 저장소 (Remote Repository)

로컬 저장소와 원격 저장소 연결

1. 원격 저장소(Github) 주소 복사

2. git init을 통해 폴더를 로컬 저장소로 만든다

``` 
$ git init
Initialized empty Git repository in C:/Users/sunny/TIL/.git/
```

 	3. git remote
 	 - 로컬 저장소에 원격 저장소를 ```등록,조회,삭제```할 수있는 명령어

​         1. 원격 저장소 등록

​			git remote add <이름> <주소> 형식으로 작성

``` 
$ git remote add origin https://github.com/yhs0429/TIL.git

[풀이]
git 명령어를 작성할건데, remote(원격 저장소)에 add(추가) 한다.
origin이라는 이름으로 https://github.com/yhs0429/TIL.git라는 주소의 원격 저장소를
```

​		2.원격 저장소 조회

``` 
$ git remote -v
origin  https://github.com/yhs0429/TIL.git (fetch)
origin  https://github.com/yhs0429/TIL.git (push)
```

​		3.원격 저장소 연결 삭제

​			```git remote rm <이름>``` 혹은 ```git remote remove <이름>```  으로 작성

```
$git remote rm origin
$git remote remove origin

[풀이]
git 명령어를 작성할건데, remote(원격저장소)와의 연결을 rm(remove, 삭제)한다.
그 원격 저장소의 이름은 origin이다.
```



## 원격 저장소에 업로드

- 파일을 업로드 하는게 아니라 커밋을 업로드 하는것
- 로컬저장소에서 커밋을 생성해야 원격 저장소에 업로드 할 수 있다



1. 로컬 저장소에서 커밋 생성

   ``` 
   # 현재 상태 확인
   $ git status
   On branch master
   
   No commits yet
   
   Untracked files:
     (use "git add <file>..." to include in what will be committed)
           a.txt
   
   
   $ git add a.txt
   
   
   
   $ git commit -m '커밋'
   [master (root-commit) 9590a28] 커밋
    2 files changed, 1 insertion(+)
    create mode 100644 a.txt
    create mode 100644 test.md        
   
   
   #커밋 확인
   $ git log --oneline
   9590a28 (HEAD -> master) 커밋
   ```

   

2. git push
   - 로컬 저장소의 커밋을 원격 저장소에 업로드하는 명령어
   - git push <저장소 이름> <브랜치 이름> 
   - -u 옵션을 사용하면 두번째 커밋부터는 저장소 이름 , 브랜치 이름 생략 가능

```
$git push origin master

[풀이]
git 명령어를 사용하여 origin이라는 이름의 원격 저장소의 master 브랜치에 push 한다.

-------------------------------------------

$git push -u origin master
이후에는 $git push 라고만 작성해도 push가 된다.
```



![git push](C:\Users\TEST\Desktop\Github\TIL\png\git push.png)

## clone , pull

- ### 원격 저장소 가져오기

  - #### git clone

    - 원격 저장소의 커밋내역을 모두 가져와서 , 로컬 저장소를 생성하는 명령어 
      - (처음에 한번만 실행 = git init)
    - git clone 명령어를 사용하면 원격저장소를 통째로 복제해서 내 컴퓨터로 옮길 수 있다
    - git clone <원격 저장소 주소>
    - git clone 으로 생성한 로컬 저장소는 git init 과 git remote add 가 이미 되어있음

```
$git clone https://github.com/yhs0429/TIL.git

<풀이>
github의 yhs0429라는 계정의 TIL 원격 저장소를 복제하여 내 컴퓨터에 TIL이라는 로컬저장소를 생성한다
```



- git pull
  - 원격 저장소의 변경 사항을 가져와서 , 로컬 저장소를 업데이트 하는 명령어
    - git push 랑 정반대
  - 로컬 저장소와 원격 저장소의 내용이 완전 일치하면 git pull 해도 변화 없음
  - git pull <저장소 이름> <브랜치 이름>

```
$git pull origin master

<풀이>
git 명령어로 origin이라는 원격 저장소의 master 브랜치의 내용을 가져온다
```



``` 
<git clone>
$git clone https://github.com/yhs0429/TIL.git
<git push 새 파일 생성 후>
$touch 123.md
$git add .
$git commit -m '새로운파일 생성'
$git push origin master
<git pull>
```



## Branch

- Branch는 나뭇가지 처럼 여러갈래로 작업공간을 나누어 ```독립적으로```작업할 수 있도록 도와주는 Git의 도구
- 브랜치는 독립 공간을 형성하기 때문에 원본(master)에 대해 안전하다
- Git은 브랜치를 만드는 속도가 빠르고 용량도 적게 든다
- 하나의 작업에 하나의 브랜치로 나뉘게되어 체계적인 개발이 가능



### (1) git branch

- 브랜치 ```조회,생성,삭제 등``` 브랜치와 관련된 Git 명령어

```
#브랜치 목록 확인
$git branch

#원격 저장소의 브랜치 목록 삽입
$git branch -r

#새로운 브랜치 생성
$git branch <브랜치이름>

#특정 커밋 기준으로 브랜치 생성
$git branch <브랜치이름> <커밋ID>

#특정 브랜치 삭제
$git branch -d <브랜치이름> #병합된 브랜치만 삭제 가능
$git branch -D <브랜치이름> #(주의)강제 삭제 (병합되지않은 브랜치도 삭제가능)
```



### (2) git switch

- 현재 브랜치에서 다른 브랜치로 ```HEAD```를 이동시키는 명령어

```
#다른 브랜치로 이동
$git switch <다른 브랜치 이름>

#브랜치를 새로 생성과 동시에 이동
$git switch -c <브랜치이름>

#특정 커밋 기준으로 브랜치 생성과 동시에 이동
$git switch -c <브랜치이름> <커밋ID>
```

git switch 하기 전에 워킹
