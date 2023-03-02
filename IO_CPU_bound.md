# IO bound, CPU bound

`IO bound` : CPU burst보단 **IO burst 가 많은 프로세스**

- 일반적인 BackEnd 서버



`CPU bound`: IO burst보단 **CPU burst 가 많은 프로세스** 

- ex) 영상 편집 프로그램, AI 프로그램



> burst?
>
> 어떤 현상이 짧은 시간동안 집중적으로 일어나는 일
>
> CPU burst: 프로세스가 CPU에서 한번에 연속적으로 실행되는 시간
>
> IO burst: 프로세스가 IO 작업을 요청하고 결과를 기다리는 시간 (Blocking)





## 특정 CPU(듀얼코어, 헥사코어, 싱글코어 등) 동작할 CPU bound 프로그램을 구현한다면 몇 개의 스레드를 쓰는게 좋은가?



> Goetz 가 말하길..
>
> CPU bound 프로그램에서 적절한 Thread의 수는 CPU의 코어 갯수 + 1 이다.



### Why?

무턱대고 Thread의 갯수를 늘린다면 그만큼 **Context Switch** 의 빈도가 높아지기 때문에 오버헤드가 발생하기 때문
