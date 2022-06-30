# .equals()
- `==` : 메모리까지만 비교
- `.equals()` : 내용까지 비교

```java
import java.util.Objects;

class Person {
	int id;
	String name;

	public Person(int id, String name) {
		this.id = id;
		this.name = name;
	}

	@Override
	public String toString() {
		return "Person [id=" + id + ", name=" + name + "]";
	}

	@Override
	public int hashCode() {
		return Objects.hash(id, name);
	}

	@Override
	public boolean equals(Object obj) {
		if (this == obj)
			return true;
		if (obj == null)
			return false;
		if (getClass() != obj.getClass())
			return false;
		Person other = (Person) obj;
		return id == other.id && Objects.equals(name, other.name);
	}
}

public class App {
	public static void main(String[] args) {

		Person person1 = new Person(5, "bob");
		Person person2 = new Person(4, "sue");
		
		// 1. 당연
		System.out.println(person1 == person2); // false
		
		// 2. 당연
		person1 = person2;
		System.out.println(person1 == person2); // true

		Person person3 = new Person(6, "tom");
		Person person4 = new Person(6, "tom");
		
		// 3. semantically same but, in terms of memory they are physically two different objects
		// System.out.println(person3 == person4); // false
		
		// 4. using .equals() after overriding
		System.out.println(person3.equals(person4)); // true
		
		Double value1 = 7.2;
		Double value2 = 7.2;
		
		System.out.println(value1 == value2);
		System.out.println(value1.equals(value2));
		
		Integer number1 = 6;
		Integer number2 = 6;
		
		System.out.println(number1 == number2);
		System.out.println(number1.equals(number2));
		
		String text1 = "hello";
		String text2 = "hello";

		System.out.println(text1 == text2);
		System.out.println(text1.equals(text2));
		
		String text3 = "goodbye";
		String text4 = "goodbyeddd".substring(0,6);
		
		System.out.println(text3 == text4);
		System.out.println(text3.equals(text4));
	}
}
```