- use when a and b is not related, don't have same parent class etc
- can implement many interfaces
- do not write code in block
- kind of text contract
---
전체 코드

App.java
```java
public class App {
    
    public static void main(String[] args) {
        
        Machine mach1 = new Machine();
        mach1.start();
        
        Person person1 = new Person("Bob");
        person1.greet();
        
        Info info1 = new Machine();
        info1.showInfo();
        
        Info info2 = person1;
        info2.showInfo();
        
        System.out.println();
        
        outputInfo(mach1);
        outputInfo(person1);
    }
    
    private static void outputInfo(Info info) {
        info.showInfo();
    }

}
```

Machine.java
```java
public class Machine implements Info {
    
    private int id = 7;
    
    public void start() {
        System.out.println("Machine started.");
    }

    public void showInfo() {
        System.out.println("Machine ID is: " + id);
    }
}
```

Person.java
```java
public class Person implements Info {
    
    private String name;
    
    public Person(String name) {
        this.name = name;
    }

    public void greet() {
        System.out.println("Hello there.");
    }

    @Override
    public void showInfo() {
        System.out.println("Person name is: " + name);
    }
}
```

Info.java
```java
public interface Info {
    public void showInfo();
}
```