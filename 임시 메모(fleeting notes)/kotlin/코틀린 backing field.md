# 제목
---

날짜: 2023-10-30
태그: #코틀린 #backing_field
메모:

예시 코드:
```kotlin
class Person(
	name: String,
	var age: Int,
) {
	val name: String = name
		get() = field.uppercase() 
}
```
- val name: String = name
	- 주생성자에서 받은 name을 불변 프로퍼티 name에 바로 대입
	- name에 대한 Custom getter를 만들 때 'field'를 사용


field(backing field) 사용 이유:
예시 코드
```kotlin
class Person(
	name: String,
	var age: Int,
) {
	val name: String = name
		get() = name.uppercase()  //field대신 name사용
}
```
- field 대신 name 사용할 경우 name은 다시 get을 호출
- get은 name을 호출하고 name은 다시 get을 호출하는 무한루프 발생

이런 무한루프를 방지하기 위해, 자기 자신을 가리키는 예약어로 backing field를 사용

backing field 대신 실제 업무 시 사용할 수 있는 방법:
```kotlin

class Person(
	val name: String = "테스트"
	var age: Int = 1
) {

	//방법1: 함수이용
	fun getUppercaseName(): String = return this.name.uppercase()

	//방법2: 변수이용
	val uppercaseName: String
		get() = this.name.uppercase()
}


```

출처:
[인프런 강의](https://www.inflearn.com/course/lecture?tab=curriculum&courseSlug=java-to-kotlin&unitId=110623)

연결문서
