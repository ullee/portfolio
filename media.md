# Media Convert

#### 미디어 스트리밍 프로토콜 종류
> - HLS, MPEG-DASH, MSS...
> - 업로드된 동영상은 보통 호환성이 좋은 HLS로 변환하지만, 각 OS별로 특화된 인코딩 방식을 사용하기로 함

#### CMAF 도입
> - 동일한 콘텐츠를 서비스 포맷에 맞게 재 인코딩 또는 트랜스 코딩을 하는데, 이같은 과정이 비디오 전송에 있어 시간과 비용에 많은 소모가 되어 결국 스트리밍의 속도 저하
> - CMAF로 컨테이너화 해서 파일 1개로 통합. 플랫폼별 DRM 암호화를 위해 여러 물리 파일 생성 불필요
> - Android 7.1 이상 iOS 10 이상 지원
> - 엣지 또는 IE11과 같은 윈도우즈 기본 브라우저를 지원하지 못함. MS에서 CBC모드를 지원하면 가능 (PC의 경우 Chrome, Safari 브라우저 사용)
>
> ![](https://steemitimages.com/DQmabwp8ZmXC59ubEce5pBjPe7U8M621YVuCqTTsxHu98Y5/image.png)

#### DRM(디지털 저작권 관리) 패키징 종류
  - Widevine, FairPlay, PlayReady
---
### 1. 인코딩 과정
![image](https://miro.medium.com/max/1400/1*EBrO1ioquwHC41Zkw-KlhQ.jpeg)
> 1. multipart upload 가 가능한 REST API를 통해 video 파일을 업로드 합니다.
> 2. upload 서버는 s3에 파일 업로드가 완료되면 AWS Lambda를 호출 합니다.
> 3. AWS Lambda는 MediaConvert 작업 Queue를 생성한 후 종료 됩니다.
> 4. MediaConvert 작업이 완료 되면 CloudWatch로 Event가 발생 합니다.
> 5. Cloudwatch는 Event 콜백을 받은 후 다시 AWS Lambda를 호출 합니다.
> 6. 호출된 AWS Lambda는 각 서비스에 컨버팅(hls/dash)이 완료된 경로를 업데이트 해준 후 종료 됩니다.

---
### 2. 미디어 서비스 구성도
![media](https://kroki.io/c4plantuml/svg/eNp9k1FP2zAQx9_9KW55mFJpGmLsA0ADEhJ0q5ohXpAq1z5aC8fOHDsUTXz3ObaTuoPx0pzv9z_f5X_NeWepsa6R5JNQTDqOUH1fV1pZ3Nuv7XuACoUmImKFlQh3rdSUw2dYIBcUvKhHY6FG0wuGhCzRdFqVrkPzBQomBSpbzEj90lls1nPtFKfmpWTfPL24r4sZ_CEAEZdFd1b4fB1-fRXANERZuNB5IHdTRFsRZGO9pM2G04HcTlEmWF_tbVk0w-QsDj4IwptUh_OVYpoLtQWr4fq2Prm8qK8f1II-IVyuFilqDYoen6EXHPWDWmGjewTci8c3_ZjUjj9Ty3bD7dVwuh9PufhgzqknN26DRqHF7mBCcuvIFrajYeoqPUdLjkQbTU0wbD4G78qCM5MlueyVvBKyQpkWG3fh-fJn_QtO0mpmUZFY3IXX7KxtExtz-Qq84rdDh_-Ud2cetM7G9PoHiu1uo0055Kert_iGH1998H5YbO__jDB3XaqZU_Y0jXSkrHTTSu89KG3Fo2DUCq3yqsH1fI7Vsspx8PsDHob8gEeXY5PMvxymFv-hqcFIyTkq7r_ivxX4R9U=)
