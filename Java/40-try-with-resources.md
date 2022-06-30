- try-with resources 는 java7 부터 사용 가능함
  - autoclose 기능이 있음 -- 따로 close를 안해줘도 됨
  - 이전에 아주 길게 작성해야 했던 코드를 간결하게 작성가능케 함

App.java
```java
import java.io.BufferedReader;
import java.io.File;
import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;

public class App2 {
	public static void main(String[] args) {

		File file = new File("test.txt");
		try (BufferedReader br = new BufferedReader(new FileReader(file))) {
			String line;
			while ((line = br.readLine()) != null) {
				System.out.println(line);
			}
		} catch (FileNotFoundException e) {
			System.out.println("Can't find file " + file.toString());
		} catch (IOException e) {
			System.out.println("Unable to read file " + file.toString());
		}
	}
}
```