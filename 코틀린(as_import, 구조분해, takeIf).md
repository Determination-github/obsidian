# 코틀린(as_import, 구조분해, takeIf)
---

날짜: 2023-12-04
태그: #코틀린 #as_import #구조분해 #componentN #TakeIf #TakeUnless
메모:

as import
- 패키지 또는 클래스를 다른 이름을 가져올 때 사용
- 예시:
```Kotlin
import com.example.mypackage.MyClass as CustomName

fun main() {
    val instance = CustomName()
    // 이제 "instance"는 "MyClass"의 인스턴스와 같습니다.
}
```
- `MyClass`를 `CustomName`으로 가져옴

구조분해
- 데이터 클래스나 배열등의 복합 데이터 유형에서 그 안에 포함된 개별 요소들을 분리해 여러 변수에 할당하는 기능
- 예시:
```kotlin
data class Person(val name: String, val age: Int)

fun main() {
	val person = Person("Alice", 30)

	//구조분해선언
	val (name, age) = person
	// val name = person.component1()
	// val age = person.component2()

	println("Name: $name, Age: $age")
}
```
- data 클래스가 componentN함수를 구현해줌
- 예시 - 배열의 구조 분해:
```kotlin
fun main() {
    val numbers = arrayOf(1, 2, 3, 4, 5)
    
    // 구조 분해 선언
    val (a, b, _, _, c) = numbers
    
    println("a: $a, b: $b, c: $c")
}
```
- 여기서 '\_'는 해당 위치의 값을 무시하고 건너뛰는 데 사용됨
- Data 클래스가 아닌 경우 componentN을 구현하여 사용할 수 있음
- 예시:
```kotlin
class Person{
	val name: String,
	val age: Int
} {
	operator fun component1(): String {
		return this.name
	}

	operator fun componenet2(): Int {
		return this.age
	}
}
```


TakeIf와 TakeUnless
- 코틀린의 표준 라이브러리
- 주어진 조건을 만족하는 경우에만 수행되도록 하는 기능

TakeIf
- `takeIf`함수는 주어진 조건이 참일 경우에만 수행
- 그렇지 않은 경우 'Null'을 반환
- 주로 'If'문을 대체하여 사용
- 예시
```kotlin
val number = 42
val result = number.takeIf { it > 0 }
```


TakeUnless
- `takeIf`와 반대 동작을 수행함
- 즉, 주어진 조건이 거짓일 경우에만 수행되고, 조건이 참이면 'Null'을 반환
- 예시
```kotlin
val number = 42
val result = number.takeUnless { it <= 0 }
```



출처: 자바 개발자를 위한 코틀린 입문
연결문서
