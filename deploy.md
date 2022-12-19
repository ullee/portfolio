## 자체 개발 배포툴

![image](https://user-images.githubusercontent.com/48572149/208466242-19edef74-2511-4955-91bb-90165b8a634f.png)

> EC2 Tag:Group 에 ID를 지정하여 배포할 대상 서버를 그룹핑 합니다.
> 
> 그룹화 된 배포서버에 AWS SDK - RunShellCommnad() 메소드로 git 명령을 수행 합니다.
> 
> Git 배포 명령 이외에 추가 명령어(ex. npm build)가 필요할 경우 Script 파일로 커스텀이 가능 합니다.
> 
> 배포 결과는 히스토리 페이지와 Slack 메신저를 통해 확인이 가능 합니다.
> 
> 특정 시점으로 롤백이 가능 합니다. 배포시 Commit아이디를 DB에 기록하고 해당 Commit아이디로 hard reset 합니다.
