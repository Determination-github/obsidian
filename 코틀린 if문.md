# 코틀린 if문
---

날짜: 2023-11-02
태그: #코틀린 #if #statement #expression 
메모:

자바의 if문과 코틀린의 if문은 형태적으로 거의 동일
차이점:
- 자바의 경우 if가 문(statement)이다.
- 코틀린은 if가 expression이다.

자바의 if도 return값이 있는데 expression이 될 수 없는 이유?
코틀린은 if문 자체를 리턴할 수 있음:
```kotlin
fun getPassOrFail(score: Int): String {
	return if (score >= 50) //if식 자체를 리턴
		"P"
	} else {
		"F"
	}
}
```

코틀린에서 3항 연산자
- if-else문을 expression으로 사용할 수 있기 때문에 3항 연산자가 없다.

출처:
연결문서
