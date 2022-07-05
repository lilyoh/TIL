# Calendar
- date 객체의 지역화 부분을 보완하여 나옴
---
- calendar 클래스의 생성
  - calendar 클래스는 추상 클래스
  - 인스턴스를 생성하려면 calendar 클래스가 가지고 있는 메소드인 getInstance() 메소드를 사용해야 함
  - getInstance() 메소드를 호출하면 내부적으로 java.util.GregorianCalendar 인스턴스를 만들어 리턴함
  - GregorianCalendar 는 Calendar 의 자식 클래스
```java
        Calendar cal = Calendar.getInstance();
```

- Calendar 클래스를 이용해 현재 날짜와 시간에 대한 정보 알아내는 법
  - Calendar 는 현재 날짜와 시간에 대한 정보를 가짐
  - get 메소드에 Calendar 상수 중 어떤 것을 넣어주느냐에 따라 다른 값이 나옴
```java
        System.out.println(cal.get(Calendar.YEAR));
        System.out.println(cal.get(Calendar.MONTH) + 1);
        System.out.println(cal.get(Calendar.DATE));
        System.out.println(cal.get(Calendar.HOUR_OF_DAY)); // 24시간을 기준으로 시간 보여줌
        System.out.println(cal.get(Calendar.MINUTE));
```

- 원하는 날짜나 시간에 대한 정보 얻기
  - Calendar 가 가지고 있는 add 메소드를 이용
```java
            System.out.println(cal.get(Calendar.YEAR)); // 2022
            cal.add(Calendar.YEAR, 3);
            System.out.println(cal.get(Calendar.YEAR)); // 2025
```



전체 코드
```java
import java.util.Calendar;

public class CalendarExam {
	public static void main(String[] args) {

		Calendar cal = Calendar.getInstance();

		System.out.println(cal.get(Calendar.YEAR));
		System.out.println(cal.get(Calendar.MONTH) + 1);
		System.out.println(cal.get(Calendar.DATE));
		System.out.println(cal.get(Calendar.HOUR_OF_DAY));
		System.out.println(cal.get(Calendar.MINUTE));

		cal.add(Calendar.YEAR, 3);
		
		System.out.println(cal.get(Calendar.YEAR));
	}
}
```