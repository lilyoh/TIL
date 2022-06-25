a way of
- extending existing class
- implementing interface

 ```java
class Machine {
	public void start() {
		System.out.println("starting machine");
	}
}

interface Plant {
	public void grow();
}

public class App {
	public static void main(String[] args) {
		
		// This is equivalent to creating a class that "extends"
		// Machine and overrides the start method
		Machine machine1 = new Machine() {
			@Override public void start() {
				System.out.println("camera snapping");
			} 
		};
		
		machine1.start();

		// This is equivalent to creating a class that "implements"
		// Plant interface
		Plant plant1 = new Plant() {
			@Override public void grow() {
				System.out.println("plant growing");
			}
		};
		
		plant1.grow();
	}
}
```