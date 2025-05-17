## main 함수
```
	// 실행 함수 main. main 함수가 없으면 실행 안됨.
	// 세미콜론은 무조건 찍어야 한다.
	void main() {
		print("hello World");
	}
```

## 변수 선언
```
	void main() {
		// dart는 타입추론이 가능하기 때문에 명시적으로 타입을 선언하지 않아도 됨.
		// 타입을 명시해서 변수 선언해도 상관없음.
		// dart에서는 지역변수 선언 시 var로 변수를 선언하도록 권장함.
		var name = 'coma';
		name = 'comacoma';
		
		// 변수 선언 시 값을 초기화하지 않으면 'dynamic' 타입으로 지정된다.
		// dynamic은 dart에서 변수에 할당되는 값을 확인하여 타입을 지정해 준다.
		// 명시적으로 어떤 값이 오는지 알수 없을 때 dynamic으로 선언하여 변수를 생성한다.
		var dyName;
		dynamic dyName2;
		
	}
```

## null safety
```
String? name  // Nullable type. Can be `null` or string.

String name   // Non-nullable type. Cannot be `null` but can be string.

name?.isEmpty; //name 가 null일때는 isEmpty를 실행하지 않음.
```

## Final Variables
* 상수로 변수를 선언하는 방법
```
final name = 'aaa';
final String name2 = 'bbb';
```

## Late Variables
* late 는 final 앞이나 var 앞에 선언
* late는 초기 데이터 없이 변수를 선언 할 수 있게 함.
* 지연 초기화의 개념으로 선언 시 데이터를 지정하지 않고 나중에 데이터를 지정하여 초기화 한다.

## Constant Variables
* const는 compile-time constant를 만듬.
* 컴파일 시 상수를 선언.
```
void main() {  
const name = "tom"; // 컴파일 시점에 바뀌지 않는 값  
final username=fetchAPI(); // 컴파일 시점에 바뀌는 값  
}
```