# 리스트와 배열
- 공통점 : 둘 다 자료구조
- 차이점 :
  - 리스트 : 저장 공간이 필요에 따라 자유롭게 변함
  - 배열 : 한 번 생성하면 크기 변경 불가

# 리스트
- 리스트는 데이터의 중복이 있을 수 있고, 순서도 있음
- 리스트는 길이가 정해져 있지 않기 때문에, "길이를 알 수 없는 배열" 을 더할 때 유용하게 사용할 수 있음

```java
import java.util.ArrayList;
import java.util.List;

public class ListExam {

	public static void main(String[] args) {
		
		List<String> list = new ArrayList<>();
		list.add("kim");
		list.add("kang");
		list.add("kim");
		
		System.out.println(list.size()); // 3
		
		for(int i = 0; i < list.size(); i++) {
			String str = list.get(i);
			System.out.println(str);
		}
	}
}
```