# 인앱 결제 아키텍처
> 구독 상태 변경 및 갱신 결제 시 App Store, Google Play Store 에 등록된 콜백 URL로 콜백을 전달 받습니다.
>
> Store Server-side Notification --> POST /store/{os} --> Server (gRPC)


# 2. Apple 결제 프로세스

### 구독 상품 (IOS)

> 유저 정보 식별을 위해 서버는 appAccountToken 필드를 사용합니다.
> 
> Client 에서 구독 상품 구매 시 서로 약속된 룰로 생성한 [UUID](https://developer.apple.com/documentation/storekit/product/purchaseoption/3749440-appaccounttoken)를 appAccountToken 필드에 추가 합니다. 

![ios_purchase](https://kroki.io/plantuml/svg/eNp1kssOgjAQRfd8xfxAm_g2xhh8bNwZie4rjEljobUd9PctKFoUVyw49zE3jR0JS2WuoqUxwNgCErQ3tDPocdhZnZUpgZKOwOK1REc1N2fsw7Ff0hldOHxb-m9C2uIM-h_UWJkiyOKsbS5I6uInIZCFGV3Cv4EDDtvlLrSuf7QuHXJYC6VOIr14MEVpKLSPntyX8YjDUSiZNQ2esibnJWlfMaqu6BS96gdBm1XF-7kOxtMId18QqbvKmMO-srph1p6iHT9ppvg71tQPoXPjg7BCoxiLzD-NB6H2tfY=)

### 소모성 상품 (IOS)

![ios_purchase](https://kroki.io/plantuml/svg/eNp9kssOgjAQRfd8xfxASXwQDTFG1I07EqJ7AmPSpNDaDvr7FqSCgKy6OfcxNz0YSjVVhfAipYCxPSSon6hDWPgQa5lXGYHghkDjo0JDDbdjrOPYmDRKlga_lvZNSGoMYdmhSvMMgZd3qYuUuCxHCT1ZP2NK-Ddw5cMlimesNw4YWLjz1j7cUsFzl5QhV9RP9z7kIDeYlLkareS3SVAfOSlqq_WCzseat2telaURXqkQSIMqzXEThpkslKVxbretDyeH2X28A5a5_SVvtt-6RA==)

---


# 3. Google 결제 프로세스
### 소모성 상품 (Android)

![android_purchase](https://kroki.io/plantuml/svg/eNqdkssKwjAQRfd-xSx1kR8QESuCuCv42IdmbINpJk4Si39vtVhpfaHb4cw9d0JmPkgOsTSDxDkQYgpr5BPyGFImFbMARvsAjMeIPtygiRDvIO_IemyjlkS5wdTI8zoQ4wN3rDMEbffEpQya7JPgp9Vv2lWSfhc0UC_qfudOGq0a3ZUbVjoU4CJnhfS4oQPaUWtodl43-SPnZdleTtv7kzvJDpYqgyrHEm2n52I-hq2rAxGir2eVNAY7RP0g760ztKr-Qhf2zM19)

### 구독 상품 (Android)

![android_subscription](https://kroki.io/plantuml/svg/eNqVkkEOwiAQRfc9BRfgAo0xrZoYd00a3SOMDSkFhMHG20tsq1WrjVt4f_4bQuaROQyNSnJrCaVLUoK7gEtJ4YwIHImSHomDcwCPd2hB6TfIW6M9PEZtjakUFIpdSzQOnrh1kgOR-mRcw1Aa_VHwV3SudpcX8wUd1I96u315mDVT6sh4HWkO0uJYJumgaY0DU1IMzl10sOpjk2KTsd7zV13Oa21aBaKCBjSO2c0qJXsbhwIJPp61cSXAJAMt4le4AYa-vHc=)
