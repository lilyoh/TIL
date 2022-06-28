# throwing exceptions

App.java
```java
import java.io.IOException;

public class App {

	public static void main(String[] args) {
		
		Test test = new Test();
		
		// 1. 아래처럼만 적어주면 Test.java 파일에 적어준 throw를 처리해주지 않은 것이기 때문에 에러남
		// test.run();
		
		// 2. try/catch 써서 에러처리 해줘야 함
		try {
			test.run();
		} catch(IOException e) {
			System.out.println(e.getMessage());
            // Could not connect to server.
        }
	}
}
```
Test.java
```java
import java.io.IOException;

public class Test {

	public void run() throws IOException {
		
		int code = 1;
		
		if(code != 0) {
			throw new IOException("Could not connect to server.");
		}
		
		System.out.println("running successfully");
	}
}
```
# create own exception
ServerException.java  
-- usually create a folder i.e. named "exceptions"
```java

public class ServerException extends Exception {
	
	public ServerException(String message) {
		super(message);
	}
}
```

App.java
```java
public class App {

	public static void main(String[] args) {
		
		Test test = new Test();
		
		try {
			test.run();
		} catch(ServerException e) {
			System.out.println(e.getMessage());
		}
	}
}
```

Test.java
```java
public class Test {

	public void run() throws ServerException {
		
		int code = 1;
		
		if(code != 0) {
			throw new ServerException("Could not connect to server. - server exception");
		}
		
		System.out.println("running successfully");
	}
}
```