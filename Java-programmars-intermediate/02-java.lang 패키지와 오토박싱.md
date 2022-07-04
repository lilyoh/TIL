# java.lang 패키지
자바는 기본적으로 다양한 패키지를 지원함, 그 중에서도 가장 중요한 패키지가 java.lang 패키지
- java.lang 패키지의 클래스는 import 하지 않고도 사용 가능
- 기본형 타입을 객체로 변환시킬 때 사용하는 Wrapper 클래스가 있음
  - Boolean, Byte, Short, Integer, Long, Float, Double 클래스
- java.lang 패키지의 클래스들
  - 모든 클래스의 최상위 클래스인 Object
  - 문자열과 관련된 String, StringBuffer, StringBuilder
  - 화면에 값을 출력할 때 사용했던 System 클래스
  - 수학과 관련된 Math 클래스
  - Thread 와 관련된 중요 클래스들

```java
public class WrapperExam {

	public static void main(String[] args) {
		
		int i = 5;
		
		Integer i2 = new Integer(5); // integer 기본형 타입을 객체로 변환시킨 Wrapper 클래스 중 하나인 Integer
		Integer i3 = 5; // java 5 부터 이렇게 작성 가능 -- 오토박싱
		
		int i4 = i3.intValue();
		int i5 = i3; // java 5 부터 이렇게 작성 가능 -- 오토 언박싱
	}
}
```
# 오토박싱
- 오토박싱
  - 자동으로 객체형으로 형변환
- 오토 언박싱
  - 자동으로 기본형으로 형변환
- 오토박싱과 오토 언박싱은 java 5부터 지원, 내부적으로 Wrapper 클래스들이 사용되는 것