# 제목
---

날짜: 2023-10-22
태그: #코틀린 #Inline

메모:
함수가 호출되는 대신, 함수를 호출한 지점에 함수 본문을 그대로 복붙하고 싶은 경우 사용하는 함수

예시:
```kotlin
fun main() {
	3.add(4)
}

inline fun Int.add(other: Int): Int {
	return this + other
}
```

- 함수 호출에 대한 overhead를 줄이기 위해 주로 사용

출처:
연결문서
