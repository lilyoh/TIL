# Inheritance
a 클래스가 b 클래스를 상속하게 하는 방법  
-> extends 뒤에 상속하고 싶은 부모 클래스의 이름을 적어줌
```java
public class Car extends Machine {
}
```

b 클래스를 상속받은 a 클래스가 b 클래스의 메서드를 override 하는 방법  
-> 부모 클래스(b)의 메서드를 그대로 가져와서 수정  
-> annotation을 붙이면 오류 체크 가능
```java
    // annotation below will check whether 
    // method name is same as its parent
	@Override
	public void start() {
		System.out.println("Car started.");
	}
```

# Public, Private, Protected
variable 선언 방법
- public : 모든 클래스에서 access 가능
- private : 해당 클래스 블록 내에서만 access 가능
- protected : 자식 클래스에서만 access 가능
---
전체 코드

App.java
```java
public class App {
    public static void main(String[] args) {

        Machine mach1 = new Machine();

        mach1.start();
        mach1.stop();

        Car car1 = new Car();

        System.out.println("---");

        car1.start();
        car1.stop();
        car1.wipe();
        // code below won't work
        car1.showInfo();
    }
}

```

Machine.java
```java
public class Machine {

    private String name = "Machine type 1";

    public void start() {
        System.out.println("Machine started.");
    }

    public void stop() {
        System.out.println("Machine stopped.");
    }
}
```

Car.java
```java
public class Car extends Machine {

	// annotation below will check whether method name is same as its parent
	@Override
	public void start() {
		System.out.println("Car started.");
	}
	
	public void wipe() {
		System.out.println("Wiping!");
	}
	
	public void showInfo() {
		System.out.println("Car name: " + name);
		// error! The field Machine.name is not visible.
		// because name is private variable
	}
}

```