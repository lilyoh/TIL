# non-static inner class  
- 기능별로 그룹핑할 때 사용  
  - 로봇 -- outer class  
  - 뇌, 팔, 다리 -- inner class  

# static inner class  
- 그룹핑을 목적으로 하지는 않지만 감싸는 클래스 밖에서 사용할 니즈가 있는 클래스  

App.java
```java
public class App {
	public static void main(String[] args) {

		Robot robot = new Robot(7);
		robot.start(); // Robot 7 is thinking
		
		// Brain 을 public class로 만든다면,
		// 이렇게도 쓸 수 있음 -- 하지만 이렇게 쓰는 경우는 드묾
		// Robot.Brain brain = robot.new Brain();
		// brain.think(); // Robot 7 is thinking
		
		Robot.Battery battery = new Robot.Battery();
		battery.charge();
	}
}
```

Robot.java
```java
public class Robot {

	private int id;
	
	private class Brain {
		public void think() {
			System.out.println("Robot " + id + " is thinking");
		}
	}
	
	public static class Battery {
		public void charge() {
			System.out.println("battery is charging");
		}
	}
	
	public Robot (int id) {
		this.id = id;
	}
	
	public void start() {
		System.out.println("starting robot " + id);
		
		Brain brain = new Brain();
		brain.think();
		
		final String name = "Robert";
		
		class Temp {
			public void doSomething() {
				System.out.println("ID is: " + id);
				System.out.println("My name is " + name);
			}
		}
		
		Temp temp = new Temp();
		temp.doSomething();
	}
}
```