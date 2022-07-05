파일에서 한 줄씩 입력받아서 파일에 출력
- 파일에서 읽기 위해서 FileReader 클래스 이용
- 한 줄 읽어들이기 위해서 BufferedReader 클래스 이용
  - BufferedReader 클래스가 가지고 있는 ReadLine() 메소드가 한 줄씩 읽게 해줌
  - readLine() 메소드는 더이상 읽어들일 내용이 없을 때 null 을 리턴
- 파일에 쓰기 위해서 FileWriter 클래스 이용
- 편리하게 출력하기 위해서 PrintWriter 클래스 이용

```java
import java.io.BufferedReader;
import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;
import java.io.PrintWriter;

public class CharIOExam2 {
	public static void main(String[] args) {

		BufferedReader br = null;
		PrintWriter pw = null;
		
		try {
			br = new BufferedReader(new FileReader("src/CharIOExam2.java"));
			pw = new PrintWriter(new FileWriter("test.txt"));
			
			String line = null;
			
			while((line = br.readLine()) != null) {
				pw.println(line);
			}
			
		} catch (Exception e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		} finally {
			try {
				br.close();
			} catch (IOException e) {
				// TODO Auto-generated catch block
				e.printStackTrace();
			}
			pw.close();
		}
	}
}
```