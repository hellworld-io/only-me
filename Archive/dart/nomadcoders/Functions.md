
## Defining a Function
```
	// 반환값이 없을때 void 사용
	void sayHello(String name) {
		print('Hello my name is $name');
	}

	//반환값이 있을때 반환값의 타입을 지정하여 사용
	String sayHello(String name) {
		return 'Hello my name is $name';
	}

	//함수에 반환값만 존재할때 "=>" 를 사용하여 표현
	String sayHello(String name) => 'Hello my name is $name';
	
	void main() {
		
	}
```

## Named Parameters
```
	//함수 파라메터를 여러개 명시적으로 설정
	String sayHello(String name, int age, String country) {
		return "Hello my name is $name, my age is $age, I am from $country";
	}

	//중괄호({})를 파라메터에 설정해서 파라메터를 명으로 설정
	String sayHello({String name, int age, String country}) {
		return "Hello my name is $name, my age is $age, I am from $country";
	}

	//sayHello 호출 시 파라메터를 지정하지 않거나 null값을 보낼때 오류 방지를 위해 기본값 설정.
	String sayHello({String name = 'bb', int age = 20, String country = 'cc'}) {
		return "Hello my name is $name, my age is $age, I am from $country";
	}

	//sayHello 호출 시 파라메터를 지정하지 않거나 null값을 보낼때 오류 방지를 위해 required를 설정하여 필수값 지정
	String sayHello({required String name, required int age, required String country}) {
		return "Hello my name is $name, my age is $age, I am from $country";
	}
	
	void main() {
		sayHello('aaa', 12, 'Korea');   //함수 파라메터를 여러개 명시적으로 설정. 가독성이 떨어짐.
		//파라메터 지정 순서는 상관없고 함수에 정의된 파라메터명만 정확히 설정하면 됨.
		sayHello(
			name: 'aaa',
			age: 12,
			country: 'Korea',
		);

		//sayHello 호출 시 파라메터를 지정하지 않거나 null값을 보낼때 오류 방지를 위해 기본값 설정.
		sayHello();

		//sayHello 호출 시 파라메터를 지정하지 않거나 null값을 보낼때 오류 방지를 위해 required를 설정하여 필수값 지정
		sayHello(); //required 파라메터를 설정하지 않아서 컴파일 오류.
	}
```

## Recap

- 위 내용 리마인드 강의

## Optional Positional Parameters

- 함수 파라메터를 필수로 사용하고 싶지 않을때 설정함.

```
//optional parameter 설정할때 "[]"를 사용하고 파라메터의 default 값을 설정하고 null safe "?"을 설정한다.
String sayHello(String name, int age, [String? country = 'korea']) => 'Hello $name, You are $age years old from $country';

void main() {
	var result = sayHello('ccc', 12);
	print(result);
}
```

## QQ Operator

- ?? 연산자 : ?? 왼쪽값이 null인 경우 오른쪽을 실행함.

```
	String capitalizeName(String name) {
		return name.toUpperCase();
	}

	//null 사용할 수 있게 함수 변경. 코드가 길어짐
	String capitalizeName(String name) {
		if (name != null) {
			return name.toUpperCase();
		}
		return 'ANON';
	}

    String capitalizeName(String name) => name != null ? name.toUpperCase() : 'ANON';

	//name이 null일때 ANON, null이 아닐때 toUpperCase 실행.
	String capitalizeName(String name) => name.toUpperCase() ?? 'ANON';
	

	void main() {
		capitalizeName('aaa')   //AAA
		capitalizeName(null)    //null을 사용할 수 있게 하기 위해

		String? name;   //null safe 변수 선언
		name ??= 'bbb'; //name이 null일때 값 셋팅
	}
```