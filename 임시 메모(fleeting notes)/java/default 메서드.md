인터페이스에서 디폴트 메서드를 사용하는 이유는 다음과 같습니다:

1. **호환성:** 새로운 메서드를 추가할 때 기존의 인터페이스를 구현하는 클래스들이 해당 메서드를 구현하지 않아도 되므로, 기존 코드와의 호환성을 유지할 수 있습니다.
2. **확장성:** 디폴트 메서드를 사용하면 인터페이스를 수정하지 않고도 새로운 기능을 추가할 수 있습니다.
3. **코드 재사용:** 인터페이스에 공통으로 사용되는 기본 동작을 정의할 수 있으며, 구현 클래스에서 이를 재사용할 수 있습니다.
    

디폴트 메서드를 사용한 예제:

```java
// 인터페이스 정의 
interface MyInterface {     
	void someMethod(); // 추상 메서드
	     
	default void defaultMethod() {         
		System.out.println("디폴트 메서드");     
	} 
}  

// 인터페이스를 구현하는 클래스 
class MyClass implements MyInterface {     
	@Override     
	public void someMethod() {
		 System.out.println("someMethod를 구현함");     
	 } 
 }  

public class Main {     
	public static void main(String[] args) {         
		MyClass obj = new MyClass();         
		obj.someMethod(); // 구현한 메서드 호출         
		obj.defaultMethod(); // 디폴트 메서드 호출     
	} 
}
```

위의 코드에서 `MyInterface`에는 `defaultMethod`라는 디폴트 메서드가 정의되어 있습니다. 이 메서드는 기본적인 동작을 제공하며, `MyClass` 클래스에서는 `someMethod` 메서드만 구현했습니다.

`MyClass` 객체를 생성하고 `someMethod`와 `defaultMethod`를 호출할 수 있습니다. `defaultMethod`는 기본 동작을 제공하므로 `MyClass`에서 구현할 필요가 없습니다. 이렇게 디폴트 메서드를 사용하면 인터페이스를 확장하고 새로운 메서드를 추가해도 기존 코드에 영향을 미치지 않고 새로운 기능을 제공할 수 있습니다.

디폴트 메서드를 사용하면 인터페이스를 더 유연하게 확장할 수 있으며, 이미 존재하는 코드와의 호환성을 유지하면서 새로운 동작을 추가할 수 있습니다.