# Generic 적용 전
Box.java
```java
public class Box {

    private Object obj;

    public void setObj(Object obj) {
        this.obj = obj;
    }

    public Object getObj() {
        return obj;
    }
}
```

BoxExam.java
```java
public class BoxExam {

	public static void main(String[] args) {
		
		Box box = new Box();
		
		box.setObj(new Object());
		Object obj = box.getObj();
		
		box.setObj("hello");
		String str = (String)box.getObj();
		System.out.println(str);
		
		box.setObj(3);
		int value = (int)box.getObj();
		System.out.println(value);
	}
}
```

# Generic 적용 후
- java 5에는 Generic 이라는 문법이 사용됨으로써, 인스턴스를 만들 때 사용하는 타입을 지정하는 문법이 추가됨
- Generic 을 사용함으로써 선언할 때는 가상의 타입으로 선언하고,  
  사용 시에는 구체적인 타입을 설정함으로써 다양한 타입의 클래스를 이용하는 클래스를 만들 수 있음
- Generic 을 사용하는 대표적인 클래스는 컬렉션 프레임워크와 관련된 클래스들

Box.java
> `Object` 키워드 대신 `E` 키워드로 대체  
> `E` 는 가상의 클래스를 의미
```java
public class Box<E> {

	private E obj;

	public void setObj(E obj) {
		this.obj = obj;
	}
	
	public E getObj() {
		return obj;
	}
}
```

BoxExam.java
```java
public class BoxExam {

	public static void main(String[] args) {
		
		Box<Object> box = new Box<>();
		box.setObj(new Object());
		Object obj = box.getObj();
		
		Box<String> box2 = new Box<>();
		box2.setObj("hello");
		String str = box2.getObj();
		System.out.println(str);
		
		Box<Integer> box3 = new Box<>();
		box3.setObj(3);
		int value = box3.getObj();
		System.out.println(value);
	}
}
```