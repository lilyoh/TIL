- 파일로부터 512 바이트씩 읽어들여 파일에 512 바이트씩 저장하는 프로그램을 작성
  - byte[] buffer = new byte[512];
  - 512 바이트만큼 읽어들이기 위해 바이트 배열을 사용

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;

public class ByteIOExam2 {
	public static void main(String[] args) {

		long startTime = System.currentTimeMillis();
		
		FileInputStream fis = null;
		FileOutputStream fos = null;

		try {
			fis = new FileInputStream("src/ByteIOExam1.java");
			fos = new FileOutputStream("byte.txt");

			int readCount = -1;
			byte[] buffer = new byte[512];
			
			while ((readCount = fis.read(buffer)) != -1) {
				fos.write(buffer, 0, readCount);
			}

		} catch (Exception e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		} finally {
			try {
				fos.close();
				fis.close();
			} catch (IOException e) {
				// TODO Auto-generated catch block
				e.printStackTrace();
			}
		}
		
		long endTime = System.currentTimeMillis();
		System.out.println(endTime - startTime);

	}
}
```

- 앞서 작성해보았던 "1바이트씩 읽고 쓰기" 와 수행 시간을 비교해보면, 512 바이트씩 읽고 썼을 때 수행 시간이 훨씬 짧아짐
  - 그 이유는, 원래 프로그램이 512 바이트씩 읽어들이기 때문
  - 1바이트씩 읽고 쓰게 했을 때 실제 수행 과정 : 512 바이트를 읽고, 1바이트를 쓴 뒤, 나머지 511 바이트를 버림 => 이 과정 반복
  - 따라서 512 바이트씩 읽고 쓰는 것이 훨씬 효율적