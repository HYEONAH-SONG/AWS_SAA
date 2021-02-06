- Key Management Service (KMS)
  - key 관리 시스템으로 데이터를 암호화하고 복호화하는 기능을 담당
  - EBS, S3, RDS 등의 서비스에서 데이터 암호화/복호화 기능을 제공
  - AWS가 직접 키의 안전을 책임짐
  - Key의 3가지 유형 (CMK를 누가 관리하는가에 대한 기준)
    - AWS Managed CMK(AWS) : 사용자는 CMK에 대한 제어 권한이 없음, 주기적으로 변경
    - Customer Managed(고객) : 고객은 KEY의 활성화, 비활성화, 삭제 등에 제어 권한을 가짐 
    - AWS Owned CMK(사용자) :  CMK를 KMS가 아닌 CloudHSM에 저장하여 사용하는 방식

