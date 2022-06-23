# package
- tool for organising code
- tool to use other people's code

# package name convention
- lower case
- simple
- don't use under score
- worldwide convention
  - reverse your website and add particular name
  - i.e) com.caveofprogramming.oceangame

# file structure
- default package = src folder (root folder)
- can nest packages

---
전체 코드

App.java
```java
// should import when using class in other package
import ocean.Fish;
import ocean.plants.Seaweed;

// or you can import everything in one package
// import ocean.*;

public class App {
	public static void main(String[] args) {
		
		Fish fish = new Fish();
		Seaweed weed = new Seaweed();
	}
}
```

Fish.java
```java
package ocean;

public class Fish {

}
```

Seaweed.java
```java
package ocean.plants;

public class Seaweed {

}
```
---
주제 외에 알게 된 것
- src folder = java files
- bin folder = class files