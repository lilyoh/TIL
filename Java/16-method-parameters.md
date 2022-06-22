- class에서 method를 만들 때는 1) 타입과 2) 변수  
를 적어주고 각 인스턴스에서 parameter로 전달해줄 수 있다.  
- parameter에는 1) 직접적인 값을 전달해도 되고 2) 변수를 전달해도 된다.
```java
class Robot {
	public void speak(String text) {
		System.out.println(text);
	}
	
	public void jump(int height) {
		System.out.println("jumping: " + height);
	}
	
	public void move(String direction, double distance) {
		System.out.println("moving " + distance + " in direction " + direction);
	}
}

public class App {
	public static void main(String[] args) {
		Robot sam = new Robot();
		
		sam.speak("hello i am sam");
		sam.jump(100);
		sam.move("west", 6.22);
		
		String greeting = "Hello there";
		sam.speak(greeting);
		
		int value = 14;
		sam.jump(value);
	}
}
```