- file reading과 크게 다를 것 없음
- `BufferedWriter` , `FileWriter`를 사용함
- `.write()`로 원하는 내용을 적어주고 `.newLine()`으로 개행할 수 있음

App.java
```java
import java.io.BufferedWriter;
import java.io.File;
import java.io.FileWriter;
import java.io.IOException;

public class App {
	public static void main(String[] args) {

		File file = new File("test.txt");
		try (BufferedWriter br = new BufferedWriter(new FileWriter(file))) {
			br.write("This is line one");
			br.newLine();
			br.write("This is line two");
			br.newLine();
			br.write("This is last line");
		
		} catch (IOException e) {
			System.out.println("Unable to read file " + file.toString());
		}
	}
}
```