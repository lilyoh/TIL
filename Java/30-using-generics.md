# Generics
- the object that can work with other objects  
- can specify what type of object to work with  
- when you create object from the class  

```java
import java.util.ArrayList;
import java.util.HashMap;

class Plant {
	
}

public class App {
	public static void main(String[] args) {
		
		// before java 5
		ArrayList list = new ArrayList();
		
		list.add("apple");
		list.add("banana");
		list.add("orange");
		
		String fruit = (String)list.get(1); // should cast because list.get() will return object
		System.out.println(fruit);
		
		// java 5 -- generics introduced
		// can parameterize what type you will work with
		// how to use : base_type<parameter_type>
		ArrayList<String> strings = new ArrayList<String>();
		
		strings.add("cat");
		strings.add("dog");
		strings.add("elephant");
		
		String animal = strings.get(1); // don't have to cast because you already specified what type to return
		System.out.println(animal);
		
		// there can be more than one type argument
		HashMap<Integer, String> map = new HashMap<Integer, String>();
		
		// java 7 style
		// <> 안에는 기존 클래스 말고도 custom 클래스를 넣을 수 있음
		// 뒤의 <>는 생략 가능
		ArrayList<Plant> plants = new ArrayList<>();
	}
}
```
