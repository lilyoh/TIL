# Setters
- setters = set methods = mutators
- class 안의 data를 private으로 만들고, setter로만 접근 가능하게 만듦

# This
this = 해당 class 를 가리킴

```java
class Frog {
	private String name;
	private int age;
	
	public void setName(String name) {
		this.name = name;
	}
	
	public void setAge(int age) {
		this.age = age;
	}
	
	public String getName() {
		return name;
	}
	
	public int getAge() {
		return age;
	}
	
	public void setInfo(String name, int age) {
		setName(name);
		setAge(age);
	}
}

public class App {
	public static void main(String[] args) {
		
		Frog frog1 = new Frog();
		
//		frog1.name = "tori";
//		frog1.age = 1;
		
		frog1.setName("tori");
		frog1.setAge(7);
		
		System.out.println(frog1.getName());
		System.out.println(frog1.getAge());
		
		Frog frog2 = new Frog();
		
		frog2.setInfo("mozzi", 6);
		
		System.out.println(frog2.getName());
		System.out.println(frog2.getAge());
	}
}
```