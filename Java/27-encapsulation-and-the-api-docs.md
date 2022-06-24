```java
class Plant {
	// usually only static final members are public
	public static final int ID = 7;
	
	// instance variables should be declared private,
	// or at least protected
	private String name;
	
	// only method intended for use outside the class should be public
	// these methods should be documented carefully if you distribute your code
	public String getData() {
		String data = "some stuff" + calculateGrowthForecast();
		return data;
	}
	
	// methods only used in the class itself should
	// be private or protected
	private int calculateGrowthForecast() {
		return 9;
	}

	public String getName() {
		return name;
	}

	public void setName(String name) {
		this.name = name;
	}
}

public class App {
	public static void main(String[] args) {
		
	}
}
```