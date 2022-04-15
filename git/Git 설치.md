# Git 설치

[https://git-scm.com/downloads](https://git-scm.com/downloads)

1. 사용 OS 맞춰서 설치    
   
    ![Untitled 1](https://user-images.githubusercontent.com/83447120/163581375-7d6dc6f9-6def-4bfd-8df0-4c16fa57cea8.png)

    
    
2. 설치 옵션 설정
   
    ![Untitled 2](https://user-images.githubusercontent.com/83447120/163581387-e50e8f70-c549-478f-ab8d-71a1504af0ca.png)
   
    
    ![Untitled 3](https://user-images.githubusercontent.com/83447120/163581394-6baafec1-d82b-4b43-a0af-979fa55e6178.png)

   
    
    <aside>
    ➡️ Additional Icons
    
    -On the Desktop : 바탕화면에 아이콘 추가하기
    
    Windows Explorer integration
    -Git Bash Here, Git GUI Here : 폴더에서 깃 을 바로 연결할 수있는 기능추가하기
                
    ![Untitled 4](https://user-images.githubusercontent.com/83447120/163581422-871842ae-d64e-4bac-8756-dafadb12934a.png)

   
    
    Git LFS(Large File Support) : 대용량 파일 지원
    
    Associate .git configuration files with the default text editor : .git* 구성 파일을 기본 텍스트 편집기에 연결
    
    Associate .sh files to be run with Bash : 실행할 .sh 확장자 파일을 bash와 연결
    
    Check daily for Git for Windows updates : 윈도우용 Git를 매일 확인
    
    Add a Git Bash profile to windows terminal :  git bash profile을 윈도우 터미널에 추가
    
    </aside>
    
3. git에서 사용할 기본 편집기 설정
                      
    ![Untitled 5](https://user-images.githubusercontent.com/83447120/163581448-e48f5063-af2c-4974-8a30-aa7a9cba203b.png)

   
    
4. git의 branch 이름 (git init했을 때) 설정
                      
    ![Untitled 6](https://user-images.githubusercontent.com/83447120/163581457-c622445c-d8c3-46b7-a73b-ebe43fd0d76c.png)

    
    초기 branch : master < 선택 추천
    초기 bransh : 사용자가 정한 이름
    
5. 환경 변수 설정
                
    ![Untitled 7](https://user-images.githubusercontent.com/83447120/163581835-91bd905d-fe91-4f9c-b32b-10f7b160118f.png)

    
    깃 명령어를 오직 git bash에서만 사용
    
    git 환경 변수를 등록하고, gitbash, cmd, power shell 등에서 사용 < 선택 추천
    
    cmd의 unix tool에서 사용
    
6. 보안 서버 접속 방식 설정
            
    ![Untitled 8](https://user-images.githubusercontent.com/83447120/163581844-037f9418-7cad-4cae-8ecf-4610c4a423b9.png)

    
    기본 제공되는 openSSH 사용 < 선택 추천
    
    외부 openSSH 사용 
    
7. HTTP 연결 옵션 설정
            
    ![Untitled 9](https://user-images.githubusercontent.com/83447120/163581862-d20785ef-594d-4f76-83c1-a7f7c81b4bc2.png)

    
    openSSL 라이브러리 사용(서버 ca-bundle.crt 파일로 검증) < 선택 추천
    
    윈도우 인증서 저장소를 사용하여 검증
    
8. 텍스트 파일 줄바꿈 부분 설정
    
    🔸윈도우(\r\n) vs 유닉스(\n) 스타일 차이 
            
    ![Untitled 10](https://user-images.githubusercontent.com/83447120/163581877-fcbdebc3-8515-48ca-bb61-af77cdd39528.png)

    
    체크아웃 : 윈도우 스타일, 커밋 : 유닉스 스타일 (OS: 윈도우일경우)
    
    체크아웃 : 변경없이, 커밋 : 유닉스 스타일 (OS :리눅스일경우)
    
    체크아웃, 커밋 : 변경없이
    
9. 터미널 애뮬레이터 설정
            
    ![Untitled 11](https://user-images.githubusercontent.com/83447120/163581884-c619801c-0366-4e40-98e7-3d4aabc5715d.png)

    
    git bahs 기본 터미널 에뮬레이터를 사용
    
    윈도우 기본 콘솔 cmd.exe사용
    
10. git pull 했을 때 설정
            
    ![Untitled 12](https://user-images.githubusercontent.com/83447120/163581894-6f4ac79a-7087-454d-a00c-fda14608e7e2.png)

    
    default < 선택 추천
    
11. 자격증 도우미 설정
                
    ![Untitled 13](https://user-images.githubusercontent.com/83447120/163581902-ee32e301-0802-4693-bba1-c13502a26a38.png)

    
    git 자격증 도우미 < 선택 추천
    없음
    
12. 기타옵션 설정
                
    ![Untitled](https://user-images.githubusercontent.com/83447120/163581912-73cba471-4b20-410f-ac81-9e38759cb029.png)

    
    파일 시스템 캐싱을 사용하여 성능향상 제공
    
    심볼릭 링크를 사용 
    
13. 설치 완료하기
