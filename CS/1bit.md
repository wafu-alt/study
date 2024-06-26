인프런 강의 : **[넓고 얕게 외워서 컴공 전공자 되기](https://inf.run/7Dpa) - 널널한 개발자**

## 하드웨어

CPU와 Mainboard 하드웨어 부분을 알면 컴퓨터 구조를 알 수 있고, 운영체제에도 영향을 받는다.

단자 = 인터페이스

### CPU 상세정보 [예시](https://prod.danawa.com/info/?pcode=32038667&cate=112747&adinflow=Y#bookmark_product_information)
![image](https://github.com/wafu-alt/study/assets/83447120/a81a9ce0-ae0f-4a10-81ac-a72b1ffa746d)


소켓 구분 : 메인보드와 물리적인 호환성

제조 공정 : 

- 반도체의 제작과정이고, 트랜지스터와 트랜지스터와의 거리
    - CPU는 트랜지스터라는 반도체로 만들어짐
    - 반도체는 주로 실리콘으로 만들어짐
    - 실리콘은 (규소+산소)전자4개 (실리콘)원자1로 구성
    - 실리콘은 안전정적인 구조 최외각 전자 8개일 때 전자가 이동되지 않아서 전류가 안 흐름
    - 전자 1개를 부족하거나 추가해서 전기를 통하게 만들 수 있음
        - 전자 1개 추가 : P(Positive)형 반도체
        - 전자 1개 부족 : N(Negative)형 반도체
    - 트랜지스터 : 전기가 흐르게 할 수 있게 못할 수 있게 하는 스위치
    - 트랜지스터로 논리회로를 만들 수 있고 AND, OR, NOT, XOR을 만들 수 있다
    - 트랜지스터로 2진법이 완성된다.
- 공정이 미세하고, 트랜지스터의 집적도가 높아지면 성능⬆️ 전력소모⬇️ 발열량⬇️
코어 수 : 동시에 처리할 수 있는 수

쓰레드 수 : CPU내부의 실질적 업무 수행하는 가장 작은 논리적 단위

- CPU 1코어 당 1쓰레드로 업무가 가능하다
- 인텔은 하이퍼스레딩이라는 기술로 1코어가 2쓰레드를 가지고 동시 처리가능하다
    - 하이퍼스레딩(Hyper-Threading Technology) : 운영체제에서 CPU 코어 한 개당 스레드가 하나씩 추가되어 싱글 코어에서 두개의 CPU가, 듀얼 코어에서 네 개의 CPU가 장착된 것으로 인식(코어 당 2개)하는 기술
    - 이 기술을 사용할 경우 기존의 물리 코어의 개념은 없어지고 논리 코어로만 작동하게 되는데 사용 환경과 프로그램에 따라 성능이 향상.
    - 특히 다중 작업에서 유리함

기본 클럭(주파수) : 

- CPU 동작 속도, 0과 1의 구분을 초당 몇번 할 수 있는지 수치
- 1GHz 10억번 의미하고, 40억번 이상 구분 가능
- IPC : 클럭 당 명령어 처리 횟수
- SIMD : 하나의 명령어에 의해 여러 개의 데이터를 처리하는 기술
- 단순히 클럭 수로 CPU 동작속도를 비교하긴 어렵지만 대략적인 성증 지표로는 삼을 수 있음

L2 캐시 

- CPU 내부에서 임시로 사용하는 버퍼(Buffer) 메모리 중 하나
- level 2의 약자, PC에 장착된 메모리와 CPU 사이에서 동작하며, CPU가 데이터를 처리하는 동안 다음에 처리할 내용을 메인 메모리로부터 불러와 대기하는 곳이 L2 캐시 메모리

L3 캐시

- L3 캐시 메모리도 L2 캐시 메모리와 마찬가지로 CPU 안에 내장되어 있는 일종의 임시 메모리
- 다중 코어 CPU의 경우 L2 캐시는 코어마다 하나씩 들어있으나 L3 캐시 메모리는 CPU 전체에서 하나만 존재
- Level 3 캐시 메모리라고도 하며, PC에 장착되어 있는 메인메모리에서 CPU에 처리해야 할 데이터를 보낼 때 가장 먼저 지나게 되는 임시 저장소

연산 체계

- 내부에서 데이터 처리를 위해 계산할 때 한 번에 처리하는 데이터의 크기를 말함
- 8비트 CPU라 함은 CPU가 한 번에 8비트 단위로 데이터를 처리할 수 있다는 뜻
- 64비트 CPU는 264B(약 16EB)까지 메모리를 관리할 수 있는데, 이는 사실상 무한대에 가까운 수치

버스 속도

- 버스는 컴퓨터 구성 요소들 간 또는 컴퓨터들 간에 데이터를 전송하는 하위 시스템
- 종류로는 CPU와 메모리 컨트롤러 허브 간에 데이터를 전달하는 FSB, 컴퓨터 메인보드의 인텔 I/O 컨트롤러 허브와 인텔 통합 메모리 컨트롤러 사이의 상호 연결인 DMI, CPU와 통합 메모리 컨트롤러 간 지점간 상호 연결인 QPI 등 ⇒ CPU와 메인보드에 있는 칩셋 사이에 데이터를 주고 받을 때 사용하는 통로의 너비
- 이 대역폭은 CPU의 성능이 빨라짐과 함께 동시에 커짐
그래야 CPU가 처리한 데이터를 빨리 내보내고 그와 동시에 CPU가 처리해야할 데이터를 보낼 수 있음
- 표현하는 단위는 T/s( Transfer to second의 약자이며 초당 전송률)
- 인텔에서 사용하는 CPU 대역폭은 QPI와 DMI, UPI가 있으며
 AMD는 UMI와 HT를 사용
    
    ![다나와 참조](https://github.com/wafu-alt/study/assets/83447120/bfb86e37-726a-4f55-bf5e-c9c86118d4ed)

    노란 형광색 부분) - CPU와 메인보드 칩셋 사이에서 데이터를 주고 받는 통로를 말함
    
    ![다나와 참조](https://github.com/wafu-alt/study/assets/83447120/d59636b9-c9a7-4df5-a8d2-2c8803e930d6)

PBP/MTP

- 전력소모 표기 방식
    - TDP : 열 설계 전력, 기본 클럭으로 장시간 활용 시 쿨링에 필요한 전력 → 실제 CPU 소비 전력은 더 높음
    - PBP(인텔) : 프로세스 기본 전력, 기본 클럭으로 작동 시 소비전력
    - MTP(인텔) : 최대 터보 전력, 부스트 클럭으로 작동시 소비 전력 → 순정 상태에서도 순간적으로 더 높은 전력을 소비할 수도 있음
    - PPT(AMD) : 패키지 전력 추적, CPU가 사용하는 최대 전력
- 인텔은 12세대 CPU 까지는 TDP(Thermal Design Power)열설계전력을 사용하여 CPU의 소비전력과 배출하는 열량을 표기
    - TDP는 기본 클럭으로 제한된 조건에서의 풀 워크로드를 가정하기 때문에, 워크로드 부하가 커지면 터보 부스트 클럭으로 동작하는 실 환경과 사용전력 및 해소해야 할 열량 어느쪽에서도 차이가 있음
    - 13세대 랩터레이크 부터는 PBP(Processor Base Power)와 MTP(Maximum Turbo Power)로 분리하여 전력 및 해소 열량을 표기하기 시작
- PBP는 CPU가 기본 클럭에서 작동될 때 소모되는 전력으로, 기존 TDP와 유사하다고 보면 되고(PL1 - Power Limit 1)
- MTP는 1초 이상 지속되는 최대 전력 소모를 의미하기 때문에(PL2 - Power Limit 2) 순간적으로 표기된 MTP보다 더 큰 전력이 소모될 수 있음
- CPU의 모든 성능을 활용하고자 할 때, 쿨러는 MTP 보다 100W 가량 넉넉한 TDP를 지원하는 제품을 구비하는 것이 좋음

PCIe 버전

- CPU에서 지원하는 PCIe버전을 뜻함
- PCIe는 주로 NVMe SSD와 그래픽카드를 연결하는 인터페이스로 사용

    ![image](https://github.com/wafu-alt/study/assets/83447120/2bfa3bbc-acb8-4381-9390-16dbe11fe08b)


- NVMe SSD와 그래픽카드의 성능을 온전히 발휘하기 위해서는 각각의 버전을 지원하는 CPU와 메인보드를 구매해야함

최대 PCIe 레인수

- CPU에서 지원하는 PCIe 레인 수
- 레인 수가 많을수록 확장성이 좋음
- PCIe 레인은 CPU가 그래픽카드, 저장장치, 메인보드 등 외부장치와 서로 통신하기 위한 통로
- 하나의 장치가 쓸 수 있는 최대 레인 개수는 x16
    - 고성능의 그래픽카드는 16개의 레인을 모두 사용
    - 가성비 그래픽카드는 그 절반인 8개의 레인만 사용하는 경우도 있음
- 인텔 12세대 및 AMD 4세대 이후 CPU는 M.2 NVMe SSD를 위한 기본 4레인을 확보해두고 있으며, 일반적인 CPU는 그래픽카드 16레인을 합쳐 총 20레인을 지원하는 경우가 많음
    - 만약 그래픽카드를 장착하지 않는다면 남은 16레인을 다른 장치에 할당 할 수 있으며, 반대로 그래픽카드와 M.2를 사용중임에도 추가로 PCIe 슬롯에 다른 장치를 연결할 경우, 그래픽카드의 속도가 x8로 감소
    - 반면 이미 M.2 NVMe SSD 용도로 확보된 4레인은 그래픽카드 등 다른 장치가 사용 할 수 없음
- AMD의 경우 최대 레인 수가 같은 시대에 출시된 인텔 메인보드보다 4레인 많은 것을 알 수 있는데, AMD는 그래픽카드, M.2 용도의 x16 x4 레인 외에 메인보드 칩셋용 4레인이 별도로 할당되어 있기 때문
    - 따라서 AMD CPU가 24(20)레인 으로 표기된 경우, 지원하는 레인 개수는 총 24레인 이지만 메인보드가 4레인을 고정적으로 사용하고 있어, 사용자가 그래픽카드와 M.2에 사용 할 수 있는 PCIe 레인 개수는 20개 라고 해석 할 수 있음    

최대 메모리 크기

- CPU에서 최대로 지원하는 메모리 크기

메모리 규격

- CPU에서 지원하는 메모리 규격
- 메모리 규격이 DDR3 > DDR4 > DDR5로 갈 수록 데이터속도⬆️, 전송속도⬆️ 전력소모 ⬇️
    - DDR : Double Data Rate
        - 클럭 신호의 다운비트와 업비트에서 사이클당 2회에 걸쳐 프로세서로 데이터를 전송
        - SDRAM은 클럭 한 신호에 대해서만 데이터 전송
        - DDR이 메모리 어레이에서 내부 입력/출력 버퍼로 2비트의 데이터를 전송하는 프로세스를 2비트 프리페치prefetch
        - DDR2는 개선된 버스 신호를 이용해 DDR보다 2배 빠르게 작동
            - DDR과 동일한 내부 클록 속도를 사용하지만 향상된 입력/출력 버스 신호를 이용하기 때문에 전송 속도가 더 빠름
            - 실제 내부 동작 클럭
                - DRAM cell의 작동클럭에 물리적 한계가 있어 내부에 여러 cell들에서 나오는 데이터를 저장해두는 버퍼가 있음
                - prefetch buffer라고 부르고 데이터 단위를 4n, 8n, 16n같이 표기
            - 한 주기(cycle)의 동작 - 전송률
                - 실제 데이터를 cpu에게 전송할 때 prefetch buffer를 DRAM cell보다 더 높은 클럭으로 데이터가 나가고 DDR4기준으로 4배의 클럭이 됨(MHz/s , GHz/s)
                - 한 클럭에 두번 데이터 전송으로 *2해서 총 8배 수치로 데이터를 전송 DDR4 : 8n
        - [crucial 참조](https://www.crucial.kr/articles/about-memory/difference-among-ddr2-ddr3-ddr4-and-ddr5-memory)
        
        ![image](https://github.com/wafu-alt/study/assets/83447120/5bba6de8-66b4-4524-9b3b-7dc3bd24780b)

        
    - RAM : Random Access Memory
    - 컴퓨터가 켜지는 순간부터 CPU는 연산을 하고 동작에 필요한 모든 내용이 전원이 유지되는 내내 이 기억장치에 저장
    - 일반적으로 전원이 차단되면 내용이 지워지는 **휘발성** 기억 장치
    - Random Access : “어느 위치에든 똑같은 속도로 접근하여 읽고 쓸 수 있다”는 의미
        
        ![image](https://github.com/wafu-alt/study/assets/83447120/3af7825e-629b-4653-96cc-a5f2a4fef951)

        
    - 동작클럭 : 5600MHz
        - 메모리의 동작 속도를 말함
        - 초당 데이터 전송 수를 말함 Hz/s
        - 동작속도가 클 수록 빠름
        - 실제 내부 동작속도가 아님 (위의 DDR설명 참조)
            
            ![image](https://github.com/wafu-alt/study/assets/83447120/dfac87a3-4e86-4b2a-b727-0f052e15a295)

            
        - MT/s단위 MHz를 기본적으로 사용

메모리 클럭

- CPU가 지원하는 동작 클럭을 말함

메모리 채널

- 메인보드의 지원에 따라 다름
- 메모리를 묶어서 속도를 올려주는 기능
- 주로 2개씩 묶음. 3개나 4개 메모리를 묶어서 속도를 올려줄 수 있음
- CPU가 메모리와 데이터를 주고 받을때 128비트 사용
- 메모리 1개는 64비트를 지원. 2개씩 묶으면 128을 맞출 수 있음

### 메인보드(Mainboard) [예시](https://prod.danawa.com/info/?pcode=19536062&cate=112751&adinflow=Y#bookmark_product_information)
![image](https://github.com/wafu-alt/study/assets/83447120/49f83b59-498e-4644-aec7-5d2517ef170f)
제품 분류

- CPU 호환되는 규격. 인텔, AMD가 있다

CPU 소켓

- CPU 장착하는 부분

세부 칩셋

- 각 메인보드마다 지원하는 소켓 수와 종류가 다르다
- 칩셋(chipset) : 중앙제어장치와 같은 역할
- 칩셋 종류마다 메모리 오버클럭을 할 수 있다.
    - 메모리 RAM 작동 주파수와 지연 특성을 타이밍이라고 불리운다
    - 타이밍을 낮게, 주파수를 높게해서 더 빠르게 데이터 전송하는 방식
- CPU와 타 장치 사이에서 데이터를 중개역할

폼팩터(Form Factor)

- 메인보드 크기에 따른 분류
- 전원, 케이스 내부의 메인보드 위치, 공기의 흐름, 메인보드 외부 커넥터를 위한 I/O 플레이트 크기 등이 정의되어있음
- 아래 사진으로 크기 비교되고 mm 단위이다

![image](https://github.com/wafu-alt/study/assets/83447120/204ed9f0-97df-46cb-b642-b96c329c2391)


![image](https://github.com/wafu-alt/study/assets/83447120/b09bbea3-585f-4f95-abe7-bc0d3e28ba13)


전원부
- 페이즈(Phase) : 파워서플라이가 전기를 만들어주는 것을 받아서 해당 하드웨어에 전기를 배분하는 역할
    - 300W를 배분할때 5개 페이즈면 각 페이즈마다 60W 배분해서 페이즈가 부담한다.
    - 페이즈가 많을 수록 배분량이 줄어 발열량이 줄어든다.
        
        ![image](https://github.com/wafu-alt/study/assets/83447120/ed6674c3-a20e-4b53-a3f3-9e019f48b49a)
- 전원부 : 파워에서 받아온 전압을 낮추거나 배분해주는 역할하는 장소
    - 초크코일 + 트랜지스터 + 캐패시터 = 페이즈
    - 초크코일(Choke Coil)
        - 나쁜 전기 성분들을 걸러주는 필터
        - 페이즈 개수를 말할 때 보통 초크 개수를 따라감
        - 토로이달(Toroidal) 타입, 큐빅(Cubic) 타입으로 나눔
            - 토로이달
                - 원형 코어에 코일이 감겨져 노출된 형태
                
                ![image](https://github.com/wafu-alt/study/assets/83447120/a8359753-2ab6-4160-a09d-c4913c7b75b9)

                
            - 큐빅
                - 반개방형은 정사방면 사이드는 막혀있되 위쪽은 에폭시로 몰드된 코일이 노출된 형태
                - 완전차폐형은 네모난 커버로 덮혀 있는 형태
                    - 완전 차폐형 큐빅 초크 쪽이 발열이 좀 더 낮으며 전력을 좀 더 낮게 소비하고 노이즈 차폐에도 강함
                
                ![image](https://github.com/wafu-alt/study/assets/83447120/7d1d4920-042e-4696-b3fb-df358a461160)

                
    - 트랜지스터(모스펫 Mosfet)
        
        ![image](https://github.com/wafu-alt/study/assets/83447120/b5685d68-adf5-41c7-bc6e-68b7fecf7476)

        
        - D-PAK이라 불리는 IC 패키지로 제공되며, RDS(On)이라 불리는 스위칭 소자의 내부저항이 낮을수록 열 손실이나 전력 소비면에서 더 나은 성능을 나타냄
            - 제조사에 다라 독자적인 고급 모스펫 사용
            - 닥터모스, NXP TrenchFET, DirectFET, Power Stage 등
        - 기판에 납땜되어 있는 다리 수가 많을수록 좋은 제품
        - 1개의 초크 당 많은 모스펫 사용하면 좋은 메인보드 제품
    - 캐피시터(Capacity)
        
        ![image](https://github.com/wafu-alt/study/assets/83447120/61dd1d91-9403-4566-9de5-a5a4dc8c5af8)

        
        - 전해질 타입과 솔리드 알루미늄 타입으로 나눔
            - 전해질 타입의 경우 오래 사용하면 부풀어 올라 누액을 일으키거나 내용물이 흘러나와 망가지는 경우가 있음
            - 솔리드 알루미늄 타입은 부풀어 오르거나 내용물이 흘러 나오는 경우가 거의 없음
    - PWM컨트롤러(모스펫 드라이버)
        
        ![image](https://github.com/wafu-alt/study/assets/83447120/3b417af5-e0ed-49df-8976-7057d1ea2743)

        
        - PWM(Pulse Width Modulation) 펄스 폭 변조
        - +12V 전압을 각 부품이 필요로 하는 전압
        - 보통은 CPU 따로, 메모리 따로, 칩셋 따로 PWM 컨트롤러를 할당해 놓으며 이 PWM 컨트롤러는 아날로그 방식과 디지털 방식으로 나눔
        - 일반적으로 디지털 방식이 아날로그에 비해 더 정교한 전압 컨트롤이 가능해지기에 오버클럭에 더 유리하다고 알려져 있음
메모리 종류

- 메인보드가 지원하는 메모리 소켓

메모리 속도

- 메인보드가 지원하는 메모리의 클럭

메모리 슬롯

- 메인보드가 지원하는 메모리의 슬롯 갯수

메모리 채널

- 메인보드에서 메모리를 묶어서 속도를 올려주는 기능
- 2개 3개 4개씩 묶을 수 있음
- 듀얼 채널일 경우 메모리를 2개 꽂으면 자동으로 동작

메모리 용량

- 메인보드가 인식할 수 있는 메모리의 용량

메모리 기술

- XMP(eXtreme Memory Profiles) 인텔에서 만든 메모리 오버클럭 기술
- 메인보드 BIOS설정만으로 쉽게 고성능 메모리를 가질 수 있음
    - BIOS : Basic Input/Output System(기본 입출력 체계)
    - 컴퓨터 소프트웨어의 최저층에 존재
    - 소프트웨어가 하드웨어를 제어하고, 하드웨어가 소프트웨어에 변경된 정보를 전달 등 소프트웨어 - 하드웨어 간의 설정 및 정보전달의 매개 역할하는 컴퓨터 펌웨어

VGA 연결

- 그래픽카드 연결하는 소켓
- PCIe x 16슬롯이 일반적.
- 대역폭 1x, 4x, 8x, 16x로 구분되고 1lane, 4lane, 8lane, 16lane이라고 표기

![image](https://github.com/wafu-alt/study/assets/83447120/6dd83bae-e9e8-4113-b150-92ddb5d0a17b)

![image](https://github.com/wafu-alt/study/assets/83447120/1ca99fce-a156-4489-a01f-9bea4cd7127d)
PCIe슬롯

- 메인보드가 지원하는 슬롯
- PCIe(PCI-Express) x16 : 16배속 슬롯이라고도 함
- 주로 그래픽카드에서 사용. 사운드카드, USB확장카드 등에도 사용가능
- x16은 x8, x4, x1슬롯 하위호환 가능
      
### 1bit와 2수 (다른 말로 디지털)

- 1bit(비트)를 전기 스위치 on / off로 표현
    - on : 1
    - off : 0
- 스위치 4개를 조합하면 4bit
    - 경우의 수는
        - 0000 , 0001 , 0010 , 0011 …. 총 2^4 = 16가지

### 2진수, 16진수 진법변환

- 디지털은 0,1 이고 4bit씩 묶으니 16가지 수가 되어서 16진수로 표현함
- 4비트를 자리수로 0000 표현하는데 자리값이 존재
    - 0000 → 8421 자리값으로 10진수로 변환할 수 있다
        - 0110 → 0+4+2+0 = 6(10진수)
        
        ![image](https://github.com/wafu-alt/study/assets/83447120/94a7c641-4eb8-4c2d-b616-83fb54539b0c)

        
        - 1010 → 8+0+2+0 = 10(10진수) →  A (16진수) ← 0x 0A로 표현 가능 0x가 16진수라는 표기
            - “0x”를 프리픽스(Prefix)라고 함
            - “0x F4” → 1111 0100 = 8bit를 말함
            - 8bit = 2^8 = 256가지 수를 가짐
                - 자릿 수 값으로 환산하면 128 + 64 + 32 + 16 + 8 + 4 + 2 + 1
                - 0x F4 = 1111 0100 = 128 + 64 + 32 + 16 + 0 + 4 + 0 + 0 = (10진수) 244
### 16진수 표기가 사용 예

- 색상표현
    - RGB 색상 표현에 (255,255,255) 중 (255)는 8bit를 사용 2^8으로 256가지 수를 가짐
        - #B71C1C 같은 경우 8bit*3해서 24bit Red,Green,Blue로 표현
            - (10진수로 변환하면) RGB 183 28 28 로 표현됨
- 컴퓨터 하드웨어 주소 표현
- 메모리 값 표현
    - 8bit = 1byte = 영문자 한 글자가 저장될 수 있는 메모리 크기, 관리의 최소 단위(RAM 메모리의 작은 용량 단위)
    - 4bit = 16가지 수, 8bit = 256가지 수, 16bit = 65,536가지 수(64KB)
        - 2^10 = 1024 기준으로 단위가 바뀜
        - 1024 byte = 1KB
    - 2^32(bit) = 4,294,967,296 (42.9억) byte = 4GB
    
    | 1Bit | 전기 스위치 0, 1 |
    | --- | --- |
    | 1Byte (바이트) | 8Bit (2^1) |
    | 1KB (킬로바이트) | 1024Byte (2^10) |
    | 1MB (메가) | 1024KB (2^20) |
    | 1GB (기가) | 1024MB (2^30) |
    | 1TB (테라) | 1024GB (2^40) |
    | 1PB (페타) | 1024TB (2^50) |
    | 1EB (엑사) | 1024PB (2^60) |
    | 1ZB (제타) | 1024EB (2^70) |
    | 1YB (요타) | 1024ZB (2^80) |
### 컴퓨터가 글자를 다루는 방법

- 숫자 → 글자 로 연결,맵핑, 사상함 ⇒ 렌더링한다고 말함
    - 10진수 65 - “A” - 16진수 0x41로 표기 하자는 코드체계
    - 미국 표준 코드 체계 ASCII (American Standard Code for Information Interchange)
        - 10진수 1 = 0x01
        - 문자 “1” = 0x31
- 숫자, 글자를 구별하지 않고 정보를 말할 때는 바이너리(Binary)라고 함
    - 컴퓨터 모든 정보가 2진수로 되어있음 이 모든 것을 바이너리라고 함
    - 빈칸, 엔터, 숫자, 문자 등등 다 정보 취급
        - 엔터 : 0D 0A
        - 빈칸 : 20

### 컴퓨터가 사진을 다루는 방법

- 모니터 화면 상 ‘점’ 하나를 화소(Pixel)이라고 함
- 화소 하나 표현하는데 ⏹️⏹️⏹️⏹️ 8+8+8+8 = 32bit정보 필요 RGBA라고 함
    - R = Red, G = Green, B = Blue
    - A(알파채널) = 투명도
    - 32bit = 4byte (= 32 / 8)
    - 4 x 4 = 8픽셀 일 때
        - 8 x 4byte = 32byte = 256bit (32 x 8)
- bitmap = 각 화소를 그대로 저장하는 방법 → 그래서 용량이 큼 , 잘 사용하지 않음
- 압축기술을 통해 압축한 파일을 사용
### 디지털 회로

- CPU가 게이트 회로로 이루어짐
- 전자식 계산기
- not = Inverter
- XOR = exclusive or (익스크루시브 or) = 배타적 논리합
- A, B가 input일 때 아래와 같이 산수 연산

![image](https://github.com/wafu-alt/study/assets/83447120/f8278057-7aab-4afa-b51e-5faeaadb81bf)


- TTL gate를 내장한 IC칩셋을 반도체라고 할 수 있음
    - transistor-transistor logic
    - 트랜지스터를 조합한 논리 회로
    - 전기가 신호가 되어서 값이 각각 2개 on / off = 도체일 수도 부도체일 수도 ⇒ 반도체

![image](https://github.com/wafu-alt/study/assets/83447120/6f6bfea4-94ce-4901-a85c-a9c38da9c93b)


![image](https://github.com/wafu-alt/study/assets/83447120/f3be8033-5c2f-4e17-844a-9194a2d6d29b)


- 각 inputA + inputB  결과가 2가지
- input에 2가지 값을 가져서 1bit라고 할 수 있음 on / off

### 덧셈

- 반 가산기
    - XOR + AND 게이트로 이루어짐
        
        ![image](https://github.com/wafu-alt/study/assets/83447120/01245491-24d9-4524-87eb-6498aa9e8558)

        
    - 결과값과 C (carry out=자리 올림) 출력값을 가짐
        
        ![image](https://github.com/wafu-alt/study/assets/83447120/d0319332-d483-433a-bd56-6e2de9a4a353)

        
    - A + B를 더하는 계산기를 만들 수 있음
        - 2진수로 1 + 1 = 10 → 10진수 2+0 = 2
    - bit합산이 2개만 됨
- 전 가산기
    - 여러 bit합산을 할 수 있게 구성됨
    - XOR 2개, OR 1개, AND 2개 게이트로 구성
    - Cin은 이전 자리올림
    
        ![image](https://github.com/wafu-alt/study/assets/83447120/7cad07d6-6d34-4dc6-b5ec-3118404b1d04)

    

        ![image](https://github.com/wafu-alt/study/assets/83447120/b2197cee-9071-471b-9d56-7f2a22b2b7c5)


        ![image](https://github.com/wafu-alt/study/assets/83447120/4b71b8a6-bdb1-40fb-80bc-c1d3601a8896)


- 위의 전 가산기를 붙여서 아래 4bit 가산기를 만들 수 있음

![image](https://github.com/wafu-alt/study/assets/83447120/1a7b354a-9832-4229-afff-4a6f7f5e40dc)


![image](https://github.com/wafu-alt/study/assets/83447120/163d41e3-d54e-4a5f-90c2-fa1f6432dda6)
- https://kldp.org/node/110850 참조

### 뺄셈

- 보수를 통해서 구함
    - 10진수 인 경우 6 +⏹️ = 10 → ⏹️ = 4
    - 4는 6에 대한 10의 보수가 됨
        - 10진수는 10의 보수, 9의 보수가 존재 0~9
    - 보수를 구한 다음 더함
        - 54 - 34 = ⏹️
        - 34의 10의 보수 100 - 34 = 66
        - 54 + 66 = 120, 100자릿수를 버림, ⏹️ = **20**
- 컴퓨터는 2진수로 1의 보수를 구하면 됨
    - 2진수는 2의 보수, 1의 보수가 존재 0~1
    - 0 → 1 , 1 → 0
    - (10진수)13 - 6 = ⏹️ → (2진수)1101 - 0110 = ⏹️
        - 6 → 0110의 2의 보수 0110 + 1 = 1010
        - 13 + 6(2의보수값) → 1101 + 1010 = 0001 0111 에서 (0001)9비트이상 자리를 버림
        - ⏹️ = 0111 → 7

### 곱셈

- 곱셈은 기본적으로 더하기를 계속 해주면 됨
    - 2x3 = 2 + 2 + 2
- 숫자를 왼쪽으로 밈 (Shift) - 곱하는 수가 짝수일 때
    - 10진수
        - 1 → 10 → 100 각 자리 수 마다 10^n씩 늘어남
        - 10^0 → 10^1 → 10^2
        - 자리 값을 알 수 있음
    - 2진수
        - 0001 → 0010 → 0100 각 자리 수 마다 2^n씩 늘어남
            - 오른쪽에 0으로 채워짐 (Padding)
            - 위와 같이 자리 값을 알 수 있음
        - 2^0 → 2^1 → 2^2
        - (10진수) 2x2 → 2x3 → 2x4 한다는 가정하면
            - 2x(2^1) → 2x(2^1 “+ 1”) → 2x(2^2) 으로 변환 할 수 있음
            - 주의할 건 홀수로 곱해지는 부분인데 “+ 1” 의 의미는 기존 2에 해당하는 bit값을 더해주면 됨
                - (10진수)2x1 = (2진수) 0010
                - (10진수)2x2 = 4 = (2진수)0100 = 0010 + 0010
                    - 0100 = 0010 + 0010
                - (10진수)2x3 = 6 = (2진수)0110 = 0100(=10진수 4) + 0010(=10진수 2)
                    - 0110 = 0010 + 0010 + 0010
                    - 3 = 2^1 + 1 , (10진수 2=)0010에서 쉬프트 1번 후 + 0010  와 같은 의미
                - (10진수)2x4 = 8 = (2진수)1000
                    - 1000= 0010 + 0010 + 0010 + 0010
                - (10진수)2x5 = 10 = (2진수)1010 = 1000(=10진수 8) + 0010(=10진수 2)
                    - 5 = 2^2 + 1 , (10진수 2=)0010에서 쉬프트 2번 후 + 0010  와 같은 의미
                - (10진수)2x8 =16 = (2진수)0001 0000 , 이지만 4bit를 넘어서서 0000만 출력
                - (10진수)2x9 =18 = (2진수)0001 0010 , 이지만 4bit를 넘어서서 0010만 출력
                    - 9 = 2^3 + 1 , (10진수 2=)0010에서 쉬프트 3번 후 + 0010  와 같은 의미
### 나눗셈

- 나눗셈은 기본적으로 빼기를 계속 해주면 됨
    - 8 / 2 →  8 - 2 - 2 - 2 - 2 = 0 → 몫은 4 = 2를 4번 뺌
- 숫자를 오른쪽으로 밈(Shift) - 나누는 수가 짝수 일 때
    - 왼쪽에 0으로 채워짐 (Padding)
    - (10진수)6 = (2진수) 0110
    - (10진수)6/2 = 3 = (2진수) 0011
        - 0110 - 0010 = 0100 > 0010
        - 0100 - 0010 = 0010 = 0010  stop
        - 0010  - 0010  = 0 stop
            - 0110 - 0010 - 0010 - 0010
    - (10진수)6/3 = 2 = (2진수) 0010
        - 0110  - 0011 = 0011 = 0011
        - 0011  - 0011 = 0 stop
            - 0110  - 0011 - 0011
        - 3 = 2^1 + 1으로 오른쪽으로 쉬프트1번 후 나머지는 버려짐
    - (10진수)6/4 = 1 ,나머지 2 = (2진수) 0001  … 0010
        - 0110  - 0100 = 0010 < 0100 stop
    - (10진수)6/5 = 1 ,나머지 1 = (2진수) 0001  … 0001
        - 0110  - 0101 = 0001 < 0101 stop
        - 5 = 2^2 + 1으로 오른쪽으로 쉬프트2번 후 나머지는 버려짐

### 컴퓨터가 연산하는 과정

- CPU : 연산장치(비메모리)
    - 레지스터 : RAM에서 가져온 정보를 담음(복사)
    - 산술논리장치(ALU, arithmetic and logical unit) : 산술 작업
    - 이름으로 관리됨
    
    ![image](https://github.com/wafu-alt/study/assets/83447120/2a15b734-dbe3-4035-8623-016889215e1d)

    
- RAM : 메모리 반도체(저장목적)
    - 1차 메모리
        - 2차 메모리 : SSD , HDD
    - 일련번호(엑셀의 셀이라고 생각하면 쉬움)
    - 일련번호마다 공간 있음 ← 정보 저장
    - 32bit = 2^32 = 42억 9천만 byte = 4GB
        - 운영체제 32bit면 4GB메모리를 인식만 가능
- 동작 순서 (RAM → CPU → RAM)
    1. RAM에서 일련번호를 참조해서 정보를 가져옴
    2. 레지스터로 복사해서 ALU에서 산술함
    3. 다시 RAM에 보냄
    
    ![image](https://github.com/wafu-alt/study/assets/83447120/8f8afc0b-5a0a-438f-a993-e3aab850e00a)
    - [이미지 참조 링크](https://hongong.hanbit.co.kr/%EC%BB%B4%ED%93%A8%ED%84%B0%EC%9D%98-4%EA%B0%80%EC%A7%80-%ED%95%B5%EC%8B%AC-%EB%B6%80%ED%92%88cpu-%EB%A9%94%EB%AA%A8%EB%A6%AC-%EB%B3%B4%EC%A1%B0%EA%B8%B0%EC%96%B5%EC%9E%A5/)
    
### 기억장치의 종류와 역할

![image](https://github.com/wafu-alt/study/assets/83447120/ffc0421a-3df0-4d39-a352-a3607e28c6d0)
- [이미지 참조 링크](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=techref&logNo=222246966805)

- CPU
    - Register
    - L1,2,3 캐시 메모리(Cache memory)
        - RAM과 속도 차이 나는 부분을 메꾸기 위함
        - 정보 - 프로그램 코드, 코드를 연산해야 할 대상
        - CPU가 미리 예측해서 캐시 메모리에 임시 저장함
            - 예측 실패할 경우 캐시 폴트(fault)
            - 실패하면 RAM에서 찾고 RAM에서 업으면 보조 메모리에서 찾음
    - 속도가 굉장히 빠름
    - 고가
    - 메모리 크기가 작음 (메모리 용량 취급 안하고 CPU일부로 취급)
- 메인 메모리(1차)
    - RAM
    - 휘발성 메모리 (전원 끄면 데이터 날라감)
    - CPU 다음으로 속도가 빠름
- 보조 메모리(2차)
    - HDD, SSD, USB disk 등
### 컴퓨터가 기억공간을 관리하는 방법

- 정보가 저장된 위치 숫자로 표시 - 메모리 주소 = RAM 일련번호
- 보조기억장치 - 트랙(Track), 섹터(Sector) 를 관리함
    - HDD - 트랙은 눈에 보이지 않음 (자기 디스크가 직접 회전)
        - 안쪽에서 0 ~ 시작함
        
        ![image](https://github.com/wafu-alt/study/assets/83447120/c556a19e-b30b-4714-8948-4bfac21d4073)
        - [이미지 참조 링크](https://gusdnd852.tistory.com/86)
        
    - 정보는 섹터에 담김
        - 0번 트랙 0번 섹터 : 마스터 부트 레코드 MBR
        - 운영체제 부트로더가 들어가있음
        - 컴퓨터 부팅하는데 사용
    - 삭제
        - 지울 때는 지웠다고 테이블에 표시 남김
        - 실제 데이터는 살아 있음
        - 그래서 복원도 가능
    - 포맷 (파일 할당테이블(File Allocation Table) 형식을 바꿈)
        - FAT 메타 데이터를 날리는 식 - 빠른 포맷
            - 파일 시스템 FAT, FAT32, EXFAT, NTFS 등등
        - 모든 트랙과 섹터들을 0으로 덮어쓰는 식 - 느린 포맷
    - SSD - 트랙과 섹터로 관리(칩 형태)
- 보조 기억장치에서 프로그램을 설치
- 실행 시 주 기억장치에 프로그램이 복사됨
- CPU가 연산함 - 실행
### 동시성(Concurrency)

- 예시. 인터넷 브라우저 실행, 윈도우에서 다른 프로그램 실행
- 동시 연산 실행에 문제없음
- 상호 간섭이 없음

### 병렬성(**Parallelism**)

- 코인의 채굴 - GPU 프로세서 유닛 대규모 연산
- 같은 일을 여러 주체가 함께 동시에 진행
- 영상 처리 할 때 많이 사용

### 원자성(Atomicity)

- 동시성에서 A,B가 서로 간섭하게 될 경우 → 동기화 개념도 나옴
- 자원의 선점 ← LOCK 잠김 상태가 들어감
- 자원 선점이 끝남 ← UnLock 잠김상태 풀림
- 잠김 ~ 잠김 풀림 : 원자성

### 동기화(Synchronization)

- 원본과 사본이 있을 때 원본이 변경 될 경우 사본도 같이 변경 해줌
- 원자성의 잠금 장치로 다른 쪽에서 간섭 못 하게 순서를 지어주는 것을 동기화라고 함

### 교착상태(Deadlock)

- 동기화의 오류 - 교착상태
- 잠금 상태에서 잠금 상태를 못 푸는 경우
- 계속 잠금 되어지는 상태
