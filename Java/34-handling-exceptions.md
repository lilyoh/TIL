demo1/App.java
> throws로 에러 처리
```java
package demo1;
import java.io.File;
import java.io.FileNotFoundException;
import java.io.FileReader;

public class App {
	public static void main(String[] args) throws FileNotFoundException {

		File file = new File("test.txt");
		FileReader fr = new FileReader(file);
	}
}
```
demo2/App.java
> try/catch로 에러 처리
```java
package demo2;

import java.io.File;
import java.io.FileNotFoundException;
import java.io.FileReader;

public class App {
	public static void main(String[] args) {

		File file = new File("test.txt");
		try {
			FileReader fr = new FileReader(file);
			
			// This will not be executed if an exception is thrown
		} catch (FileNotFoundException e) {
			// below if default
			// e.printStackTrace();
			
			System.out.println("File not found: " + file.toString());
		}
		
		System.out.println("Finished");
	}

}
```
demo3/App.java
> 특정 메서드에서 throws로 에러 처리하고,  
> main 메서드에서 try/catch로 한번 더 에러 처리
```java
package demo3;

import java.io.File;
import java.io.FileNotFoundException;
import java.io.FileReader;

public class App {
	public static void main(String[] args) {
		try {
			openFile();
		} catch (FileNotFoundException e) {
			System.out.println("Could not open file");
		}
	}

	public static void openFile() throws FileNotFoundException {

		File file = new File("test.txt");
		FileReader fr = new FileReader(file);
	}

}
```