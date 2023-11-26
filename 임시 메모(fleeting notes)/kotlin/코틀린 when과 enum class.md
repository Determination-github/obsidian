
# 코틀린 when과 enum class
--- 
날짜: 2023-10-30
태그: #코틀린 #enum #when
메모:

```kotlin
fun handleCountry(country: Country) {  
    when (country) {  
        Country.KOREA -> println("한국")  
        Country.AMERICA -> println("미국")  
    }  
}  
  
enum class Country(  
    private val code: String,  
) {  
    KOREA("KR"),  
    AMERICA("US")  
    ;  
}
```

- country는 KOREA와 AMERICA만 가능하므로 else 구분 없이 작성할 수 있음

출처:
연결문서
[[코틀린 enum]]
