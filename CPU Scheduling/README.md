# CPU Scheduling
### CPU Scheduler
Ready 상태의 프로세스 중에서 CPU를 줄 프로세스를 고른다
### Dispatcher 
CPU의 제어권을 선택된 프로세스에게 넘긴다. 
기존에 running되던 프로세스의 정보를 (save) 하고 새로운 프로세스의 정보를 (load)하는 역할
### Scheduling Criteria(스케쥴링 알고리즘 성능 척도)
- CPU Utilizagtion(CPU 이용률)
- Throughput(처리량)
- Turnaround time(소요 시간)

## 1. FCFS(First Come First Served)
Ex P1 24, P2 3, P3 3

Wating Time = 0 + 24 + 27
Average Time = Total Wating Time / Process count

CPU의 점유가 짧은 프로세스가 먼저 오는 경우에는 짧아진다. 
반대의 경우 **Convoy Effect**

## 2. SJF (Shortest Job First)
P1 24, P2 4, P3 2
P3 -> P2 -> P1

CPU 사용시간이 긴 프로세스는 지속적으로 CPU를 할당할 수 없는 Starvation(기아)이 발생하게 된다.

**SJF is Optimal** 
주어진 프로세스들에 대해 최저 평균 대기시간을 가진다.
-> OS가 프로세스를 빼앗을 수 있는 경우 SRTF(Shortest Remaning Time first) 방법으로 최적의 방법을 보장한다.


## 3. Priority Scheduling
priority = predicted next CPU burst Time
SJF는 일종의 우선순위 스케쥴링 방법이다 
당연히 starvation을 수반하게 된다
Aging 시간이 지날수록 프로세스의 우선순위를 높여준다.

## 4. Round Robin(RR)
각 프로세스는 동일 크기의 CPU 할당 시간을 가진다. 
할당 시간이 끝나면 인터럽트가 발생하여 프로세스는 CPU를 빼앗기고 CPU 큐의 제일 뒤에 줄을 선다.
동일 크기의 할당량을 짧게 잡으면 CPU의 오버헤드가 급증하게 된다.
SJF보다 response time이 제일 적고 average turnaround time이 길다(모든 job이 큐에서 빠져나갈 때까지 걸리는 시간)

## Multilevel Queue
프로세스가 다른 큐로 이동 가능
Aging과 같은 방법으로 multilevel queue를 구현할 수 있다.

## Multiple - Processor Scheduling 
CPU가 여러 개인 경우 스케쥴링은 더욱 복잡해진다. 

## Symmetric Multiprocessing(SMP)
각 프로세서가 각자 알아서 스케쥴링 결정

## Asymmetric Multiprocessing 

## Thread Scheduling 
- Local Scheduling
사용자 수준의 thread library에 의해 어떤 thread를 사용할 지 결정
- Global Scheduling
kernel level thread의 경우 단기 스케쥴러가 어떤 thread를 스케쥴 할지 결정