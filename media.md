## Media Convert Flow

![media](https://kroki.io/c4plantuml/svg/eNp9k1FP2zAQx9_9KW55mFJpGmLsA0ADEhJ0q5ohXpAq1z5aC8fOHDsUTXz3ObaTuoPx0pzv9z_f5X_NeWepsa6R5JNQTDqOUH1fV1pZ3Nuv7XuACoUmImKFlQh3rdSUw2dYIBcUvKhHY6FG0wuGhCzRdFqVrkPzBQomBSpbzEj90lls1nPtFKfmpWTfPL24r4sZ_CEAEZdFd1b4fB1-fRXANERZuNB5IHdTRFsRZGO9pM2G04HcTlEmWF_tbVk0w-QsDj4IwptUh_OVYpoLtQWr4fq2Prm8qK8f1II-IVyuFilqDYoen6EXHPWDWmGjewTci8c3_ZjUjj9Ty3bD7dVwuh9PufhgzqknN26DRqHF7mBCcuvIFrajYeoqPUdLjkQbTU0wbD4G78qCM5MlueyVvBKyQpkWG3fh-fJn_QtO0mpmUZFY3IXX7KxtExtz-Qq84rdDh_-Ud2cetM7G9PoHiu1uo0055Kert_iGH1998H5YbO__jDB3XaqZU_Y0jXSkrHTTSu89KG3Fo2DUCq3yqsH1fI7Vsspx8PsDHob8gEeXY5PMvxymFv-hqcFIyTkq7r_ivxX4R9U=)

> 1. multipart upload 가 가능한 REST API를 통해 video 파일을 업로드 합니다.
>
> 2. upload 서버는 s3에 파일 업로드가 완료되면 AWS Lambda를 호출 합니다.
>
> 3. AWS Lambda는 MediaConvert 작업 Queue를 생성한 후 종료 됩니다.
>
> 4. MediaConvert 작업이 완료 되면 CloudWatch로 Event가 발생 합니다.
>
> 5. Cloudwatch는 Event 콜백을 받은 후 다시 AWS Lambda를 호출 합니다.
>
> 6. 호출된 AWS Lambda는 각 서비스에 컨버팅(hls/dash)이 완료된 경로를 업데이트 해준 후 종료 됩니다.
