## 서버 모니터링 데몬 개발

![image](https://user-images.githubusercontent.com/48572149/208467613-a6b3a6a1-cc9f-4bbe-ad09-f09948e61826.png)

> watchdog 모듈은 각서버에 위치하며 주기적으로 metirc 정보를 cloudwatch에 전송 합니다.
>
> watchdog-server 모듈은 cloudwatch 지표를 모니터링 하며, 수집된 metric 데이터를 5분 단위로 계산합니다.
>
> 서버별 metric type별 임계치는 Constants.go 에 정의 되어 있습니다.
>
> 임계치 초과 시 Slack 알림을 발송 하고, 장애 조치 Script를 수행 합니다.
