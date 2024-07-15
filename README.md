notion 링크:https://wind-dewberry-ca7.notion.site/postgresql-7f6e0fbf653f410ca3c2506843fa2474?pvs=4

![image](https://github.com/user-attachments/assets/d97a4114-c4c8-4e63-adf6-d7c8b0640a13)


감사모듈에서 db인스턴스에 대한 제어를 수행한다.

모니터링 모듈은 node 1 or node 2 에서 분산시켜 사용한다.

데이터 연동 모둘: t_up과같은 걸 db링크라고 함.

![image](https://github.com/user-attachments/assets/9bbc43ad-8997-4eee-bf07-973bb4b03d2b)


멀티 프로세스 방식의 구성이므로 커넥션풀은 지원하지 않는다.

클라이언트 - 서버 모델 

리눅스에서의 프로세스를 확인가능하다.

postmaster = oracle listner

postmaster 에서 오라클의 리스너와 같이 세션의 연결할당하는 프로세스를 부여하는 데몬 프로세스이다.

비정상 작동 체크도하며 하위프로세스가 장애시 이를 재기동 시키는 역할도 수행한다.

```jsx
ps -ef - grep postgres
```

![image](https://github.com/user-attachments/assets/da1dc19f-873b-4cd6-ae4d-68cd2a1eabab)


백엔드 프로세스 기동 종료시 새로운 백그라운드 프로세스가 생성된다.

