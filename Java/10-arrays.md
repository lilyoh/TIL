```java
import java.util.Scanner;

public class Application {
	public static void main(String[] args) {

		int value = 7;

		// 타입 뒤에 []를 붙여주고, 변수명을 적으면 배열 생성
		int[] values;
		values = new int[3];

		System.out.println("values[0]: " + values[0]); 
		// values[0]: 0 -> type의 default 값으로 초기화 됨
		// int type의 default 값은 0

		values[0] = 10;
		values[1] = 20;
		values[2] = 30;

		System.out.println(values[0]); // 10
		System.out.println(values[1]); // 20
		System.out.println(values[2]); // 30

		// 배열의 각 요소를 출력하기 위해 for문 사용
		for (int i = 0; i < values.length; i++) {
			System.out.println(values[i]);
			/*
			 * 10 20 30
			 */
		}

		// 이렇게 바로 배열의 값을 적어줘도 됨
		int[] numbers = { 5, 6, 7 };

		for (int i = 0; i < numbers.length; i++) {
			System.out.println(numbers[i]); // 5, 6, 7
		}
	}
}
```