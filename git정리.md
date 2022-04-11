# git 정리

1. Git 설치가이드
2. GUI vs CLI
   1. GUI와 CLI의 정의
   2. CLI를 사용하는 이유
   3. Git Bash를 사용하는 이유

3. 경로
   1. 루트,홈 디렉터리
   2. 절대 경로와 상대 경로

4. 터미널 명령어



### 1.Git 설치가이드

[링크](https://git-scm.com/) < 접속

**※설치할때 Git 경로를 변경하지 않는다 !**

![](C:\Users\TEST\Desktop\git7.png)

![git13](C:\Users\TEST\Desktop\git13.png)

![git15](C:\Users\TEST\Desktop\git15.png)

제외하고 나머진 next로 넘어간다.

설치 완료 후 터미널에서 **git --version** 입력하여 설치된 git 버전 정보 확인 



## 2.GUI 와 CLI의 정의 

GUI (Graphic User Interface) : 그래픽을 통해 사용자와 컴퓨터가 상호 작용 하는 방식

CLI (command Line Interface) : 터미널을 통해 사용자와 컴퓨터가 상호 작용하는 방식



- GUI
  - CLI에 비해 사용하기 쉽지만 단계가 많고 컴퓨터의 성능을 더 많이 소모함

- CLI 
  - CLI는 GUI로는 불가능한 많은 세부적인 기능을 사용 할 수 있음

#### Git bash를 사용하는 이유 

- 명령어의 통일을 위하여 Windows 와 UNIX계열 (맥OS,Linux)의 명령어 차이가 존재 
  - 개발자 입장에서는 Windows보단 UNIX 계열 운영체제 기반의 프로그램이 더 많음
  - 따라서 Git bash를 통해서 UNIX 계열 운영체제의 터미널 명령어를 연습

## 3.경로

- 루트,홈 디렉토리
  - 루트 디렉토리 (Root Directory,  /)
    - 모든 파일과 폴더를 담고 있는 최상위 폴더 (Windows > C드라이브)

- 홈 디렉토리 (Home Directory, ~)

  - 틸드(Tilde)라고도 부르며  , 사용자의 홈 을 의미
    -  Windows : C:/사용자(Users)/현재 사용자 계정
    - Mac : /Users/현재 사용자 계정

  **폴더와 디렉토리는 비슷한 의미로 구분이 무의미하지만**

  특수폴더 (ex: 네트워크환경,내컴퓨터 등) 는 폴더 이지만 디렉토리가 아니라서 

  폴더가 디렉토리보다 넓은 개념이라고 할 수 있다.

