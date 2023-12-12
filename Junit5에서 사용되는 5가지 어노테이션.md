# 제목
---

날짜: 2023-12-12
태그:
메모:

Junit의 5가지 어노테이션
@Test: 테스트 메소드를 지정한다. 테스트 메서드를 실행하는 과정에서 오류가 없으면 성공
@BeforeEach: 각 테스트 메서드가 수행되기 전에 실행되는 메서드를 지정
@AfterEach: 각 테스트가 수행된 후에 실행되는 메서드를 지정
@BeforeAll: 모든 테스트를 수행하기 전에 최초 1회 수행되는 메서드를 지정
@AfterAll: 모든 테스트를 수행한 후 최초 1회 수행되는 메서드를 지정

> @BeforeAll과 @AfterAll에는 @JvmStatic을 붙여야 한다.
> Kotlin은 기본적으로 클래스 멤버 함수를 정적 함수로 간주하지 않는다. 하지만 '@JvmStatic' 어노테이션을 사용하면 Kotlin 컴파일러에게 해당 함수를 정적 메서드로 처리하도록 지시할 수 있다. @BeforeAll과 @AfterAll은 정적 메서드로 정의되어야 해서 @JvmStatic 어노테이션을 붙인다.


단언문
- 테스트 검증 메서드 중 하나
- 'assertThat' 메서드 자체는 JUnit에 포함되어 있지 않고, AssertJ 라이브러리에서 제공
- 'assertThat'을 사용하면 테스트에서 예상되는 결과와 실제 결과를 비교할 수 있다.

단언문 메서드
- isEqualTo
- isNotNull
- isNull
- isTrue/isFalse
- isInstanceOf
- isNotInstanceOf
- isNotEmpty/isEmpty
- contains
- containsExactly
- hasSize
- startsWith/endsWith

asserThrows
- 예외가 발생하는지 여부를 확인하기 위해 사용되는 AssertJ의 메서드
- 주어진 코드 블록이 실행될 때 예외가 발생하면 성공하고, 예외가 발생하지 않으면 실패
- 예시)
```kotlin
@Test  
fun testException() {  
    val exception: Throwable = assertThrows(Exception::class.java) {  
        // 예외가 발생할 코드  
        throw Exception("예외 메시지")  
    }  
  
    // 예외 메시지 확인  
    assertThat(exception.message).isEqualTo("예외 메시지")  
    assertEquals("예외 메시지", exception.message)  
}
```


> assert

출처:
연결문서
