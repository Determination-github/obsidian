
### [Kotlin Object](https://superohinsung.tistory.com/83#Kotlin%20Object-1)

- 코틀린에는 독특한 싱글턴(singleton : 인스턴스가 하나만 있는 클래스) 선언 방법이 있다. 그것이 바로 Object이다.
- 코틀린에서는 object 키워드를 사용해서 별다른 정의 없이 싱클톤 구현을 지원해준다.
- 자바에서 클래스 내부에 static 객체로 한번만 할당해주던 코드를 코틀린에서는 object 키워드를 쓴 클래스로 구현해서 static 객체에 할당해주는 것 처럼 자동으로 생성해준다.


>싱글톤이란? 
  싱글톤은 인스턴스가 하나만 있는 클래스를 의미한다.


예시)
```kotlin
object MySingleton {
	fun doSomething() {
		println("Singleton instance")
	}
}

fun main() {
	MySingleton.doSomethong()

}
```

1. 코틀린의 싱글톤은 지연로딩된다.
2. 기본적으로 스레드에 안전하다. 
3. 보통 클래스처럼 프로퍼티나 메서드 등을 가질 수 있다.
4. 싱글톤 오브젝트는 다른 프로그래밍 언어의 static 클래스와 비슷하지만, 싱글톤 오브젝트는 클래스를 상속받거나 인터페이스를 구현할 수 있다.



### Companion Object
자바에서 static과 같이 kotlin에서 'companion object'는 클래스와 관련된 멤버(속성 및 메서드)를 만드는데 사용된다.

 `companion object`에 관한 주요 사항:

1. **Single Instance:** `companion object`는 클래스의 모든 인스턴스 사이에서 공유되는 단일 인스턴스로 하나의 인스턴스만 존재한다.
2. **인스턴스없이 액세스:** `companion object` 의 멤버에 대한 인스턴스를 생성하지 않고 액세스할 수 있다.
3. **이름:** 기본적으로 `companion object`는 'companion'이라는 이름을 가지지만, 필요한 경우 사용자 정의 이름을 부여할 수 있다.
4. **상속:** 클래스는 하나의 `companion object`만 가질 수 있으며, 상속할 수 없다.
    
`companion object` in Kotlin:

```kotlin
class MyClass {     
	companion object {         
		val someProperty = 42          
		
		fun someFunction() {            
			println("This is a function in the companion object")         
		}     
	} 
}  

fun main() {     
	println(MyClass.someProperty)  // Accessing a property from the companion object     
	MyClass.someFunction()         // Calling a function from the companion object }`
```

위 예시에서 `companion object`는 MyClass 클래스 내부에서 정의됐다. 때문에 클래스 이름(MyClass) 뒤에 `companion object`의 이름을 사용하여 그 속성과 메서드에 접근할 수 있다. 이런 방식은 클래스 수준의 기능과 상수를 캡슐화하고 구성하는 편리한 방법이다.

`companion object`는 코틀린의 강력한 기능으로 클래스와 관련된 기능을 구성하고 중앙화하는데 사용되며, 주로 팩토리 메서드를 생성하거나 상수를 정의하거나 클래스와 관련된 유틸리티 메서드를 제공하는데 사용된다.


자바에서 Kotlin의 Companion Object를 사용하려면?
```kotlin
companion object {
	private const val MIN_AGE = 0

	@JvmStatic
	fun newBaby(name: String): Person {
		return Person(name, MIN_AGE)
	}
}

//자바
Person person = Person.newBaby("A");
```