# Math
- 수학 계산을 위한 클래스 (코싸인, 싸인, 탄젠트, 절대값, 랜덤값 등을 구할 수 있음)
- Math 클래스는 생성자가 private 으로 되어 있기 때문에 new 연산자를 이용해 객체를 생성할 수는 없음
- 객체를 생성할 수는 없지만 모든 메소드와 속성이 static 으로 정의되어 있기 때문에 객체를 생성하지 않고도 사용할 수 있음

```java
public class MathExam {

	public static void main(String[] args) {
		
		int value1 = Math.max(5,  30);
		System.out.println(value1);
		
		int value2 = Math.min(5,  30);
		System.out.println(value2);
		
		int value3 = Math.abs(-10);
		System.out.println(value3);
		
		System.out.println(Math.random());
		
		System.out.println(Math.sqrt(25));

        System.out.println(Math.pow(2, 3));

        System.out.println(Math.log10(200));
	}
}
```