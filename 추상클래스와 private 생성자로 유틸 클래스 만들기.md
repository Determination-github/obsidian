### 유틸리티 클래스
- 주로 인스턴스별 상태를 필요로하지 않는 관련된 메서드를 그룹화하는 데 사용되는 클래스
- 일반적으로 애플리케이션 전체에서 재사용될 수 있는 일반적인 작업 또는 기능을 위해 사용
- 이런 유틸리티 클래스에서 인스턴스가 생성되지 않도록 하려면 추상 클래스와 비공개(private) 생성자를 사용하는 것이 일반적

다음은 추상 클래스와 비공개(private) 생성자를 사용하여 구현된 유틸리티 클래스의 예제:

```java
public abstract class MathUtils {     
	private MathUtils() {         
		// 인스턴스 생성을 방지하기 위한 비공개(private) 생성자     
	}      
	
	public static int add(int a, int b) {         
		return a + b;     
	}      
	
	public static int subtract(int a, int b) {         
		return a - b;     
	}      
	
	public static int multiply(int a, int b) {        
		return a * b;     
	}      
	
	public static double divide(int a, int b) {         
		if (b == 0) {             
			throw new IllegalArgumentException("0으로 나누는 것은 허용되지 않습니다.");
		}         
		
		return (double) a / b;     
	} 
}
```


- 이 예제에서 `MathUtils` 클래스는 인스턴스가 생성되지 않도록 하기 위해 비공개(private) 생성자와 함께 추상 클래스로 정의된다. 
- 이 클래스는 덧셈, 뺄셈, 곱셈 및 나눗셈과 같은 수학적 연산을 수행하는 정적(static) 메서드만을 포함한다. 
- 이 클래스는 유틸리티 클래스로 사용되며 클래스의 인스턴스를 생성할 필요 없이 이러한 메서드를 호출할 수 있도록 한다.

이 유틸리티 클래스는 다음과 같이 사용할 수 있습니다:

```java
public class Main {     
	public static void main(String[] args) {         
		int result1 = MathUtils.add(5, 3);         
		System.out.println("5 + 3 = " + result1);          
	
		int result2 = MathUtils.subtract(10, 4);         
		System.out.println("10 - 4 = " + result2);          
		
		int result3 = MathUtils.multiply(6, 7);         
		System.out.println("6 * 7 = " + result3);          
		
		double result4 = MathUtils.divide(12, 4);         
		System.out.println("12 / 4 = " + result4);     
	} 
}
```
이 유틸리티 클래스는 관련된 수학 함수를 편리하게 그룹화하고 클래스의 인스턴스를 실수로 생성하지 않도록 보장하는데 사용된다. 이러한 방식은 Java에서 유틸리티 클래스를 생성하는 흔한 관행