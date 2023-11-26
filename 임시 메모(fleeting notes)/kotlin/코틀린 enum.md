# 코틀린 enum
---

날짜: 2023-10-30
태그: #코틀린 #enum
메모:
코틀린의 enum은 자바와 마찬가지로 단순히 값만 열거하는 존재가 아니다.
enum 클래스 안에도 프로퍼티나 메서드를 정의할 수 있다.

enum 클래스 예시:
```kotlin
enum class Color (
	var r: Int, val g: Int, val b: Int
) {
	RED(255, 0, 0), ORANGE(255, 165, 0),
	YELLOW(255, 255, 0), GREEN(0, 255, 0),
	BLUE(0, 0, 255); //-> 여기선 반드시 세미콜론을 사용해야 함

	fun rgb() = (r * 256 + g) * 256 + b //-> enum 클래스 안에서 메서드 정의
}

println(Color.BLUE.rgb()) //255
```
- enum 클래스 안에 메서드를 정의하는 경우 반드시 enum 상수 목록과 메서드 정의 사이에 세미콜론을 넣어야 한다.


출처: 코틀린인액션
연결문서
