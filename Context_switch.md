# Context Switch

- CPU/코어에서 실행 중인 프로세스/스레드가 다른 프로세스/스레드로 교체될 때 진행되는 작업 *(= CPU의 레지스터 상태를 교체하며 대상에 따라 메모리를 초기화)*

- `Context switch`의 실행 주체는 `kernel` 이다.

- `Context`는 **프로세스/스레드**의 실행 상태를 담고있음

  
  
## 왜 필요한가?

- 여러 프로세스/스레드를 **동시**에 실행시키기 위해서 즉 **멀티 태스킹** 을 수행하기 위해서


  
## 언제 발생?

- 프로세스/스레드가 주어진 `time-slice`(=quantum)을 다 사용했거나
- `IO` `interrupt` `async` 등 발생되거나


  
## 종류

1. **Process Context Switch**
   - 이 스위칭은 가상 메모리 주소 처리를 추가로 수행하기에 `Thread Context Switch` 방식보다 무겁다 (MMU, TLB)]
   - CPU는 주기억장치에서 자주 접근하는 데이터를 `Cache`에 기록해두는데 `Context Switch` 로 인하여 캐시가 빈번히 바뀌어 오염이 된다. *(=cache pollution)*
   
2. **Thread Context Switch**
