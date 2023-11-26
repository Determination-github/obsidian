# 코틀린 Switch
---

날짜: 2023-11-02
태그: #코틀린 #switch
메모:
예시:
```kotlin
fun getGradeWtihSwitch(score: Int): String {
	return when (score) {
		9 -> "A"
		8 -> "B"
		7 -> "C"
		else -> "D"
	}
}


// 예시 2
fun getGradeWtihSwitch(score: Int): String {
	return when (score) {
		in 90..99 -> "A"
		in 80..89 -> "B"
		in 70..79 -> "C"
		else -> "D"
	}
}
```

9, in 90..99와 같이 조건부에는 어떠한 expression도 사용가능하다:
```kotlin
//java
private boolean startsWithA(Object obj) {
	if (obj instanceof String) {
		return ((String) obj).startsWith("A");
	} else {
		return false;
	}
}

//kotlin
fun startsWithA(obj: Any): Boolean {
	return when(obj) {
		is String -> obj.startsWith("A")
		else -> false
	}
}
```

여러가지 조건에 같은 결과 값이 중복될 때 사용법:
```kotlin
fun judgeNumber(number: Int) {
	when(number) {
		1, 0 , -1 -> println("여러 가지 조건")
		else -> println("1, 0, -1이 아님")
	}
}
```

출처:
연결문서
