Serialization means turns objects into binary form, usually with the aim of saving them to a file.  
Serialization gives us an easy way to implement save and load functionality in our app.  

Q. How do you make a class serializable in java?  
A. By implementing serializable interface.

Person.java
```java
import java.io.Serializable;

public class Person implements Serializable {

	private int id;
	private String name;
	
	public Person(int id, String name) {
		this.id = id;
		this.name = name;
	}
	
	@Override
	public String toString() {
		return "Person [id=" + id + ", name=" + name + "]";
	}
}
```

WriteObjects.java
```java
import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.ObjectOutputStream;

public class WriteObjects {

	public static void main(String[] args) {
		System.out.println("Writing objects...");
		
		Person mike = new Person(543, "Mike");
		Person sue = new Person(123, "Sue");
		
		System.out.println(mike);
		System.out.println(sue);
		
        // try-with resources
		try(FileOutputStream fs = new FileOutputStream("people.bin")) {
			
			ObjectOutputStream os = new ObjectOutputStream(fs);
			
			os.writeObject(mike);
			os.writeObject(sue);
			
			os.close();
			
		} catch (FileNotFoundException e) {
			e.printStackTrace();
		} catch (IOException e) {
			e.printStackTrace();
		}
	}
}
```

ReadObjects.java
```java
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.io.ObjectInputStream;

public class ReadObjects {

	public static void main(String[] args) {
		System.out.println("Reading objects...");
		
        // try-with resources
		try(FileInputStream fi = new FileInputStream("people.bin")) {
			
			ObjectInputStream os = new ObjectInputStream(fi);
			
			Person person1 = (Person)os.readObject();
			Person person2 = (Person)os.readObject();
			
			os.close();

			System.out.println(person1);
			System.out.println(person2);
			
		} catch (FileNotFoundException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		} catch (IOException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		} catch (ClassNotFoundException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
	}
}
```