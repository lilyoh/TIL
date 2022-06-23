# StringBuilder
1. everytime you use += to append string, you are creating a new string
2. modify existing string
3. append method returns reference to string object, can use method chaining

```java
public class App {

	public static void main(String[] args) {

		// 1. inefficient
		String info = "";

		info += "My name is tori";
		info += " ";
		info += "I am a builder.";

		System.out.println(info);

		// 2. more efficient
		StringBuilder sb = new StringBuilder("");

		sb.append("My name is mozzi");
		sb.append(" ");
		sb.append("I am a skater.");

		System.out.println(sb.toString());

		// 3. the same as above but nicer
		StringBuilder s = new StringBuilder();

		s.append("My name is nugi").append(" ").append("I am a dancer");
		
		System.out.println(s.toString());
	}
}
```

# String formatting
```java

public class App {

	public static void main(String[] args) {
	
		// outputing newlines and tabs
		// print - 줄바꿈 없음
		// println - 줄바꿈 있음
		System.out.print("Here is some text. \tThat was a tab. \nThat was a newline.");
		System.out.println(" More text.");
		
		// formatting integers
		System.out.printf("Total cost %5d; quantity is %d\n", 5, 120); // Total cost     5; quantity is 120
		
		// integer and string formatting control sequence
		for(int i=0; i<5; i++) {
			System.out.printf("%-2d: %s\n", i, "here is some text");
		}
		
		// formatting float point value
		
		// two decimal place:
		System.out.printf("Total value: %.2f\n", 5.8674); // 5.87
		
		// one decimal place, left-aligned in 6 character field:
		System.out.printf("Total value: %-6.1f\n", 343.23423); // 343.2 
		
		String formatted = String.format("This is a floating point value: %.3f", 5.12345);
		System.out.println(formatted); // This is a floating point value: 5.123
		
		System.out.printf("Giving it %d%% is physically impossible.", 100); // Giving it 100% is physically impossible.
	}
}

```