# 제목
---

날짜: 2023-12-04
태그: #코틀린 #scope_function
메모:

scope function
- 일시적인 영역을 형성하는 함수
- 객체의 범위에서 코드 블록을 실행하거나 특정 객체에 대해 작업을 수행할 때 사용
- 다섯 가지 주요 Scope Function
	- let
	- run
	- with
	- apply
	- also

let
- `let`함수는 수신 객체를 람다 함수의 인자로 전달하고, 람다 함수의 결과를 반환함
- 주로 null 체크나 변환 연산을 수행할 때 사용
```kotlin
val result = someNullableValue?.let {
	// 이 블록에서는 non-null 값으로 처리됨
	// it은 non-null 값임
	// 블록의 마지막 표현식이 반환됨
	it.length
}
```


run
- `run`함수는 수신 객체에서 코드 블록을 실행하고, 람다 함수의 결과를 반환함
- `this` 키워드를 통해 수신 객체에 접근할 수 있음
 ```kotlin
 val result = someObject.run {
	 //여기서는 someObject의 멤버에 직접 접근 가능하다.
	 //블록 마지막 표현식이 반환된다.
	 this.property1 + this.property2
 }
```

with
- `with`함수는 수신 객체를 인자로 받지 않고, 코드 블록 내에서 수신 객체의 멤버에 직접 접근할 수 있도록 한다.
- `with`함수는 일반 함수로, 수신 객체를 인자로 받아서 코드 블록을 실행한 후 블록의 결과를 반환
```kotlin
val result = with(someObject) {
	//여기서는 someObejct의 멤버에 직접 접근 가능
	//블록의 마지막 표현식이 반환됨
}
```

apply
- `apply`함수는 수신 객체를 람다 함수의 리시버로 전달, 수신 객체를 반환함
- 주로 객체의 초기화 또는 설정 시 사용
```kotlin
val someObject = SomeClass().apply {
	//여기서는 someObject의 멤버에 직접 접근 가능
	property1 = "value1"
	property2 = "value2"
}
```

also
- `also`함수는 수신 객체를 람다 함수의 리시버로 전달하고, 수신 객체를 반환
- `apply`와 유사하지만

출처:
연결lllllll문서
