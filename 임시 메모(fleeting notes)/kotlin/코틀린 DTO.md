DTO는 주로 데이터를 전송하거나 다른 레이어 간에 데이터를 전달하는 데 사용됩니다. 아래는 Kotlin에서 DTO를 만들고 사용하는 간단한 예제입니다.

1. **DTO 클래스 만들기:**

   DTO 클래스를 만들 때 주요 데이터 필드를 포함하고 해당 필드에 액세스할 수 있는 getter 및 setter 메서드를 추가합니다.

   ```kotlin
   data class StudentDTO(val name: String, val age: Int)
   ```

   `data class`를 사용하면 클래스에 자동으로 getter 및 setter 메서드, `equals()`, `hashCode()`, `toString()` 등이 생성됩니다.

2. **DTO 사용하기:**

   이제 만든 DTO를 사용하여 데이터를 전달하거나 다른 레이어 간에 데이터를 교환할 수 있습니다. 아래는 간단한 예제입니다.

   ```kotlin
   // DTO 생성
   val student = StudentDTO("홍길동", 20)

   // 데이터 전송 또는 전달
   fun saveStudent(student: StudentDTO) {
       // student를 저장하거나 다른 작업 수행
   }

   saveStudent(student)
   ```

   이렇게 하면 `StudentDTO` 객체를 만들고 함수를 통해 데이터를 전송할 수 있습니다.

이것이 Kotlin에서 DTO를 만들고 사용하는 간단한 방법입니다. DTO를 사용하면 데이터 전송과 관련된 문제를 추상화하고 데이터의 일관성과 보안을 유지하는 데 도움이 됩니다.