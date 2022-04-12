# Github

- 원격 저장소 (Remote Repository)
  - 로컬 저장소와 원격 저장소 연결
  - 원격 저장소에 업로드



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
