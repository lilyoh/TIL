to give method a generics as a parameter:  
base_type<parameter_type> variable_name

```java
import java.util.ArrayList;

public class App {
	public static void main(String[] args) {

		ArrayList<String> list = new ArrayList<>();
		
		list.add("one");
		list.add("two");
		list.add("three");

		showList(list);
	}

	public static void showList(ArrayList<String> list) {
		for (String value : list) {
			System.out.println(value);
		}
	}
}
```

wild card
```java
import java.util.ArrayList;

class Machine {
	
	@Override
	public String toString() {
		return "i am machine";
	}
	
	public void start() {
		System.out.println("machine start");
	}
}

class Camera extends Machine {
	
	@Override
	public String toString() {
		return "i am camera";
	}
}

public class App {
	public static void main(String[] args) {
		
		ArrayList<Machine> list = new ArrayList<>();
		
		list.add(new Machine());
		list.add(new Machine());
		
		ArrayList<Camera> list2 = new ArrayList<>();
		
		list2.add(new Camera());
		list2.add(new Camera());

		showList2(list);
		showList3(list2);
	}
	
	public static void showList(ArrayList<?> list) {
		for (Object value : list) {
			System.out.println(value);
		}
	}
	
	public static void showList2(ArrayList<? extends Machine> list) {
		for (Machine value : list) {
			System.out.println(value);
			
			value.start();
		}
	}
	
	public static void showList3(ArrayList<? super Camera> list) {
		for (Object value : list) {
			System.out.println(value);
		}
	}
}
```