# 유니버스 CI/CD 구축
## 파이프라인 구성
### - 젠킨스 (NC Cloud), gradle 7.2, github

## 배포 Flow
- code push
- 젠킨스의 빌드 스크립트 스케줄링(정기배포) or 수동배포
- gradle jib plugin -> jar 와 docker image 빌드
- ECR Push. (ECR Repository 가 존재하지 않을 경우 자동 생성)
- Helm 기반 EKS Pods Rolling update 배포

![](https://user-images.githubusercontent.com/48572149/213778539-12e152d1-3acf-482d-a401-8a1aa3512a1e.png)
