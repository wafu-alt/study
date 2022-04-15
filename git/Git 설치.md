# Git 설치

[https://git-scm.com/downloads](https://git-scm.com/downloads)

1. 사용 OS 맞춰서 설치
    
    ![Untitled](Git%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20f48a9/Untitled.png)
    
2. 설치 옵션 설정
    
    ![Untitled](Git%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20f48a9/Untitled%201.png)
    
    ![Untitled](Git%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20f48a9/Untitled%202.png)
    
    <aside>
    ➡️ Additional Icons
    
    -On the Desktop : 바탕화면에 아이콘 추가하기
    
    Windows Explorer integration
    -Git Bash Here, Git GUI Here : 폴더에서 깃 을 바로 연결할 수있는 기능추가하기
    
    ![Untitled](Git%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20f48a9/Untitled%203.png)
    
    Git LFS(Large File Support) : 대용량 파일 지원
    
    Associate .git configuration files with the default text editor : .git* 구성 파일을 기본 텍스트 편집기에 연결
    
    Associate .sh files to be run with Bash : 실행할 .sh 확장자 파일을 bash와 연결
    
    Check daily for Git for Windows updates : 윈도우용 Git를 매일 확인
    
    Add a Git Bash profile to windows terminal :  git bash profile을 윈도우 터미널에 추가
    
    </aside>
    
3. git에서 사용할 기본 편집기 설정
    
    ![Untitled](Git%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20f48a9/Untitled%204.png)
    
4. git의 branch 이름 (git init했을 때) 설정
    
    ![Untitled](Git%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20f48a9/Untitled%205.png)
    
    초기 branch : master < 선택 추천
    초기 bransh : 사용자가 정한 이름
    
5. 환경 변수 설정
    
    ![Untitled](Git%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20f48a9/Untitled%206.png)
    
    깃 명령어를 오직 git bash에서만 사용
    
    git 환경 변수를 등록하고, gitbash, cmd, power shell 등에서 사용 < 선택 추천
    
    cmd의 unix tool에서 사용
    
6. 보안 서버 접속 방식 설정
    
    ![Untitled](Git%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20f48a9/Untitled%207.png)
    
    기본 제공되는 openSSH 사용 < 선택 추천
    
    외부 openSSH 사용 
    
7. HTTP 연결 옵션 설정
    
    ![Untitled](Git%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20f48a9/Untitled%208.png)
    
    openSSL 라이브러리 사용(서버 ca-bundle.crt 파일로 검증) < 선택 추천
    
    윈도우 인증서 저장소를 사용하여 검증
    
8. 텍스트 파일 줄바꿈 부분 설정
    
    🔸윈도우(\r\n) vs 유닉스(\n) 스타일 차이 
    
    ![Untitled](Git%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20f48a9/Untitled%209.png)
    
    체크아웃 : 윈도우 스타일, 커밋 : 유닉스 스타일 (OS: 윈도우일경우)
    
    체크아웃 : 변경없이, 커밋 : 유닉스 스타일 (OS :리눅스일경우)
    
    체크아웃, 커밋 : 변경없이
    
9. 터미널 애뮬레이터 설정
    
    ![Untitled](Git%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20f48a9/Untitled%2010.png)
    
    git bahs 기본 터미널 에뮬레이터를 사용
    
    윈도우 기본 콘솔 cmd.exe사용
    
10. git pull 했을 때 설정
    
    ![Untitled](Git%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20f48a9/Untitled%2011.png)
    
    default < 선택 추천
    
11. 자격증 도우미 설정
    
    ![Untitled](Git%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20f48a9/Untitled%2012.png)
    
    git 자격증 도우미 < 선택 추천
    없음
    
12. 기타옵션 설정
    
    ![Untitled](Git%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20f48a9/Untitled%2013.png)
    
    파일 시스템 캐싱을 사용하여 성능향상 제공
    
    심볼릭 링크를 사용 
    
13. 설치 완료하기