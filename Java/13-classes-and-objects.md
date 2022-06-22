```java
class Person {
	// instance variables (data or state)
	String name;
	int age;
	
	// classes can contain
	// 1. data
	// 2. subroutines (methods)
}

public class Application {
	public static void main(String[] args) {
		// create a person object using the person class
		Person person1 = new Person();
		person1.name = "tori";
		person1.age = 7;
		
		// create a second person object
		Person person2 = new Person();
		person2.name = "mozzi";
		person2.age = 6;
		
		System.out.println(person1.name); // tori
		System.out.println(person1.age); // 7
		System.out.println(person2.name); // mozzi
		System.out.println(person2.age); // 6
	}
}
```