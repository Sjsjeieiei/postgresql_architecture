notion 링크:https://wind-dewberry-ca7.notion.site/postgresql-7f6e0fbf653f410ca3c2506843fa2474?pvs=4

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/7540eda1-50b0-4704-924e-78f9872ec9b8/b2d1b02d-e417-4c15-9067-4956bf89b5f2/Untitled.png)

감사모듈에서 db인스턴스에 대한 제어를 수행한다.

모니터링 모듈은 node 1 or node 2 에서 분산시켜 사용한다.

데이터 연동 모둘: t_up과같은 걸 db링크라고 함.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/7540eda1-50b0-4704-924e-78f9872ec9b8/3fd87146-2db9-4579-a593-973598abffd5/Untitled.png)

멀티 프로세스 방식의 구성이므로 커넥션풀은 지원하지 않는다.

클라이언트 - 서버 모델 

리눅스에서의 프로세스를 확인가능하다.

postmaster = oracle listner

postmaster 에서 오라클의 리스너와 같이 세션의 연결할당하는 프로세스를 부여하는 데몬 프로세스이다.

비정상 작동 체크도하며 하위프로세스가 장애시 이를 재기동 시키는 역할도 수행한다.

```jsx
ps -ef - grep postgres
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/7540eda1-50b0-4704-924e-78f9872ec9b8/2e88b5cb-62bb-410d-8b26-039927371b56/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/7540eda1-50b0-4704-924e-78f9872ec9b8/c24bda8b-2e93-4f53-9b14-3015ad56617a/Untitled.png)

백엔드 프로세스 기동 종료시 새로운 백그라운드 프로세스가 생성된가.

오라클 sga

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/7540eda1-50b0-4704-924e-78f9872ec9b8/0457dee5-659d-4f0f-85e8-14c6b8b1b55e/Untitled.png)

- bg writer

쉐어드 버퍼 디스크 블록을 기록하는 프로세스

dirty blcok: db 버퍼캐쉬에서 변경된 블록.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/7540eda1-50b0-4704-924e-78f9872ec9b8/be1f81df-58bb-476f-a576-7ffe2f7f84e2/Untitled.png)

대부분의 dbms는 8kb를 고수한다.

check point : sga 공간부족시 데이터 파일과 메모리 영역을 동기화 시켜준다.
