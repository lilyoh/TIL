- what to learn
  - how enum works behind the scenes
  - what enum "constants" actually are
  - how to transform between enum constants and strings (useful for working with databases)

- what is "enum"
  - predefined list of values
  - lists of constants like unchangeable variables (think of final keyword)

- if you use enum
    1. you increase compile-time checking
    2. avoid errors from passing in invalid constants
    3. document which values are legal to use

App.java
```java
public class App {
	public static void main(String[] args) {

		Animal animal = Animal.DOG;
		
		switch(animal) {
		case CAT:
			System.out.println("Cat");
			break;
		case DOG:
			System.out.println("Dog"); // Dog
			break;
		case MOUSE:
			break;
		default:
			break;
		}
		
		System.out.println(Animal.DOG); // This animal is called: Fido
		System.out.println("Enum name as a string: " + Animal.DOG.name()); // Enum name as a string: DOG
		
		System.out.println(Animal.DOG.getClass()); // class Animal
		
		System.out.println(Animal.DOG instanceof Enum); // true
		
		System.out.println(Animal.MOUSE.getName()); // Jerry
		
		Animal animal2 = Animal.valueOf("CAT");
		System.out.println(animal2); // This animal is called: Fergus
	}
}
```

Animal.java
```java
public enum Animal {
	CAT("Fergus"), DOG("Fido"), MOUSE("Jerry");
	
	private String name;
	
	// constructor
	Animal(String name) {
		this.name = name;
	}
	
	public String getName() {
		return name;
	}
	
	public String toString() {
		return "This animal is called: " + name;
	}
}
```