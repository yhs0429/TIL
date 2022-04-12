git 정리

1. Git 설치가이드
2. GUI와 CLI의 정의
3. Git Bash를 사용하는 이유
3. 경로
   1. 루트,홈 디렉터리
   2. 절대 경로와 상대 경로
4. 터미널 명령어



### 1.Git 설치가이드

[링크](https://git-scm.com/) < 접속

**※설치할때 Git 경로를 변경하지 않는다 !**

![사진](C:\Users\TEST\Desktop\Github\TIL\png\git7.png)

![사진2](C:\Users\TEST\Desktop\Github\TIL\png\git13.png)

![사진2](C:\Users\TEST\Desktop\Github\TIL\png\git15.png)

제외하고 나머진 next로 넘어간다.

설치 완료 후 터미널에서 **git --version** 입력하여 설치된 git 버전 정보 확인 



## 2.GUI 와 CLI의 정의 

- GUI (Graphic User Interface) : 그래픽을 통해 사용자와 컴퓨터가 상호 작용 하는 방식
  - CLI에 비해 사용하기 쉽지만 단계가 많고 컴퓨터의 성능을 더 많이 소모함

- CLI (command Line Interface) : 터미널을 통해 사용자와 컴퓨터가 상호 작용하는 방식
  - CLI는 GUI로는 불가능한 많은 세부적인 기능을 사용 할 수 있음

## 3.Git bash를 사용하는 이유 

- 명령어의 통일을 위하여 Windows 와 UNIX계열 (맥OS,Linux)의 명령어 차이가 존재 
  - 개발자 입장에서는 Windows보단 UNIX 계열 운영체제 기반의 프로그램이 더 많음
  - Git bash를 통해서 UNIX 계열 운영체제의 터미널 명령어를 연습

## 4.경로

- 루트,홈 디렉토리
  - 루트 디렉토리 (Root Directory,  /)
    - 모든 파일과 폴더를 담고 있는 최상위 폴더 
    - Windows > C드라이브
  - 홈 디렉토리 (Home Directory, ~)
    - 틸드(Tilde)라고도 부르며  , 사용자의 홈 을 의미
    - Windows : C:/사용자(Users)/현재 사용자 계정
    - Mac : /Users/현재 사용자 계정
  
  **폴더와 디렉토리는 비슷한 의미로 구분이 무의미하지만**
  
  특수폴더 (ex: 네트워크환경,내컴퓨터 등) 는 폴더 이지만 디렉토리가 아니라서 
  
  폴더가 디렉토리보다 넓은 개념이라고 할 수 있다.
  
- 절대 경로와 상대 경로

  - 절대 경로 : 루트 디렉토리로부터 목적 지점까지 거치는 모든 경로를 작성한 것

    - 윈도우 바탕화면의 절대 경로 C:/users/kyle/Desktop

  - 상대 경로 : 현재 작업하고 있는 디렉토리를 기준으로 계산된 상대적 위치를 작성한 것

    - 현재 작업하고 있는 디렉토리 C:/Users 라고 한다면

    - 윈도우 바탕화면의 상대 경로는 kyle/Desktop 이 된다

    - ./ : 현재 작업하고 있는 폴더를 의미

    - ../ : 현재 작업하고 있는 폴더의 부모 폴더를 의미

      

## 5.터미널 명령어

- touch

  - 파일을 생성하는 명령어

  - 띄어쓰기로 구분하여 여러 파일을 한번에 생성가능 (ex : $ touch a.txt b.txt c.txt)

  - 숨김 파일을 만들기 위해서는 . 을 파일 명 앞에 붙인다 

    

- mkdir
  - make directory
  - 새 폴더를 생성하는 명령어
  - 띄어쓰기로 구분하여 여러 폴더를 한번에 생성가능
  - 폴더 이름 사이에 공백을 넣고 싶다면 따옴표로 묶어서 입력. (ex : $ mkdir 'hi')



- ls
  - list segments
  - 현재 작업 중인 디렉토리의 폴더/파일 목록을 보여주는 명령어(ex : $ ls)
  - -a : all옵션 . 숨김파일 까지 모두 보여준다 (ex : $ ls -a)
  - -l : long옵션 . 용량 ,수정, 날짜 등 파일 정보를 자세히 보여준다(ex : $ls -l)
    -  ls -a -l  all,long 옵션 함께 적용가능
    - ls -al 여러 옵션 축약 가능



- mv
  - move
  - 폴더/파일을 다른 폴더 내로 이동하거나 이름을 변경하는 명령어
    - text.txt를 forder 폴더 안에 넣을 때
      - $mv text.txt folder
    - text1.txt 의 이름을 text2.txt 로 변경할때
      - $mv text1.txt text2.txt
  - 단,다른 폴더로 이동할때는 작성한 폴더가 반드시 있어야 한다. 없으면 이름이 바뀐다.



- cd

  - change directory

  - 현재 작업중인 디렉토리를 변경하는 명령어

  - cd ~ 를 입력하면 홈 디렉토리로 이동한다.(cd라고만 입력해도 가능)

  - cd .. 를 입력하면 부모 디렉토리로 이동 (위로가기)

  - cd - 를 입력하면 바로 전 디렉토리로 이동 (뒤로가기)

    | $cd folder  (현재 작업 중인 디렉토리에 있는 folder 폴더로 이동) |
    | ------------------------------------------------------------ |
    | $cd ../parent/child (상대 경로를 통한 디렉토리 변경)         |
    | $ cd c:/Users/kyle/Desktop (절대 경로를 통한 디렉토리 변경)  |

    

- rm

  - remove

  - 폴더/파일 지우는 명령어

  - GUI와 달리 휴지통으로 이동하지 않고 완전삭제 한다.

  - *(asterisk, wildcard) 를 사용해서 rm *.txt 라고 입력하면 txt 파일 전체를 다 지운다.

  - -r  : recursive 옵션 , 폴더를 지울때 사용

    | $rm test.txt   |
    | -------------- |
    | $ rm -r folder |



- start, open

  - 폴더/파일을 여는 명령어

  - Windows 에서는 start를, Mac에서는 open을 사용 할 수 있다

    | Windows          |
    | ---------------- |
    | $ start test.txt |
    | Mac              |
    | $ open test.txt  |

    

## 유용한 단축키

- 위, 아래 방향키 : 과거의 작성했던 명령어 조회 
- tab : 폴더/파일 이름 자동완성
- ctrl + a : 커서가 맨 앞으로 이동
- ctrl+ e : 커서가 맨 뒤로 이동
- ctrl+w : 커서가 앞 단어를 삭제
- ctrl + l : 터미널 화면을 깨끗하게 청소 (스크롤 올리면 과거 내역 조회 가능)
- ctrl + insert : 복사
- shift+insert : 붙여넣기
