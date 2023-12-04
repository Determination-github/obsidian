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

|              | it 사용    | this 사용 |
| ------------ | ---------- | --------- |
| 람다의 결과  | let        | run       |
| 객체 그 자체 | also, with | apply     |
- this: 생략이 가능한 대신, 다른 이름을 붙일 수 없다.
- it: 생략이 불가능한 대신, 다른 이름을 붙일 수 있다.

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
- 객체 초기화와 반환 값의 계산을 동시에 해야 할 대 사용
- `this` 키워드를 통해 수신 객체에 접근할 수 있음
 ```kotlin
 val result = someObject.run {
	 //여기서는 someObject의 멤버에 직접 접근 가능하다.
	 //블록 마지막 표현식이 반환된다.
	 this.property1 + this.property2
}

//객체를 만들어 DB에 바로 저장하고, 그 인스턴스를 활용할 때
val person = Person("A", 30).run(personReposiotry::save)
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
- `apply`와 유사하지만, `also`는 블록의 마지막 표현식이 아닌 수신 객체 자체를 반환함
- 주로 객체를 생성하고 그에 대한 추가 작업을 수행할 때 사용
```kotlin
val someObject = SomeClass().also {
	//여기서는 someObject의 멤버에 직접 접근이 가능
	//마지막 표현식이 아니라 객체 자체를 반환
	it.property1 = "value1"
	it.property2 = "value2"
}
```

출처:
연결lllllll문서
