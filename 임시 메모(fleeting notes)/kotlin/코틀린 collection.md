# 코틀린 컬렉션
---

날짜: 2023-10-22
태그: #코틀린 #컬렉션 #collection 
메모:

가변 (Mutable) 컬렉션 
- 컬렉션에 element를 추가, 삭제할 수 있다.
- 기본 구현체는 ArrayList

불변 컬렉션
- 컬렉션에 element를 추가, 삭제할 수 없다.
- 예) Collections.unmodifiableList()
- 불변 타입의 컬렉션도 Reference Type인 Element의 필드는 바꿀 수 있다.

 > 코틀린에서는 불변/가변 컬렉션을 반드시 명시해줘야 한다 **


> 기본적으로 불변 리스트를 만들고, 꼭 필요한 경우 가변 리스트로 바꾼다.


List
기본적인 사용법
```kotlin
fun main() {
	val numbers = mutableListOf(100, 200)
	numbers.add(300)

	println(numbers[0])

	for (number in numbers) {
		println(number)
	}

	for ((idx, value) in numbers.withIndex()) {
		println("${idx} ${value}")
	}
}
```

Set
- 중복이 제거되는 것을 제외하고 List와 동일

Map
기본적인 사용법
```kotlin

fun main() {
	val oldMap = mutableMapOf<Int, String>()
	oldmap[1] = "MONDAY"
	oldmap[2] = "TUESDAY"
// 자바처럼 PUT 사용도 가능

	mapOf(1 to "MONDAY", 2 to "TUESDAY")

	for (key in oldMap.keys) {
		println(key)
		println(oldmap[Key])
	}

	for ((key, value) in oldMap.entries) {
		println(key)
		println(value)
	}

}
```


컬렉션의 null 가능성
1. List<Int?> : 리스트에 null이 들어갈 수 있지만, 리스트는 절대 null이 아님
2. List<Int\>? : 리스트에는 null이 들어갈 수 없지만, 리스트는 null일 수 있음
3. List<Int?>? : 리스트에 null이 들어갈 수도 있고, 리스트가 null일 수도 있음

> 자바와의 차이점:
> 자바는 읽기 전용 컬렉션과 변경 가능 컬렉션을 구분하지 않는다.
> 
> 즉, 코틀린 쪽 컬렉션이 자바에서 호출되면 컬렉션 내용이 변할 수 있음을 감안해야 함
> 
> 코틀린 쪽에서 Collections.unmodifalbeXXX()를 활용하면 변경 자체를 막을 순 있음


출처: [자바 개발자를 위한 코틀린 입문 강의]
연결문서
