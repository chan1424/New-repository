죄송합니다. 한국어로 README.md 파일 형식에 맞춰 다시 작성해 드리겠습니다.

아래 내용을 복사하여 README.md 파일로 저장하신 후 GitHub에 업로드하시면 됩니다.

Git & GitHub 사용법 정리
이 문서는 한경대학교 ICT로봇기계공학부 최현호 교수님의 '공학설계입문' 수업 내용 을 바탕으로 Git과 GitHub의 핵심 사용법을 정리한 README 파일입니다.


1. Git & GitHub란?

Git: 코드의 변경 이력(버전)을 체계적으로 관리하는 버전 관리 도구입니다. 2005년 리누스 토르발스가 만들었으며 , 이를 통해 파일을 언제 어떻게 수정했는지 추적하고 이전 상태로 되돌릴 수 있습니다.





GitHub: Git으로 관리하는 프로젝트를 온라인에 저장하고 다른 사람들과 협업할 수 있는 클라우드 플랫폼입니다. '개발자들의 SNS' 또는 '클라우드 드라이브'로 비유되기도 합니다.


2. Git 설치 및 최초 설정
설치 과정

다운로드: 웹 브라우저에서 https://git-scm.com에 접속하여 'Download for Windows' 버튼을 클릭해 설치 파일을 받습니다.

설치: 다운로드한 파일을 실행하여 설치를 진행합니다. 설치 과정 중 'Choosing the default editor used by Git' 단계에서는 'Visual Studio Code'를 선택하는 것이 권장됩니다. 나머지 설정은 기본값으로 두고 설치를 완료합니다.


설치 확인: 명령 프롬프트(cmd)나 터미널을 열고 아래 명령어를 입력하여 Git 버전이 출력되는지 확인합니다.

Bash

git --version
최초 사용자 정보 설정
Git을 처음 사용할 때는 커밋(버전 기록)에 사용할 사용자 이름과 이메일 주소를 설정해야 합니다.

Bash

git config --global user.name "사용자 이름"
git config --global user.email "사용자 이메일"
3. 로컬 프로젝트를 GitHub에 업로드하기
진행 순서

GitHub 저장소 생성: GitHub에 로그인하여 새로운 저장소(Repository)를 생성합니다. 

Repository name을 입력하고 Public으로 설정한 뒤 생성합니다.


로컬 저장소 초기화: 내 컴퓨터의 프로젝트 폴더에서 터미널을 열고 아래 명령어를 실행합니다. 

.git 폴더가 생성되며 버전 관리가 시작됩니다.

Bash

git init

파일 추가 (Staging): 변경된 모든 파일을 커밋할 준비 단계인 스테이징(staging) 영역으로 추가합니다. 

.은 모든 파일을 의미합니다.

Bash

git add .

버전 기록 (Commit): 스테이징된 파일들을 하나의 버전으로 기록합니다. 

"메시지" 부분에는 해당 버전에서 변경된 내용을 요약하여 작성합니다.

Bash

git commit -m "first commit"

원격 저장소 연결: 내 로컬 저장소와 GitHub에서 생성한 원격 저장소를 연결합니다. 

origin은 원격 저장소의 별칭입니다.

Bash

git remote add origin <GitHub 저장소 URL>

업로드 (Push): 로컬에 커밋된 내용을 원격 저장소로 업로드합니다. 

-u 옵션은 앞으로 git push만 입력해도 자동으로 해당 경로로 푸시되도록 설정합니다.

Bash

git push -u origin master
4. 파일 수정 및 추가 업로드
프로젝트 파일을 수정한 뒤에는 아래 3가지 명령어를 순서대로 실행하여 변경사항을 GitHub에 업데이트할 수 있습니다.

Bash

git add .
git commit -m "수정한 내용 요약"
git push
5. .gitignore 활용하기

venv 같은 가상환경 폴더나 용량이 큰 파일 등, GitHub에 올리지 말아야 할 파일 및 폴더를 관리하기 위해 .gitignore 파일을 사용합니다.

프로젝트 최상위 폴더에 

.gitignore 파일을 생성합니다.

파일 내부에 업로드에서 제외하고 싶은 폴더명(끝에 

/ 추가)이나 파일명을 한 줄씩 입력하고 저장합니다.

.gitignore 파일을 저장한 후, add, commit, push를 진행하면 지정된 파일/폴더는 업로드되지 않습니다.

6. 협업을 위한 브랜치(Branch) 사용법
브랜치는 독립적인 개인 작업 공간으로, 여러 사람이 동시에 다른 기능을 개발할 때 메인 코드(master)에 영향을 주지 않고 작업할 수 있게 해줍니다.

브랜치 생성 및 이동:

Bash

# 'update-name' 이라는 이름의 브랜치 생성
git branch update-name

# 생성한 브랜치로 이동
git checkout update-name
브랜치에서 작업 및 푸시: 해당 브랜치에서 코드를 수정하고 add, commit 한 뒤, 아래 명령어로 원격 저장소의 해당 브랜치에 업로드합니다.

Bash

git push origin update-name

Pull Request (PR) 생성: GitHub 저장소 페이지에서 "Compare & pull request" 버튼을 클릭하여, 내가 작업한 브랜치의 코드를 master 브랜치에 병합(Merge)해달라고 요청하는 PR을 생성합니다.

병합 및 브랜치 삭제: 코드 리뷰 후 문제가 없으면 Merge pull request 버튼을 눌러 코드를 병합합니다. 병합이 완료된 브랜치는 삭제해도 무방합니다.

7. 기타 유용한 명령어

git clone <URL>: 원격 저장소의 프로젝트를 내 컴퓨터로 복제합니다.


git pull: 원격 저장소의 최신 변경 내용을 로컬 저장소로 가져와 병합합니다.


git log: 현재까지의 커밋 기록을 확인합니다.


git reset --hard HEAD~1: 가장 최근의 커밋을 취소하고 해당 버전으로 완전히 되돌아갑니다.



git revert HEAD: 가장 최근 커밋의 변경 내용을 취소하는 새로운 커밋을 생성하여, 기록을 남기면서 안전하게 이전 상태로 되돌립니다.