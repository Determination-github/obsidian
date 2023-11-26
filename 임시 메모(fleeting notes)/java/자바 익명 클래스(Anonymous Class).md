### 익명 클래스
- 이름이 없는 클래스
- 주로 인터페이스 또는 추상 클래스의 인스턴스를 생성하고 구현하기 위해 사용
- Java 8 이후에는 람다 표현식을 사용하여 익명 클래스를 더 간결하게 정의할 수 있다.

#### 익명 클래스
클래스의 이름이 없고, 클래스를 선언하면서 동시에 인스턴스를 생성하는 방법, 주로 인터페이스나 추상 클래스의 메서드를 구현하거나 재정의할 때 사용된다.

예를 들어, 'Runnalble' 인터페이스를 구현하는 익명 클래스를 생성하고 사용하는 코드는 다음과 같다:
```java
public class Main {
	public static void main(String[] args) {
		//익명 클래스로 Runnable 구현
		Runnable runnable = new Runnable() {
			@Override
			public void run() {
				System.out.println("익명 클래스로 구현된 Runnable 실행")
			}
		};

		//익명 클래스로 생성한 인스턴스 실행
		Thread thread = new Thread(runnable);
		thread.start();
	}
}
```


#### 람다 표현식
위의 예제를 람다 표현식으로 표현하면 다음과 같다:
```java
public class Main {
	public static void main(String[] args) {
		//익명 클래스로 Runnable 구현
		Runnable runnable = () -> {
			System.out.println("람다 표현식으로 구현된 Runnable 실행")
		}

		//익명 클래스로 생성한 인스턴스 실행
		Thread thread = new Thread(runnable);
		thread.start();
	}
}
```


