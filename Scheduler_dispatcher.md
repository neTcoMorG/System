# scheduler, dispatcher

`cpu scheduler` , `dispatcher` 의 역할과 차이점을 기술함.



## scheduler

- ready Queue에 있는 프로세스/스레드를 `state`를 변경함

  

## dispatcher

- scheduler가 선택한 *(running state로 바꾼 요소)*를 실제로 CPU에서 실행될  수 있도록 작업 함

  ex) Context switch, KernelMode -> UserMode 전환

- 한 마디로 선택된 프로세스에게 CPU를 할당하는 역할



# 스케줄링의 선점 방식(동작 방식)

1. Nonepreemptive (=비선점)

   - CPU에서 실행중인 프로세스*(running)*이 자발적으로 `running` 이외의 상태로 변환하는 것 (OS에서 강제로 시킨 게 아님)

   - 협력적이지만 사용자 입장에서 느린 응답성을 보인다

     

2. Preemptive

   - `Nonepreemptive Scheduling` 기본적인 역할을 수행
   - OS가 상황에 따라 `running` 상태의 프로세스를 ready Queue로 보내는 등 상태를 강제저그로 변경
   - 빠른 응답성이지만 데이터 **일관성** 문제가 생김(강제로 스케쥴링 하기 떄문)



# 스케쥴링 알고리즘

- Ready Queue에 있는 요소를 어떤 기준으로 선별할건지에 대한 알고리즘



1. FCFS

   - 먼저 도착한 순서대로 처리 (=Queue)

     

2. SLF

   - 프로세스의 다음 CPU burst가 가장 짧은 프로세스부터 실행

     ex) p1(5), p2(10), p3(7) => p1 -> p3 -> p2

     

3. SRTF

   - 남은 CPU burst가 가장 짧은 프로세스부터 실행

     ex) p1(10) p2(5) p3(16) p2->p1->p3으로 진행하는데 중간에 더 낮은 CPU burst 프로세스가 등장하면 waitting 시키고 낮은 버스트 프로세스를 실행 *(Preemptive 느낌)*

     

4. Priority

   - 우선순위가 높은 프로세스부터 실행
     
     

5. Round-robin (RR)

   - `time-slice`로 나눠진 CPU time을 번갈아가며 실행

   - 멀티 태스킹과 가장 비슷한 스케쥴링 방식

     

6. Multilevel Queue

   - 프로세스들을 그룹화해서 그룹마다 큐를 두는 방
