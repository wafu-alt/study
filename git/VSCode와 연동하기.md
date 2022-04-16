# VSCode와 연동하기

1. VSCode 실행하기
2. 설정 ( ctrl + , )  → json으로 검색
    
    ![Untitled 1](https://user-images.githubusercontent.com/83447120/163660370-061bec04-e606-4031-a789-65f5b5b4d703.png)
    
3. settings.json에서 아래 코드 붙여넣기
    
    ```jsx
    "terminal.integrated.profiles.windows": {
            "GitBash": {
                "path":["Git Bash가 설치된 경로"],
                "icon":"terminal-bash"
            },
     
            "PowerShell": {
                "source": "PowerShell",
                "icon": "terminal-powershell"
            },
            "Command Prompt": {
                "path": [
                    "${env:windir}\\Sysnative\\cmd.exe",
                    "${env:windir}\\System32\\cmd.exe"
                ],
                "args": [],
                "icon": "terminal-cmd"
            },
     
     
        },
        "terminal.integrated.defaultProfile.windows": "GitBash",
    ```
    
    예시)
    
    ![Untitled 2](https://user-images.githubusercontent.com/83447120/163660376-52fd7e69-ce62-48d4-b823-c10111554e73.png)
    
    단, "terminal.integrated.defaultProfile.windows": "GitBash” 은 중복될 수 있으므로 안쓰는 부분은 주석 처리
    
4. 설정 ( ctrl + , )  → terminal.integrated.shell.windows 검색  → GitBash 로 설정
    
    ![Untitled 3](https://user-images.githubusercontent.com/83447120/163660378-16ecad65-8c80-4331-a44b-e7bfb2631d4d.png)
    
5. 설정 ( ctrl + , )  →  Terminal:Explorer Kind 검색  → external 로 설정
    
    ![Untitled 4](https://user-images.githubusercontent.com/83447120/163660380-77caeb98-72c6-4f9f-9b41-92306af90730.png)
    
6. vscode 재부팅
7. 새 터미널 실행 ( ctrl + shift + ` ) 
    
    ![Untitled](https://user-images.githubusercontent.com/83447120/163660381-cfbe9762-7be0-421a-8429-981d0c0ce5b1.png)
    

## 플러그인 추천

vscode에서 ctrl+x에서 플러그인

- **`Prettier - Code formatter` 를 설치해서 줄 바꿈 이쁘게 할 수 있음**

- **`Live Server` 코드 고치고 웹에서 새로고침 안되도 반영됨**

- **`Auto Rename Tag` 여는태그 고치면 닫는 태그도 고쳐줌**
