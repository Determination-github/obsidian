DTO(데이터 전송 객체)는 Java에서 데이터를 전송하거나 서로 다른 계층 간에 데이터를 교환할 때 사용되는 패턴입니다. DTO는 데이터를 포장하고, 데이터베이스에서 가져온 데이터나 웹 요청과 같은 다양한 소스에서 데이터를 추상화합니다. 이를 통해 데이터를 효율적으로 전송하고 유지보수를 쉽게 할 수 있습니다. 아래는 DTO 패턴을 설명하는 예제와 함께 간단한 DTO 클래스의 예시입니다.

**DTO 클래스의 예제:**

DTO 클래스는 데이터 필드와 해당 필드에 액세스할 수 있는 getter와 setter 메서드로 이루어집니다.

```java
public class StudentDTO {
    private String name;
    private int age;

    public StudentDTO(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
```

**DTO 패턴의 사용 예:**

예를 들어, 웹 애플리케이션에서 사용자로부터 학생 정보를 입력받고 이를 서버로 전송하는 경우 DTO 클래스를 사용할 수 있습니다.

```java
// 웹 애플리케이션의 서블릿에서 DTO를 사용하는 예제
@WebServlet("/addStudent")
public class StudentServlet extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        // 웹 요청으로부터 학생 정보 추출
        String name = request.getParameter("name");
        int age = Integer.parseInt(request.getParameter("age"));

        // DTO 객체에 데이터 설정
        StudentDTO student = new StudentDTO(name, age);

        // DTO 객체를 서비스나 데이터베이스 계층으로 전달
        StudentService.addStudent(student);
    }
}
```

이렇게 DTO를 사용하면 웹 요청에서 데이터를 추출하고, 비즈니스 로직이나 데이터베이스 계층으로 데이터를 효과적으로 전달할 수 있습니다. DTO 패턴은 데이터 전송과 관련된 문제를 추상화하고, 데이터의 일관성과 보안을 보장하기 위한 좋은 방법입니다.