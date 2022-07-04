```java
import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;
import java.util.Set;

public class MapExam {

	public static void main(String[] args) {

		// key, value 가 모두 String 타입인 HashMap 인스턴스 생성
		Map<String, String> map = new HashMap<>();

		// key 와 value 값을 put 으로 저장
		map.put("001", "kim");
		map.put("002", "kang");
		map.put("003", "lee");

		map.put("001", "choi");

		System.out.println(map.size());

		System.out.println(map.get("001"));
		System.out.println(map.get("002"));
		System.out.println(map.get("003"));

		// map 에 저장된 모든 key 들을 set 자료구조로 꺼냄
		Set<String> keys = map.keySet();
		// set 자료구조에 있는 모든 key 를 꺼내기 위해 Iterator를 구함
		Iterator<String> iter = keys.iterator();
		while (iter.hasNext()) {
			// key 꺼내기
			String key = iter.next();
			// key 에 해당하는 value 꺼내기
			String value = map.get(key);
			// key 와 value 출력
			System.out.println(key + ": " + value);
		}
	}
}
```