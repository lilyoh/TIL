```java
import java.util.Scanner;

public class Application {
	public static void main(String[] args) {

		String[] words = new String[3];
		
		words[0] = "Hello";
		words[1] = "to";
		words[2] = "you";
		
		System.out.println(words[2]); // you
		
		// declare and initialize
		String[] fruits = {"apple", "banana", "pear", "kiwi"};
		
		// for-each loop!
		for (String fruit: fruits) {
			System.out.println(fruit); // apple, banana, pear, kiwi
		}
		
		// type 별 default value
		int value = 0;
		String text = null;
		
		String[] texts = new String[2];
		System.out.println(texts[0]); // null
		
		texts[0] = "one";
		System.out.println(texts[0]); // one
	}
}
```