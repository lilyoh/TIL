# Date
날짜와 시간을 구하기 위한 클래스
- date 클래스는 jdk 1.0 때 만들어졌고, calendar 클래스는 jdk 1.1 에 만들어짐
- date 는 지역화에 대한 부분이 고려되지 않았음
  - 지역화란, 지역에 따라서 시간, 통화, 언어 등에 대해 고려하는 프로그래밍
- 기본 생성자를 이용한 date 클래스 생성
  - 기본 생성자로 date 인스턴스를 만들게 되면 현재 시간과 날짜 정보를 date 인스턴스가 가지게 됨
```java
Date date = new Date();
```

- toString() 메소드를 이용해 현재 시간을 문자열로 구함
```java
System.out.println(date.toString()); // Mon Jul 04 18:32:01 KST 2022
```

- java.util.SimpleDateFormat 클래스를 이용해서 원하는 형태로 출력하는 방법
  - a 는 오전/오후를 표현
  - zzz 는 TimeZone 을 나타냄, 한국의 경우 한국표준시 KST 가 TimeZone 에 해당하는 값

- 현재 시간을 Long 값으로 구할 수도 있음 (아래 코드 참고)

```java
import java.text.SimpleDateFormat;
import java.util.Date;

public class DateExam {

	public static void main(String[] args) {
		
		Date date = new Date();
		System.out.println(date.toString());
		
		SimpleDateFormat ft = new SimpleDateFormat("yyyy.MM.dd 'at' hh:mm:ss a zzz");
		
		System.out.println(ft.format(date));
		
		System.out.println(date.getTime());
		
		long today = System.currentTimeMillis();
		System.out.println(today);
		
		System.out.println(today - date.getTime());
	}
}
```