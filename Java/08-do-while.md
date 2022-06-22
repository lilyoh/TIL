while loop vs. do-while loop?
- while : 조건 체크해서 블록 안의 코드가 1번도 실행되지 않을 수 있음
- do-while : while 조건문이 나중에 적히기 때문에 do 블록 안의 코드가 무조건 1번은 실행이 됨  

```java
import java.util.Scanner;

public class Application {
	public static void main(String[] args) {

		Scanner scanner = new Scanner(System.in);

		/*
		 * System.out.println("Enter a number: ");
		 * 
		 * int value = scanner.nextInt();
		 * 
		 * while (value != 5) { System.out.println("Enter a number: "); value =
		 * scanner.nextInt(); }
		 */

		int value = 0; // scope!

		do {
			System.out.println("Enter a number: ");
			value = scanner.nextInt();
		} while (value != 5);

		System.out.println("Got 5!");
	}
}
```