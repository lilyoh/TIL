# void와 return값
void = 해당 메서드가 return  값이 없다는 의미로 메서드 앞에 적어주는 키워드  
return 값을 적어주려 하는 메서드 앞에는 해당 리턴값의 타입을 적어주면 됨

# 캡슐화 encapsulation
해당 클래스의 데이터를 다른 클래스로부터 숨기는 것
getter를 통해 캡슐화 구현

```java
class Person {
	String name;
	int age;

	void speak() {
		System.out.println("My name is: " + name);
	}

	// return 값의 타입이 int이므로
	// 아무 생각없이 void를 적어줬던 자리에 int를 적어주면 됨
	int calculateYearsToRetirement() {
		int yearsLeft = 60 - age;
		return yearsLeft;
	}
	
	String getName() {
		return name;
	}

	int getAge() {
		return age;
	}
}

public class Application {
	public static void main(String[] args) {
		Person person1 = new Person();
		// 이 부분이 클래스의 데이터를 직접 조작하는 부분
		person1.name = "tori";
		person1.age = 7;
		// person1.speak();
		
		int age = person1.getAge();
		String name = person1.getName();
		System.out.println("age is: " + age);
		System.out.println("name is: " + name);

		// calculateYearsToRetirement 메서드의 return 값이 생겼으니
		// 해당 리턴값을 가지고 변수에 저장해서 원하는대로 조작해서 사용 가능
		int years = person1.calculateYearsToRetirement();
		System.out.println("Years till retirement: " + years);
		int yearsRich = years - 50;
		System.out.println("Years tiil retirement if you are rich: " + yearsRich);
	}
}
```