Byte 단위 입출력 클래스는 클래스의 이름이 `InputStream` 이나 `OutputStream`으로 끝남

- 파일로부터 1바이트씩 읽어들여 파일에 1바이트씩 저장하는 프로그램을 작성
  - 파일로부터 읽어오기 위한 객체 - FileInputStream
  - 파일에 쓸 수 있게 해주는 객체 - FileOutputStream

- read() 메소드가
  - 바이트를 리턴한다면 끝을 나타내는 값을 표현할 수 없기 때문에 바이트가 아닌 int 를 리턴함
  - 음수의 경우 맨 좌측 비트가 1이 됨, 읽어들일 것이 있다면 항상 양수를 리턴함

- FileInputStream과 FileOutputStream을 이용해 1바이트씩 읽어들여 1바이트씩 저장
  - read()메소드가 리턴하는 타입은 정수인데, 정수 4바이트 중 마지막 바이트에 읽어들인 1바이트를 저장
  - read 메소드는 더이상 읽어들일 것이 없을 때 -1을 리턴

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;

public class ByteIOExam1 {
  public static void main(String[] args) {

    FileInputStream fis = null;
    FileOutputStream fos = null;

    try {
      fis = new FileInputStream("src/ByteIOExam1.java");
      fos = new FileOutputStream("byte.txt");

      int readData = -1;
      while ((readData = fis.read()) != -1) {
        fos.write(readData);
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
  }
}
```