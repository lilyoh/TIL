# what kind of exceptions are in java?
- checked exception : you're forced to handle
- runtime exception(=unchecked exception) : don't have to handle  
> runtime exception 은 코드 자체에 문제가 있을 때 발생하므로 꼭 고쳐야 함

App.java
1. null pointer exception
2. arithmetic exception
3. handling runtime exceptions
```java

public class App {
	public static void main(String[] args) {

		// Null pointer exception
		String text = null;
		System.out.println(text.length());

		// Arithmetic exception
		int value = 7 / 0;

		// You can actually handle RuntimeExceptions if you want to
		// for example, here we handle an ArrayIndexOutOfBoundsException
		String[] texts = { "one", "two", "three" };

		try {
			System.out.println(texts[3]);
		} catch (ArrayIndexOutOfBoundsException e) {
			System.out.println(e.toString());
		}
	}
}
```