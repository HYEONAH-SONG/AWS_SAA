# Application

- #### Simple Queue Service (SQS)

  - **메시지 큐 서비스**

  - Pull 기반의 서비스

  - 서비스간의 직접적인 통신이 아닌 중간 매개를 두고 안전한 대기열을 제공하여 분산 소프트웨어 시스템을 제공하는 서비스

  - 시나리오 : 서버A가 서버B로 request를 보내는 경우, 서버B에 직접보내지 않고 큐(SQS)에 저장하면, 서버B가 나중에 큐를 열어서 메시지를 확인하고 수행함

  - 수행한 메시지는 서버B가 확인 후 삭제

  - 각 메시지는 최대 256KB의 텍스트로 구성됨 (고정 x)

  - 최대 14일 까지 저장 가능 (Default : 4일)

  - 각 컴포넌트들을 **분할(decouple)**하여 독립적으로 운영하게 함으로써 한 서비스가 실패한 경우에도 서비스 요청을 보존할 수 있게 함

  - 큐(queue)의 유형

    - Standard queues (default) : 초당 무제한에 가까운 요청을 처리할 수 있으며 최소 한 번의 요청을 처리하나 순서가 보장되지 않음
    - FIFO 대기열 : 선입선출을 지키는 대기열로 초당 최대 300개의 요청 처리 가능

    

- #### Simple Notification Service (SNS)

  - 클라우드에서 설치와 동작, 알림 전송을 간단하게 만드는 웹 서비스
  - Push 기반의 서비스 / 와서 전달함
  - 구성 요소
    - Topic  : 메시지의 성격을 정의함
    - Subscription : 메시지를 받을 대상을 설정함
      - HTTP(웹)
      - SQS
      - 이메일
      - Lambda
      - mobile application
    - publisher : 메시지를 전달함
    - endpoint : 메시지를 전달 받음
  - Topic에 관한 메시지를  그 topic에 소속된 다수의 구독자(endpoint)에게 전달할 수 있음
  - Multi - AZ 지원

  

- #### SNS vs SQS

  - 공통점 : AWS 메시징 서비스
  - 차이점 : SNS - Push / SQS - Pull



- #### API Gateway

  - REST API 및 Web socket API, HTTP API 를 생성, 유지, 관리하는 AWS 서비스
  - API Gateway 구성요소
    - Resource : 서비스의 대상
    - Method : 리소스에 대해 취할 행동을 정의함 (ex. GET, PUT, HEAD, PATCH 등)
    - Stage : 클라이언트가 API Gateway를 사용하기 위해 생성하는 배포판으로 생성 시 각 리소스에 대해 URl가 생성됨
  - Lambda를 연동하여 Serverless 구축 가능
  - **API Caching**은 엔드포인트의 응답을 캐시해서 엔드포인트에 대한 호출 수를 줄일 수 있음
  - Cloudwatch에 모든 결과를 기록할 수 있음

![image-20210206160629967](C:\Users\송현아\AppData\Roaming\Typora\typora-user-images\image-20210206160629967.png)

- #### Kinesis

  - 완전 관리형 스트리밍 서비스
  - 데이터의 수집 구간과 데이터 처리 구간의 중간에 위치
  - 다양한 형태로 들어오는 데이터를 가공해서 다양한 분석 소프트웨어가 사용가능하도록 출력물을 만들어주거나 데이터 저장소에 저장하도록 해줌
  - Streaming data : 수천 개의 데이터 원본에서 연속적으로 생성되는 데이터로서, 보통 데이터 레코드를 작은 크기(KB단위)로 동시에 전송함

