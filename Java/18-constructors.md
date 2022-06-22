- constructor runs everytime when you create an instance
- you don't use void in constructor because there is no return value in constructor
- constructor method name should be same with class name, so normally method name starts with lower case but constructor name starts with upper case
- use when initializing instance variables
- can create multiple constructor
- constructor can take parameters

```java
class Machine {
	private String name;
	private int code;
	
	public Machine() {
		// below will not work
		// Machine("tori", 0);
		
		// this will work!
		// call the constructor that accepts two parameters
		// calls to constructor needs to be the first line
		this("tori", 0);
		System.out.println("constructor running");
	}
	
	public Machine(String name) {
		this(name, 0);
		System.out.println("second constructor running");
		
		// no longer need following line, since we're using the other constructor above
		// this.name = name
	}
	
	public Machine(String name, int code) {
		System.out.println("third constructor running");
		this.name = name;
		this.code = code;
	}
}

public class App {
	public static void main(String[] args) {
		
		Machine mach1 = new Machine();
		Machine mach2 = new Machine("mozzi");
		Machine mach3 = new Machine("nugi", 27);
	}
}
```