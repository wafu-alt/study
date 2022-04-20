# git bash 명령어

[https://git-scm.com/docs](https://git-scm.com/docs)

[https://learngitbranching.js.org/?locale=ko](https://learngitbranching.js.org/?locale=ko) 

도움되는 사이트

- 초기 확인
    - git --version 깃의 버젼 확인 (설치 유무도 확인 가능함)
    - git version
        
        ![Untitled](https://user-images.githubusercontent.com/83447120/164225704-1f37c03c-0a8a-42f1-95b1-6588bf0b7619.png)
        
- git 명령어
    - git config --h
- 유저 설정
    - git config --global user.name “git아이디”
    - git config --global user.email “git가입시 메일”
- 폴더 선택 후 git 초기화 하기 , 저장소 생성
    - git init
    - git init hello  : hello라는 저장소 생성함
- git 유저 네임 등록
    - git config --global [user.name](http://user.name/) "<이름>" : git관련 작업 기록에 남는 이름 등록
    git config --global [user.name](http://user.name/) "name" : name이라는 이름으로 등록
    - git config --global user.email "<이름>" : git관련 작업 기록에 남는 메일 등록
    git config --global user.email "name[@](mailto:rabbit@elice.io)gmail.com" : "name[@](mailto:rabbit@elice.io)gmail.com"이라는 메일 등록
- git 설정 확인
    - git config --list
- git 상황 알아보기
    - git status
    - git workflow 아래 사진과 같이 구조로 되어있음
    참조 : [https://www.youtube.com/watch?v=Z9dvM7qgN9s](https://www.youtube.com/watch?v=Z9dvM7qgN9s)
        
  ![Untitled 1](https://user-images.githubusercontent.com/83447120/164225760-78de8965-5664-47be-95c8-b46c9048e7ed.png)
        
- 작업 파일 git에 트랙킹 하기
    - git add 작업파일.확장자
    예시) git add a.txt
    - git add *.txt
    - git add * 또는 git add . : 전체를 staging area에 올릴 수 있음
        - ↔️ git rm --cached *.txt : txt확장자 파일 untracked
- 트랙킹한걸 되돌리기
    - git reset 파일.확장자
    예시) git reset file.txt : file.txt라는 파일을 트랙킹을 취소함
- git 커밋 ( staging area → repository)
    - git commit -m 설명 :
        
        예시) git commit -m “First commit”     :  First commit 이라는 제목을 붙임
        
        - git commit -m “타이틀부분” -m “설명부분”
        git commit -m “first commit” -m “sub Description”
    - 트랙킹 + 커밋 동시에 하기 : git commit -am 설명 
    예시) git commit -am “2 commit” :
- git 커밋메세지 수정
    - git commit --amend -m “수정메세지” 
    예시) git commit --amend -m “modified message”
- git 커밋 상황 보기
    - git log 
    commit : 16진수문자열(체크성,커밋아이디) 
    Author : 유저 이름, 메일주소
    Date : 실행할 날짜
    커밋 메세지 표기
    - git log --graph : 브랜치 상태를 그래프로 확인 가능하다
- git branch
    - git branch : 현재 사용하고 있는 branch들을 확인 할 수있다 현재 속해있는 곳은 *로 표시된다.
    - git branch 브랜치명 : 브랜치명으로 브랜치를 생성할 수 있다.
    git branch branch1 : branch1로 생성
    - git checkout 브랜치명 : 다른 브랜치로 갈아탈 수 있다
    git branch branch1 : branch1로 이동
    - git branch -d 브랜치명 : 브랜치 삭제
    git branch branch2 : branch2를 삭제
- git merge 브랜치 합치기
    - 브랜치는 주라인으로 이동 후 합쳐야한다
    1순위 : master / main , 2순위 : 주 브랜치
    - git merge 브랜치명 : 현재 있는 브랜에 브랜치명을 합친다
    git merge branch1  : branch1을 현재 있는 브랜치를 기준으로 합친다
    master branch상태에서 git merge branch1을 해서 추가 사항만 있다면 : Fast-forward라고 부른다
    - master와 branch1이 있는 branch1에서 추가 사항과 기존있는 코드를 건드리면 : merge conflict이라고 에러 뜬다 master와 branch1코드가 겹치는 서로 달라서 그러므로 사용자가 직접 수정해야한다. 그 후 git add, git commit으로 다시 합쳐야한다.
    소스코드 수정 후 → git add sourcefile.txt → git commit -m “modified code” → git merge branch1
    - 기존파일에서 코드 충돌, 새 파일 코드를 쓰기로 사용, 겹치는 부분만 새파일 코드로 바꿈
    
    ```jsx
    git branch branch1 
    git checkout branch1
    git add newfile.txt
    git commt -m “add code file”
    git checkout master
    git merge newfile.txt
    ->>> merge conflict / crash file : sourcefile.txt
    ->>> check sourcefile.txt modified code 
    git add sourcefile.txt
    git commit -m "modified code"
    git checkout master
    git merge branch1
    git branch -d branch1
    
    ```
    
- git 되돌리기
    - git reset 브랜치명 : 트래킹을 취소할때도 쓰지만 branch를 되돌릴때도 쓴다
    git reset  main : main있는 쪽으로 되돌아감
    - git revert 브랜치명 : 되돌리고 내역을 남기면서 새로 만든다
    git revert HEAD :  HEAD있는 곳을 복사하고 변경된 내용을 남길 수 있다

참조 : [https://www.zerocho.com/category/Git/post/581042fdcae2d100152ceae6](https://www.zerocho.com/category/Git/post/581042fdcae2d100152ceae6)

- github 레파지토리와 연결 시켜주기
    - git clone 깃레파지토리https주소 : 깃에 있는 레포지토리를 복사해옴
    - git remote add 이름 https://github.com/깃헙아이디/레파지토리이름.git
    예시) git remote add origin https://github.com/wafu-alt/terminal-test.git
    origin이라는 branch로 가지고옴
        - ↔**git remote remove origin : 원격저장소 (origin을) 지움**
    - git remote  : 연결된 이름 알 수 있음
    - git remote -v  : 현재 연결된 레파지토리 주소 나옴
- github 레파지토리에 가져오기
    - git pull : 원격저장소에서 가져오면서 병합함 , git lod --all로 확인함
    git pull origin master : origin을 master branch로 가져와서 병합함
    - git fetch : 원격저장소에서 가져와서 git log로 확인하고 merge해야함, git merge origin/master
    git fetch origin master : origin을 master로 가져옴
    git merge origin/master : 현재 브랜치 기준으로 origin/master와 병합
- github 레파지토리에 올리기
    - git push :
    예시)  git push origin master : origin 이름의 원격저장소 master branch에 저장함
- 원격 저장소 내용이 바뀌었을 때 푸시하는 법

```jsx
git push origin master 
->>> 에러 확인
git pull origin master
->>> 어느파일에서 에러나는지 확인
git diff
->>> 파일의 어느 코드에서 충돌되는지 확인
->>> 코드 수정
git add 수정한파일
git commit -m "수정한 파일 재 업"
git push origin master
```

참조 : [https://www.zerocho.com/category/Git/post/581b7122809622001722fc0b](https://www.zerocho.com/category/Git/post/581b7122809622001722fc0b)

- 파일 내용 수정했을 때
    - git diff : 수정된 내용을 보여줌
- 수정했던 내용 되돌리기
    - git checkout 파일명
    예시) git checkout a.txt : a.txt가 수정이 되었다가 다시 이전 버젼으로 돌아감
- 수정해서 add까지한 것을 되돌리기
    - git reset 파일명
    - 예시) git reset a.txt : (토글 확인할 것) add해서 statging area에서
        
        !![Untitled 2](https://user-images.githubusercontent.com/83447120/164225885-eebafb27-f8fc-4f67-9e0c-054bca1ac82b.png)
        
        ![Untitled 3](https://user-images.githubusercontent.com/83447120/164225899-cfb465c3-0b8c-4915-8794-3eb5666678f6.png)
        
    
- 현재 commit hash tag확인하기
    - git log pretty=oneline
- commit 특정 hash tag로 되돌아가기
    - git reset --soft “16진수 문자열”
    - git reset --soft "d74c4fca443dd29244b31bad6737edd3d3cc9746”
- commit hash tag로 삭제하기
    - git reset --hard “16진수 문자열”
    git reset --hard "9d46f1514b36dad6947508ffeb5754330ffb2c2b”
    

### 깃헙에서 처음 레파지토리 만들면 나옴

![Untitled 4](https://user-images.githubusercontent.com/83447120/164225924-32e9b76f-5be4-444d-9ca1-2ac7d65ee4fc.png)

```bash
echo "# terminal-test" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/wafu-alt/terminal-test.git
git push -u origin main
```

```bash
git remote add origin https://github.com/wafu-alt/terminal-test.git
git branch -M main
git push -u origin main
```
