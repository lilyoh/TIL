App.java
```java
public class App {
	public static void main(String[] args) {
		int value = 4;
		calculate(value);
		
		System.out.println(value); // 4 -- 아래 calculate 메서드에서 무슨 짓을 하든 위의 int value 의 값은 변하지 않음
	}

	private static void calculate(int value) {
		
		value = value - 1;
		System.out.println(value); // 3
	}
}
```

App.java -- situation of stackoverflow
```java
public class App {
	public static void main(String[] args) {
		calculate(4);
	}

	private static void calculate(int value) {
		System.out.println(value);
		
		calculate(value);
	}
}
```

App.java -- 조건부 recursive
```java
public class App {
	public static void main(String[] args) {
		calculate(4);
	}

	private static void calculate(int value) {
		System.out.println(value);
		
        // value 의 값이 1이 되면 return
		if(value == 1) {
			return;
		}
		
        // value 의 값이 1이 되면 아래 코드가 실행되지 않음, 위에서 return 되었으므로
		calculate(value - 1);
	}
}
```

App.java -- factorial
```java
public class App {
	public static void main(String[] args) {
// e.g. 4! = 4*3*2*1 (factorial 4)
		
		System.out.println(factorial(3));
	}

	private static int factorial(int value) {
		
		if(value == 1) {
			return 1;
		}
		
		return factorial(value - 1) * value;
	}
}

// process
// factorial(3)
// return factorial(2) * 3;
// return factorial(1) * 2 * 3;
// return 1 * 2 * 3;
```