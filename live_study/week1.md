
* JVM이란 무엇인가

## JVM이란 무엇인가 
- JVM이란 **JAVA Virtual Machine**(자바 가상 머신) 의 약자를 따서 줄여 부르는 용어입니다.
JVM 역활은 자바 애플리케이션을 클래스 로더를 통해 읽어 들여 자바 API와 함께 실행하는 것이다.
그리고 JVM은 JAVA와 OS사이에서 중개자 역활을 수행하여 JAVA 가 OS 에 구애받지 않고 
재사용을 가능하게 해준다.
가장 중요한 **메모리관리**, **Garbage collection**을 수행한다. 그리고 JVM은 **스택기반**의 가상머신 이다. ARM아키텍쳐 같은 하드웨어는 레지스터 기반으로 동작하는데 비해 JVM은 스택기반으로 동작한다.

> 스택기반
>>Heap 영역에 생성된 Object 타입의 데이터의 참조값이 할당된다.
>>원시타입의 데이터가 값과 함께 할당된다.
>>지역변수들은 scope 에 따른 visibility 를 가진다.
>>각 Thread 는 자신만의 stack 을 가진다.

> Garbage Collection
>> JVM의 Garbage Collector가 스택의 모든 변수를 스캔하면서
>> 각각 어떤 오브젝트를 레퍼런스 학 있는지 찾는 과정을 Mark 라고 한다.
>> Reachable 오브젝트가 레퍼런스 하고있는 오브젝트 또한 marking 한다.
>> 첫번째 단계인 marking 작업을 위해 모든 스레드는 중단되는데 이를 stop the world라고 부르기도 한다.
>> 그리고 나서 mark가 되어있지 않은 모든 오브젝트들을 Heap에서 제거하는 과정이 Sweep이다.
>> Garbage Collection 은 garbage가 아닌 것을 따로 mark하고 그 외의 것은 모두 지우는것이다.
>> 만약 Heap에 garbage만 가득하다면 제거 과정은 즉각적으로 이루어진다.

> 메모리 관리
>> 속도 만큼 중요한 점중의 하나는 메모리 사용량이다.
>> 만약 SW 가 RAM 사이즈보다 크게 되면
>> 시스템은 Virtual Memory를 사용하게 될테고, 결국
>> HDD IO 가 발생하게 되어서 속도가 급속도로 떨어지게 된다.
>> 좋은 자바프로그램이란, 효율적으로 메모리를 관리해주도록 하게 해줘야 한다.

