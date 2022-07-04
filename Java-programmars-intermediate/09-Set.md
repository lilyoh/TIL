set 은 인터페이스이므로 new 를 통해서 인스턴스 생성 불가  
set 을 구현한 클래스인 hashSet 을 이용해서 인스턴스 생성함

```java
import java.util.HashSet;
import java.util.Iterator;
import java.util.Set;

public class SetExam {

	public static void main(String[] args) {
		
		// String 을 타입으로 하는 HashSet 인스턴스 생성하여 set1 변수에 할당
		Set<String> set1 = new HashSet<>();
		
		// set 에 값을 추가할 때는 add 라는 메소드를 사용
		// add 메소드는 이미 값이 있으면 false, 없으면 true 를 반환하기 때문에
		// boolean 타입의 변수에 할당
		boolean flag1 = set1.add("kang");
		boolean flag2 = set1.add("kim");
		boolean flag3 = set1.add("kang");  
		
		System.out.println(set1.size()); // 2 -- "kang" 이 중복이므로
		
		System.out.println(flag1); // true
		System.out.println(flag2); // true
		System.out.println(flag3); // false
		
		// set 에 있는 값을 하나씩 꺼내보기 위해서는 set 의 부모 클래스인 컬렉션이 가지고 있는 이터레이터 인터페이스를 이용해야 함
		// 인덱스가 필요 없으므로 while 문 사용
		Iterator<String> iter = set1.iterator();
		while(iter.hasNext()) {
			String str = iter.next(); // next 메소드는 하나를 꺼내고 자동으로 다음 것을 참조함
			System.out.println(str);
		}
	}
}
```
참고 :  
set 의 내용은 for each 문과 iterator 을 이용해서 출력 가능함
```java
for (String str : set) {
    System.out.println(str);
        }
```