Java에서 `final` 키워드는 클래스, 메서드 및 변수에 대한 다양한 제한을 적용하는데 사용되는 한정자이다. Java의 다양한 요소에 `final`을 적용하면 서로 다른 의미와 목적을 갖게 된다.

`final`키워드의 주요 사용 사례들과 예제:

1. **Final Variable:**
    - 변수에 `final` 키워드를 적용하면 해당 변수를 상수 또는 변경할 수 없는 변수로 만든다.
    - 이는 변수의 값을 할당한 후 수정할 수 없음을 의미
    - 최종 변수는 정확히 한 번 값이 할당되어야 하며, 변수 선언 시 또는 생성자에서 값이 할당되어야 함

Example of a final variable:

```java
public class MyClass {     
	final int myConstant = 42;      
	
	public void myMethod() {         
		// 여기에서 myConstant의 값을 변경할 수 없다.
		// myConstant = 10; => 컴파일 오류 발생
	} 
}
```

2. **Final Method:**
    - 메서드 `final`키워드를 적용하면 해당 메서드가 하위 클래스에서 오버라이딩되지 못하도록 방지한다.
    - 하위 클래스는 최종 메서드의 자체 구현을 제공할 수 없다.

Example of a final method:

```java
public class ParentClass {     

	public final void finalMethod() {         
	// 이 메서드는 하위 클래스에서 오버라이딩 할 수 없음  
	} 
}  

public class ChildClass extends ParentClass {     
// finalMehtod를 오버라이딩하려고 하면 컴파일 에러 발생
}
```


3. **Final Class:**
    - `final`키워드를 클래스에 적용하면 해당 클래스를 상속할 수 없게 만든다.
    - 최종 클래스의 하위 클래스를 만들 수 없다.

Example of a final class:

```java
final class FinalClass {     
	// 이 클래스는 다른 클래스에서 확장될 수 없음
}  

// FinalClass의 하위 클래스를 만들려고 하면 컴파일 에러 발생
```

`final` 키워드는 변수의 값을 메서드의 구현을 또는 클래스의 확장을 변경할 수 없게 한다. 때문에 Java에서 불변성 및 보안 및 예측 가능성을 강제하기 위한 도구로 사용된다.
