# java.time 패키지
- java 에서 제공하는 Date, Time API 는 부족한 기능 지원을 포함한 여러 문제가 있었음
- JDK 코어에서 이런 문제점들을 해결하고 더 직관적인 API 들을 제공하기 위해
- 재디자인한 Date, Time API 를 Java SE 8부터 제공

---

- 새로운 api 의 핵심 클래스는 오브젝트를 생성하기 위해 다양한 factory 메서드를 사용함
- 오브젝트 자기 자신의 특정 요소를 가지고 오브젝트를 생성할 경우 `of` 메서드를 호출하면 되고, 다른 타입으로 변경할 경우에는 `from` 메서드를 호출하면 됨

```java
import java.time.LocalDate;
import java.time.LocalDateTime;
import java.time.LocalTime;
import java.time.Month;

public class TimeExam {
    public static void main(String[] args) {

        LocalDateTime timePoint = LocalDateTime.now();
        System.out.println(timePoint);

        LocalDate ld = LocalDate.of(2022, Month.JULY, 5);
        System.out.println(ld);

        LocalTime lt1 = LocalTime.of(00, 12);
        System.out.println(lt1);
        LocalTime lt2 = LocalTime.parse("00:13:09");
        System.out.println(lt2);

        LocalDate theDate = timePoint.toLocalDate();
        System.out.println(theDate);
        LocalTime theTime = timePoint.toLocalTime();
        System.out.println(theTime);

        Month month = timePoint.getMonth();
        System.out.println(month);
        System.out.println(month.getValue());
        System.out.println(timePoint.getMonth());
        System.out.println(timePoint.getHour());
    }
}
```

