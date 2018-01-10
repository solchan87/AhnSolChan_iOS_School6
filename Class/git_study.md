# Git 명령어 정리
> 2018.01.10 업데이트

## Git 이란

GIt은 프로그램 등의 소스 코드 관리를 위한 분산 버전 관리 시스템이다. 빠른 수행 속도에 중점을 두고 있는 것이 특징이다. 최초에는 리누스 토르발스가 리눅스 커널 개발에 이용하려고 개발하였으며, 현재는 다른곳에서도 널리 사용되고 있다. 깃의 작업 폴더는 모두, 전체 기록과 각 기록을 추적할 수 있는 정보를 포함하고 있으며, 완전한 형태의 저장소이다로 네트워크나 중앙 서버에 의존하지 않기 때문에 오프라인 상태에서도 로컬 커밋이 가능한 장점을 가지고 있다.

## Git 주요 특징

* **빠른 속도와 성능**  
  git은 VCS보다 설치가 쉬우며, 로컬에서 작업하기 때문에 속도가 매우 빠르고 branch와 merge가 빠른 장점을 가지고 있다.
* **분산 작업**  
  Git은 구조가 매우 유연하기 때문에 여러 개발자가 함께 작업하는 방식을 더 다양하게 구성할 수 있다.
* **데이터 보장성**  
  git에서는 모든 파일을 암호화시켜주며, 하나의 bit도 틀리지 않게 저장한다. 또한, 체크썸이라는 검사를 거쳐 commit 히스토리를 관리할 수 있습니다.
* **Staging area**  
  add를 통해 Staging area에 저장하여, 서버에 업로드할 준비를 하기 때문에, 일부분만 커밋하거나 충돌 시 충돌 파일만 커밋하여 해결할 수 있다.
* **브랜치(branch) 모델**  
  git은 브랜치 모델을 통해 원본을 빠르게 복사하거나 합칠 수 있으며, 통째로 복사한 코드를 원본 코드와 상관 없이 독립적으로 개발하고 합칠 수 있다.

## Git 명령어

#### 설정과 초기화  
`git config - -global user.name “Your name”`  
전역 사용자의 이름을 정한다.  

`git config - -global user.email “Your email address”`  
전역 사용자의 메일 주소를 정한다.  

`git config user.name “Your name”`  
저장소별 사용자 이름 정한다.  

`git config user.email “Your email address”`  
저장소별 사용자 이메일을 정한다.  

`git config - -global - -list`  
전역 설정 정보를 조회한다.  

`git config - -list`  
저장소별 설정 정보를 조회한다.  

`git config - -global color.ui “auto”`  
git 출력결과의 색상을 활성화한다.  

`git init`  
git 저장소 초기화한다.  

`git clone <저장소 url>`  
git을 새로운 저장소에 복사한다. 

`git remote add <원격 저장소> <저장소 url>`  
새로운 원격 저장소 추가한다.  

#### 기본 사용 명령어
`git add <파일>`  
Staging area에 파일을 스테이징 한다.

`git commit -m “<메시지>”`  
Staging area에 있는 파일을 commit하고 메세지를 정한다.

`git commit -m “<메시지>” - -amend`  
마지막 커밋을 고친다.

`git commit -C HEAD - -amend`  
이전 커밋을 수정하고 고친다.

#### 브랜치
`git branch`  
지역 브랜치 목록을 본다.  

`git branch -r`  
원격 브랜치 목록을 본다.  

`git branch -a`  
지역과 원격을 포함한 모든 브랜치 목록을 본다.  

`git branch <새로운 브랜치>`  
현재 브랜치에 새로운 브랜치를 생성한다.  

`git checkout <새로운 브랜치>`  
다른 브랜치로 체크아웃 한다.  

`git merge <브랜치>`  
다른 브랜치를 현재 브랜치로 합친다.  

`git merge - -no-commit <브랜치>`  
커밋하지 않고 브랜치를 합친다.  

`git cherry-pick <커밋명>`  
커밋을 선택하여 합친다.  

`git branch -d <삭제할 브랜치>`  
삭제할 브랜치가 현재 브랜치에 합쳐졌을 경우에 쓴다. 

`git branch -D <삭제할 브랜치>`  
삭제할 브랜치가 현재 브랜치에 합쳐지지 않았어도 사용할 수 있다.  

#### Git 이력
`git log`  
git의 모든 이력을 확인할 수 있다.  

`git log -p`  
변경 사항을 보여주는 패치와 함께 로그를 표시한다.  

`git log -1`  
로그 결과가 1개만 보이도록 갯수를 제한한다.  

`git log -20 -p`  
로그 결과가 패치와 함께 20만 보이도록 갯수를 제한한다.  

