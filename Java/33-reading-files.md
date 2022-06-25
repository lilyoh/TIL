```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class App {
	public static void main(String[] args) throws FileNotFoundException {

		String filename = "/Users/ohseungha/Desktop/dev/text.txt";
		
		File textFile = new File(filename);
		
		Scanner in = new Scanner(textFile);
		
		while(in.hasNextLine()) {
			String line = in.nextLine();
			System.out.println(line);
		}
		
		in.close();
	}
}
```