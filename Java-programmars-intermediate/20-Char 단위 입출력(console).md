Char 단위 입출력 클래스는 클래스 이름이 Reader나 Writer로 끝남
- 아래 코드는 키보드로부터 한 줄 입력받아서 콘솔에 출력하는 예제
    - `System.in` : 키보드를 의미
    - `BufferedReader` : 한 줄씩 입력받기 위한 클래스
    - BufferedReader 클래스의 생성자는 InputStream을 입력받는 생성자가 없음
    - System.in은 InputStream 타입이므로 BufferedReader의 생성자에 바로 들어갈 수 없어서 InputStreamReader 클래스를 이용해야 함

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;

public class CharIOExam1 {
	public static void main(String[] args) {

		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

		String line = null;

		try {
			line = br.readLine();
		} catch (IOException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		
		System.out.println(line);
	}
}
```
---
데코레이터 패턴
- 객체에 추가적인 요건(기능)을 동적으로 첨가하는 방식
- 서브클래스를 만드는 것을 통해 기능을 유연하게 확장할 수 있는 방법을 제공
