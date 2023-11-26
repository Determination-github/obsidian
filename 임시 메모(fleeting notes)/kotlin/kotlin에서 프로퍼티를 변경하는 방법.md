1. backing field를 이용
```kotlin  
class Person(name: String, var age: Int) {  
    // 주 생성자에서 받은 name을 불변 프로퍼티 name에 바로 대입  
    // name에 대한 Custom getter를 만들 때 field를 사용해야 함  
    // 필드를 사용해야 하는 이유  
    // - getter에서 name을 사용하면 getter를 호출할 때마다 getter가 호출되어 무한루프에 빠짐  
    // - 즉 아래 예제에서 name.uppercase()의 name은 getter를 호출해 다시 get을 부름  
    // - get() 안에는 name이 있기 때문에 무한루프가 발생  
    // field는 무한루프를 막기 위한 예약어로 자기 자신을 가리킨다.  
    // - field는 자기 자신을 가리키는 보이지 않는 field => backing field    
    val name: String = name  
        get() = field.uppercase()  
}  
```


2. 함수나 프로퍼티를 이용하는 방법
```kotlin  
class Person(val name: String, var age: Int) {  

	fun getUppercaseName(): String {
		return this.name.uppercase()
	}

	val uppercaseName: String
		get() = this.name.uppercase()
   
}  