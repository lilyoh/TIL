# while loops vs. for loops
- while : looser syntax, expects some sort of modification to the variable in the body
- for : rigid syntax, everything is in the definition

# when to use while/for loops?
- while : when you know the number of iterations ahead of time
- for : when you don't know

```java
public class Application {
    public static void main(String[] args) {
        
        for(int i=0; i < 5; i++) {
            System.out.printf("The value of i is: %dn", i);
        }
    }
}
```