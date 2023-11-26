```kotlin
class Person private constructor(  
    var name: String,  
    var age: Int,  
){  
      
    companion object {  
        private const val MIN_AGE = 1  
        
        @JvmStatic  
        fun newBaby(name: String): Person {  
            return Person(name, MIN_AGE)  
        }  
    }  
}
```

자바
```java
public static void main(String[] args) {  

  //@JvmStatic 어노테이션이 없는 경우
  Person.Companion.newBaby("ABC");  

  //@JvmStatic 어노테이션이 있는 경우
  Person.newBaby("ABC");  
}
```

