# 📁Tech-Interview_Storage
기술 면접을 대비하여 관련 내용을 정리하는 공간입니다.

<br><hr><br>

# 목차
* ### **[자료구조](#자료구조)**
* ### **[Java](#Java)**
* ### **[Network](#Network)**
* ### [운영체제](#운영체제)
* ### [Database](#Database)

# 자료구조
## **스택(Stack)**
<br>
heap영역에 생성된 Object 타입의 데이터들에 대한 참조를 위한 값들이 할당된다.
원시 타입의 경우 실제 데이터 값이 할당된다.
해당 method가 호출되면 메모리에 할당되고 method가 종료되면 메모리가 해제된다.
각 Thread는 자신만의 Stack을 가진다.
지역변수, 매개변수를 위한 공간

<br>

## **힙(Heap)**

<br>

모든 Obejct Type(String, ArrayList, HashMap, Integer,..)의 데이터가 저장되는 영역이다.
new 를 상용하여 생성되는 객체의 저장 공간

<br><hr><br>

# Java
## Java 버전 별 특징
* Java1.4 -> Java 5로 올라갈때부터 앞에 1을 빼고 표기, 내부적으론 1.5, 1.6, ... 사용
* Java SE 8
  * lambda 표현식 추가
  * stream api 추가
  * 날짜와 시간 API 추가
  * 32비트 지원 마지막 공식버전
* Java SE 9
  * HTTP/2 지원
  * 64비트 버전만 출시
* Java SE 10
  * var 키워드 이용한 지역변수 타입 추가
  * JVM 힙 영역을 시스템 메모리가 아닌 다른 종류의 메모리에도 할당
  * JDK 레퍼지토리가 하나로 통합
  * Java기반 JIT 컴파일러
* Java SE 11
  * lambda 파라미터에 대한 지역변수 문법 추가
  * HTTP 클라이언트 표준화
  * OracleJDK의 독점기능이 OpenJDK에 이식
  * 2019년 1월부터 OracleJDK가 유료 모델로 전환

<br><hr><br>

# Network
## __3-way handshake란?__ 
TCP/IP 프로토콜을 이용해서 통신을 하는 응용프로그램이 데이터를 전송하기 전에 먼저 정확한 전송을 보장하기 위해 상대방 컴퓨터와 사전에 세션을 수립하는 과정을 말한다.

자세한 내용은 -> https://jeongkyun-it.tistory.com/180 

<br>

## __4-way handshake란?__ 
3way handshake가 연결 수립을 위해 진행된 과정이였다면, 4way handshake는 세션을 종료하기 위해 수행되는 과정을 말한다.

자세한 내용은 -> https://jeongkyun-it.tistory.com/180 

<br>

## __HTTPS란? 그리고 HTTP와 차이점이란?__ 
HTTP는 클라이언트와 서버간 통신을 하는 프로토콜이다. 그러나 보안성이 낮은 이유로 HTTPS는 기본적으로 적용시켜 출시한다. 14년 구글에서 HTTPS로 변경하면 SEO 가산점을 준다는 말에 힘입어 14년 이후부터 HTTPS는 필수가 된 암호화 프로콜이라 볼 수 있다.

HTTPS는 HTTP에서 보안을 첨가한 암호화 프로토콜이며, 세션키를 대칭키로 사용하여 빠르게 암복호화를 하며 통신을 진행하는데, 
이 세션키를 키로 사용하기 위한 교환 방식은 비대칭키 암호화를 거쳐 통신하는 방식을 말한다.

자세한 내용은 -> https://jeongkyun-it.tistory.com/181

<br><br><br>

# 운영체제
## __캐시(Cache)란?__
자주 사용하는 데이터나 값을 미리 복사해 놓는 임시 장소를 말한다. <br>
캐시는 데이터를 접근하는 시간이 오래 걸리는 경우나 같은 값을 다시 계산하는 시간을 절약하고 싶은 경우 사용한다.
그래서 보통 캐시는 썸네일과 같은 이미지가 적용되어있는 부분에 많이 사용한다.

### **캐시의 지역성**
캐시가 효율적으로 동작하려면 캐시의 적중율(Hit-rate)을 극대화 시켜야한다. 그러기 위해선 캐시에 저장할 데이터가 **지역성**을 가져야 하는데,
캐시는 시간적 or 공간적 지역성 두개로 나뉘어진다. <br><br>
**시간적 지역성**은 특정 데이터가 한 번 접근되었을 경우 가까운 미래에 또 한번 데이터에 접근할 가능성이 높은 것을 말하며, <br>
**공간적 지역성**은 특정 데이터와 가까운 주소가 순서대로 접근되었을 경우를 말한다. 
<br>
### **즉, 지역성이란**<br>
-> 기억장치 내의 정보를 균일하게 Access하는 것이 아닌 어느 한 순간에 특정 부분을 집중적으로 참조하는 특성이라 보면된다.

웹 캐시 동작 방식에 대해 알고싶다면  -> https://jeongkyun-it.tistory.com/173

<br><br><br>

# Database
## __인덱스(Index)란?__
![image](https://user-images.githubusercontent.com/97106584/174426476-6d5ea61e-04de-4a8d-9783-61e06684bbe5.png)

데이터베이스 테이블에 대한 **검색 성능의 속도를 높여주는 자료구조**를 말한다.
책을 예로들어, 원하는 내용을 찾는다 가정했을 때 모든 페이지를 찾아 보는 것은 오래 걸리기때문에 보통 책의 저자들은 책의 맨 앞 또는 맨 뒤에 색인을 추가하는데, Database의 인덱스는 해당 예시의 색인과 같다고 보면된다.<br>

### 인덱스를 사용하는 이유?
위에서 말했듯 색인을 생성하여 조건 검색이라는 영역에서 큰 장점을 갖고있기에 사용한다.

### 인덱스의 단점?
인덱스의 가장 큰 문제점은 특징과 관련있다. 인덱스는 정렬된 상태를 계속 유지시켜줘야 한다는 특징 갖고있다.<br>
그렇기에 레코드 내에 데이터 값이 변경되는 부분이라면 악영향을 미친다. 그 이유는 INSERT, UPDATE, DELETE를 통해 데이터가 추가되거나 값이 바뀐다면 INDEX 테이블 내에 있는 값들을 다시 정리를 해야하기 때문이다.<br>
또한 INDEX 테이블, 원본 테이블 이렇게 두 군데에 데이터 수정 작업을 해줘야한다는 단점도 있다.<br>
따라서, 무 분별한 인덱스의 사용은 지양해야한다.<br>

인덱스에 대한 더 자세한 내용은 블로그에 정리할 예정이다.
