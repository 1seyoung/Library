---
tags:
  - AntEater_Member
---

[깃허브에서 보기](https://github.com/1seyoung/Anteater/blob/main/member-service/README_MEMBER_SERVICE.md)


![[스크린샷 2024-09-14 오전 5.45.34.png]]

### API 요청 및 인증 시나리오



1. 클라이언트가 Access Token과 함께 API 요청을 API Gateway로 전달한다.
    
2. API Gateway는 Access Token의 만료 여부를 검증한다.
    
3. Access Token이 만료된 경우:
    
    - API Gateway는 클라이언트에게 401 Unauthorized 응답을 전달한다.
    - 클라이언트는 API Gateway로 Access Token을 Refresh하기 위한 요청을 전달한다. (이때 Refresh Token을 함께 포함한다.)
    - API Gateway는 이 요청을 Member Service로 전달한다.
    - Member Service는 Redis에서 Refresh Token의 유효성을 검증한다.
4. Refresh Token이 유효한 경우:
    
    - Member Service는 새로운 Access Token을 발급한다. (새로운 Refresh Token은 저장하지 않는다.)
    - 클라이언트는 새 Access Token으로 API 요청을 다시 전달한다.
5. Refresh Token이 무효한 경우:
    
    - 클라이언트에게 재로그인을 요청한다.
6. Access Token이 유효하거나 재인증이 완료된 후:
    
    - API Gateway는 Target Service에 API 요청을 전달한다.
    - Target Service는 응답을 반환한다.
    - API Gateway는 클라이언트에게 최종 응답을 전달한다.