# 함수형 인터페이스
---

날짜: 2023-10-22
태그: #자바 #함수형인터페이스 #람다

메모:
람다 표현식을 사용할 때는 람다 표현식을 저장하기 위한 참조 변수의 타입을 결정해야 함

> 참조변수의타입 참조변수의이름 = 람다 표현식

위의 문법처럼 람다 표현식을 하나의 변수에 대입할 대 사용하는 참조 변수의 타입을 함수형 인터페이스라고 부름

함수형 인터페이스는 추상 클래스와 달리 단 하나의 추상 메서드만을 가져야 함

또한, 다음과 같은 어노테이션을 사용해 함수형 인터페이스임을 명시할 수 있음

> @FunctionalInterface

위와 같은 어노테이션을 인터페이스의 선언 앞에 붙이면, 컴파일러는 해당 인터페이스를 함수형 인터페이스로 인식

자바 컴파일러는 이렇게 명시된 인터페이스에 두 개 이상의 메서드가 선언되면 오류를 발생시킴

함수형 인터페이스를 선언하고 사용하는 예제:
```kotlin
@FuntionalInterface
interface Calc { //함수형 인터페이스 선언
	public int min(int x, int y);
}

public class Lambda {
	public static void main(String[] args){
		Calc minNum = (x, y) -> x < y ? x : y; //추상 메서드 구현
		System.out.println(minNum.min(3, 4));
	}

}


```

출처:
https://mangkyu.tistory.com/113

연결문서
[[자바 람다식]]
[[자바 익명 클래스(Anonymous Class)]]