# abstract class
- allows you to define the parent class of a new hierarchy without having to worry about the user
actually instantiating the parent
- interface와의 차이?
  - interface는 단순히 기능을 끌어다 쓰는 것
  - abstract class를 쓰면 정체성(뿌리)를 더 명시할 수 있게 됨

App.java
```java
public class App {
	public static void main(String[] args) {

		Camera cam1 = new Camera();
		cam1.setId(5);
		
		Car car1 = new Car();
		car1.setId(4);
		
		car1.run();
		
		// won't work
		// Machine mach1 = new Machine();
	}
}
```

Machine.java
```java
public abstract class Machine {

	private int id;
	
	public int getId() {
		return id;
	}
	
	public void setId(int id) {
		this.id = id;
	}
	
	public abstract void start();
	public abstract void doStuff();
	public abstract void shutDown();
	
	public void run() {
		start();
		doStuff();
		shutDown();
	}
}
```

Camera.java
```java
public class Camera extends Machine {

	@Override
	public void start() {
		System.out.println("Starting camera");
	}

	@Override
	public void doStuff() {
		System.out.println("Taking a photo");
	}

	@Override
	public void shutDown() {
		System.out.println("Shutting down the camera");
	}

}
```

Car.java
```java
public class Car extends Machine {

	@Override
	public void start() {
		System.out.println("Starting ignition");
	}

	@Override
	public void doStuff() {
		System.out.println("Driving");
	}

	@Override
	public void shutDown() {
		System.out.println("Switch off ignition");
	}
}
```