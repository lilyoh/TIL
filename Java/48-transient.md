serializing 할 때 사용하는 transient
특정 field 를 serialize 하고 싶지 않을 때 사용

Person.java
```java
import java.io.Serializable;

public class Person implements Serializable {

	private static final long serialVersionUID = 4801633306273802062L;
	 
	// 바로 여기 transient
	// ReadObjects 파일 실행하면 아래와 같은 결과 나옴
	// Person [id=0, name=Bob]
	private transient int id;
	private String name;
	
	private static int count;
	
	public Person() {
		System.out.println("default constructor");
	}
	
	public Person(int id, String name) {
		this.id = id;
		this.name = name;
		
		System.out.println("two-argument constructor");
	}
	
	public static int getCount() {
		return count;  
	}
	
	public static void setCount(int count) {
		Person.count = count;
	}
	
	@Override
	public String toString() {
		return "Person [id=" + id + ", name=" + name + "] Count is: " + count;
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

        try (ObjectOutputStream os = new ObjectOutputStream(new FileOutputStream("test.ser"))) {

            Person person = new Person(7, "Bob");
            Person.setCount(88);
            os.writeObject(person);

        } catch (FileNotFoundException e) {
            // TODO Auto-generated catch block
            e.printStackTrace();
        } catch (IOException e) {
            // TODO Auto-generated catch block
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
import java.util.ArrayList;

public class ReadObjects {

    public static void main(String[] args) {
        System.out.println("Reading objects...");
        
        try (ObjectInputStream os = new ObjectInputStream(new FileInputStream("test.ser"))) {

            Person person = (Person)os.readObject();
            System.out.println(person);
            
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