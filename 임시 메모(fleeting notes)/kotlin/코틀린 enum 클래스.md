'enum class'는 Java에서 열거형(Enumeration)으로 정의된 클래스를 나타냅니다. 이것은 서로 연관된 상수 집합을 나타내는 클래스 유형이며, 'enum' 키워드로 선언됩니다. 'enum class'는 인터페이스(interface)를 구현할 수 있으며, 각 열거 상수는 자신의 독립적인 인스턴스를 가집니다. 아래에는 'enum class'를 한국어로 설명하고, 인터페이스를 구현하는 예제를 제시합니다.

**'enum class' 생성 예:**

먼저, 'enum class'를 만들어 보겠습니다. 예를 들어, 커피 사이즈를 나타내는 'CoffeeSize' 열거형을 만들어봅시다.

```java
public enum CoffeeSize {
    SMALL, MEDIUM, LARGE
}
```

이제 'CoffeeSize' 열거형은 세 가지 커피 사이즈를 나타내는 상수를 가지고 있습니다.

**'enum class'에서 인터페이스 구현 예:**

'enum class'는 인터페이스를 구현할 수 있으며, 각 열거 상수는 해당 인터페이스의 메서드를 구현할 수 있습니다. 예를 들어, 'Drink' 인터페이스를 구현하는 'Coffee' 열거형을 만들어봅시다.

```java
public enum Coffee implements Drink {
    ESPRESSO(1.99), LATTE(2.49), CAPPUCCINO(2.99);

    private double price;

    Coffee(double price) {
        this.price = price;
    }

    @Override
    public double getPrice() {
        return price;
    }
}
```

이 예제에서 'Coffee' 열거형은 'Drink' 인터페이스를 구현하고, 각 열거 상수(ESPRESSO, LATTE, CAPPUCCINO)는 'getPrice' 메서드를 구현합니다. 이렇게 하면 커피 종류와 가격을 나타낼 수 있습니다.

'enum class'를 사용하면 코드의 가독성을 향상시키고, 서로 다른 상수 간의 관련성을 명확하게 표현할 수 있으며, 인터페이스를 구현함으로써 각 열거 상수가 특정 메서드를 가질 수 있습니다.


