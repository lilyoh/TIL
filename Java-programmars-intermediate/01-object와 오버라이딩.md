# Object
- Object 클래스는 모든 클래스의 최상위 클래스
- 아무것도 상속받지 않으면 자동으로 Object를 상속
- Object가 가지고 있는 메소드는 모든 클래스에서 다 사용할 수 있다는 것을 의미

오브젝트 메서드 중에서 가장 많이 사용되는 메서드는
- equals : 객체가 가진 값을 비교할 때 사용 (메모리 주소가 아닌 실제 값을 비교할 수 있음)
- toString : 객체가 가진 값을 문자열로 반환
- hashCode : 객체의 해시코드 값 반환  

위의 3가지 메서드는 꼭 "오버라이딩" 해서 사용해야 함

```java
import java.util.Objects;

public class Student {

	String name;
	String number;
	int birthYear;
	
	@Override
	public int hashCode() {
		return Objects.hash(number);
	}

	@Override
	public boolean equals(Object obj) {
		if (this == obj)
			return true;
		if (obj == null)
			return false;
		if (getClass() != obj.getClass())
			return false;
		Student other = (Student) obj;
		return Objects.equals(number, other.number);
	}
	
	@Override
	public String toString() {
		return "Student [name=" + name + ", number=" + number + ", birthYear=" + birthYear + "]";
	}

	public static void main(String[] args) {
		Student s1 = new Student();
		s1.name = "홍길동";
		s1.number = "1234";
		s1.birthYear = 1995;
		
		Student s2 = new Student();
		s2.name = "홍길동";
		s2.number = "1234";
		s2.birthYear = 1995;
		
		if(s1.equals(s2))
			System.out.println("s1 == s2");
		else
			System.out.println("s1 != s2");
		
		System.out.println(s1.hashCode());
		System.out.println(s2.hashCode());
		
		System.out.println(s1);
		System.out.println(s1.toString());
	}
}
```