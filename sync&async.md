# Synchronous
![동기](https://user-images.githubusercontent.com/24227385/222663377-7d1ae8b6-63d9-4f40-9aa1-f42a3993207f.jpg)


- Task1, Task2, Task3 차례 차례 실행시킴

  ex) Task1 이 끝나면 Task2 이 끝나면 Task3



# Asynchronous
![비동기](https://user-images.githubusercontent.com/24227385/222663387-8501e597-cbfe-4e65-8837-9093681391e5.jpg)


- 여러 작업을 동시에 실행시키는 **방법론**
- asynchronous != multithreading <= `multithreading` 은 비동기 프로그래밍의 한 종류이다.
- Asynchronous 프로그래밍을 가능하게 하는 요소들은 `multi-threads` `non-blick I/O` 다



## I/O 관점에서 비동기

1. 동기 I/O = BLOCK I/O,

   비동기 I/O = NON_BLOCK I/O

   

2. 동기 I/O : IO작업을 요청자가 I/O 완료까지 챙겨야 할 때(매번 확인함)

   비동기I/O : I/O작업중 장치가 작업 완료를 noti로 알려주거나 결과를 callback으로 처리

   

3. 비동기 I/O: blcok I/O를 다른 thread에서 실행
