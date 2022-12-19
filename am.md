## 접근제어솔루션 프로토콜별 제어 및 감사

![image](https://user-images.githubusercontent.com/48572149/208469181-7427bf35-b033-4c25-b040-3a63bfbfe1af.png)

> 전용 클라이언트로 ssh, sftp에 접속된 사용자 세션을 식별. 커맨드라인 및 스크립트를 감사하는 기능을 개발 했습니다.
>
> 감사기능은 exec() 시스템콜을 사용 했으며, Enter키 기준으로 등록된 명령어와 일치할 경우 session kill을 발생 시킵니다.
>
> 감사로그는 로컬 MongoDB에 기록 됩니다.
>
> 서버와 클라이언트는 socks5를 통해 통신하며 서버의 커스텀된 ssh, sftp 데몬을 호출 합니다.
