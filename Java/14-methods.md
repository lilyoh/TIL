```java
class Person {
	// instance variables (data or state)
	String name;
	int age;
	
	// classes can contain
	// 1. data
	// 2. subroutines (methods)
	
	void speak() {
		for(int i=0; i<3; i++) {
			System.out.println("My name is " + name + " and I am " + age + " years old.");
		}
	}
	
	void sayHello() {
		System.out.println("Hello!");
	}
}

public class Application {
	public static void main(String[] args) {
		Person person1 = new Person();
		person1.name = "tori";
		person1.age = 7;
		person1.speak();
		person1.sayHello();
	}
}
```

My name is tori and I am 7 years old.  
My name is tori and I am 7 years old.  
My name is tori and I am 7 years old.  
Hello!
