### :notebook_with_decorative_cover: JAVA

1. 객체지향에 대해서 설명하세요.

> 객체지향 프로그래밍/설계란 시스템을 **상호 작용하는 자율적인 객체들의 공동체**로 바라보고 객체의 역할, 책임, 협력을 이용해 시스템을 분할하는 기법을 의미한다.

<br>

2. Java의 구동원리(컴파일 과정)를 설명해주세요.

<br>

3. 쓰레드란 무엇이고, 싱글쓰레드와 멀티쓰레드의 차이를 설명해주세요.

<br>

4. 클래스는 무엇이고, 객체는 무엇인지 설명해주세요.

> Java에서 클래스는 멤버 변수 및 메서드의 집합으로 특정한 객체의 형태를 제공한다. Object는 해당 클래스의 new 키워드를 이용해 생성한 식별 가능한 개체를 말한다.

<br>

5. 인터페이스와 추상클래스의 차이점은 무엇인지 설명해주세요.

[Inerface vs Abstract Class](https://2jinishappy.tistory.com/281?category=936901)

<br>

6. 직렬화가 무엇인지 설명하세요.

<br>

7. Call by Value와 Call by Reference의 차이에 대해 설명해주세요.

> 정의부 -> [Return type] Method ([DataType] parameter, ..)
> 
> 호출부 -> Method(argument, ..)
> 
> 메서드의 정의 및 호출이 위와 같은 형식으로 이루어져 있다고 가정합니다.
> 
> **Call by Value**: 메서드를 호출할 때 argument로 전달한 인자를 복사해서 Method 내의 parameter로 전달하는 방식 
> - Method 내에서 접근하는 parameter는 지역 변수로 새롭게 복사되어 사용하는 값입니다.
> - Method 내의 parameter의 값을 변경해도 호출부의 argument에 영향이 가지 않습니다.
> - Method 내의 parameter의 Life Time은 Method의 return문이 수행될 때 까지입니다.(메서드 수행이 끝난 뒤 소멸됩니다)
> 
> **Call by Reference**: 메서드를 호출할 때 argument로 전달한 인자의 주소값을 전달하여 Method 내에서 실제 argument를 접근하는 방식
> - Method 내에서 접근하는 parameter는 실제 argument가 위치하는 메모리를 가리킵니다
> - Method 내의 parameter의 값을 변경하면 호출부의 argument가 가리키는 변수 또한 변경됩니다.
> - Method의 수행이 종료되어도 사라지지 않습니다.

<br>

8.  Catched Exception과 Uncatched Exception의 차이를 설명해주세요.

[Catched and Uncatched Exception](https://2jinishappy.tistory.com/292)

> Uncatched Exception
> : Throwable 클래스를 상속받는 클래스 중 Error 클래스와, Exception - RuntimeException를 포함한 서브 클래스를 포함하는 Exception을 가리킵니다.
> - 코드 작성 시점에는 에러가 발생하지 않지만, Runtime 시점에 에러가 발생합니다.
> - Transaction의 대상이 되어 에러가 발생할 시 Rollback이 발생합니다.
> - NPE, ClassCastException 등이 대표적인 예시입니다.
> 
> Catched Exception
> : Exception의 서브 클래스 중 RuntimeException의 서브 클래스가 아닌 클래스들을 포함하는 Exception을 가리킵니다.
> - Compile 시점에 에러가 발생하기 때문에 에러 핸들링을 해주어야 합니다.
> - Transaction의 default 대상에 포함되지 않아 에러가 발생해도 Rollback이 자동으로 일어나지 않습니다.
> - ClassNotFoundException, IOException 등이 대표적인 예시입니다.


<br>

### :notebook_with_decorative_cover: JAVA 자료구조

1. Java의 Garbage Collection 동작 과정을 설명해주세요.

[Java Garbage Collection](https://2jinishappy.tistory.com/290)

> Garbage Collection이란 더 이상 참조되지 않는 객체를 찾아내어 Heap 메모리에서 삭제하는 과정을 말합니다.  
> Java는 GC를 위해 메모리를 Young/Old Generation으로 나누고 Young Generation을 다시 Eden/Survival 0/Survival 1영역으로 나눕니다.  
> Eden영역은 새롭게 할당된 메모리 영역을 의미하고, 이 영역에서 메모리가 차면 Minor GC가 발생, **현재 사용중인 Survival 영역**으로 개체들을 이동시킵니다.
> 해당 Survival 영역이 다 차면 또 GC가 발생하고, **사용중이지 않던 Survival 영역**으로 개체들을 이동시키는 과정을 반복합니다.  
> 이 과정에서 Age가 커진 개체들은 Old Generation 영역으로 이동합니다.

<br>

2. Java의 HashMap과 HashTable의 차이점을 설명해주세요.

[Java HashMap vs HashTable](https://2jinishappy.tistory.com/233?category=936901)

|                             | HashMap                                                                                                 | HashTable                                  |
| --------------------------- | ------------------------------------------------------------------------------------------------------- | ------------------------------------------ |
| 등장 시기                   | Java 2                                                                                                  | JDK 1.0                                    |
| Map Interface 구현 여부     | O                                                                                                       | O                                          |
| associative array 지칭 용어 | Map                                                                                                     | Dictionary                                 |
| 특징                        | - Java Collection Framework<br> - 보조 해시 함수를 이용하여 collision을 덜 발생시킴<br> - 지속적인 개선 | JRE 1.0, JRE 1.1 대상으로 하위 호환성 제공 |

<br>

3. Java의 원시타입들은 무엇이 있으며 각각 몇 바이트를 차지하는지 설명해주세요.

[Java Primitive Data Type](https://2jinishappy.tistory.com/288?category=936901)

| data type | size    |
| --------- | ------- |
| byte      | 1byte   |
| short     | 2byte   |
| int       | 4byte   |
| long      | 8byte   |
| float     | 4byte   |
| double    | 8byte   |
| boolean   | ⭐1byte |
| char      | 2byte   |

> why boolean은 1byte일까?  
> 운영하는 측에서 1bit를 관리할 수 있는 능력이 없음

<br>

4. String, StringBuffer, StringBuilder의 차이를 설명하세요.

[String vs StringBuffer vs StringBuilder](https://2jinishappy.tistory.com/259?category=936901)

<br>

![image](https://user-images.githubusercontent.com/30489264/130449865-da5859ef-6e45-45c3-9913-71b0f827cf50.png)

<br>

5. 오버라이딩과 오버로딩이 무엇이며 어떤 차이점이 있는지 설명해주세요.

[Overriding vs Overloading](https://2jinishappy.tistory.com/284?category=936900)

> Overriding: 자식(서브) 클래스가 부모(슈퍼) 클래스에 정의된 메소드를 재정의 할 수 있는 기능.
> Overloading: 같은 함수 이름, 다른 함수 파라미터를 가지는 여러 메소드를 정의할 수 있는 기능.
> 기본적으로 오버로딩은 상속, 오버라이딩은 다형성에 관련되어 있습니다.

<br>

6. Generic에 대해 설명해주세요.

<br>


### :notebook_with_decorative_cover: JAVA 라이브러리 & 프레임워크

1. '=='과 'equals()'의 차이에 대해 설명하세요.

> 기본적으로 '=='은 동일성(identity), 'equals()'는 동등성(equality)에 기반합니다.  
> 
> '=='은 비교하고 있는 두 피연산자가 같은 식별자인지, 'equals()'는 비교하고 있는 두 피연산자의 상태(value)가 동일한지 비교합니다.
> 
> 따라서 
> 
> ``` java
> String a = "Hello";
> String b = "Hello";
> 
> System.out.println(a==b);   //print false
> System.out.println(a.equals(b));  //print true
> ```
> 같은 상태를 가진 서로 다른 두 객체를 
> - '=='로 비교하면, 두 객체의 식별자가 다르기 때문에 false를 return합니다.
> - 'equals()'로 비교하면, 두 객체의 현재 상태인 value가 같기 때문에 true를 return합니다.
> 
> ``` java
> String a = new String("Hello");
> String b = new String("Hello");
> ```