Person.java
```java
import java.io.Serializable;

public class Person implements Serializable {

	private static final long serialVersionUID = 4801633306273802062L;
	
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
		
        Person[] people = {new Person(1, "Sue"), new Person(99, "Mike"), new Person(7, "Bob")};
		
		try(FileOutputStream fs = new FileOutputStream("test.ser")) {
			
			ObjectOutputStream os = new ObjectOutputStream(fs);
			
			os.writeObject(people);
			
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
        try (FileInputStream fi = new FileInputStream("test.ser")) {

            ObjectInputStream os = new ObjectInputStream(fi);

            Person[] people = (Person[]) os.readObject();

            for (Person person : people) {
                System.out.println(person);
            }

            os.close();

        } catch (FileNotFoundException e) {
            // TODO Auto-generated catch b lock
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