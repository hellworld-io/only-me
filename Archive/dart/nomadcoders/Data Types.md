## Basic Data Types  
  
- dart에서 모든 데이터 타입은 object(function 포함)  
  
## Lists  
```  
    List numbers = [1, 2, 3];    
    var number2 = [4, 5, 6];  
      
```  
- collection if  
    - List를 만들 때, if를 통해 존재할 수도 안 할 수도 있는 요소를 가지고 만들 수 있다.  
```  
void main() {    
    var giveMeFive = true;    
    var item = [    
        1,    
        2,    
        3,    
        if (giveMeFive) 10, // giveMeFive가 true이면 10을 넣음    
    ];    
    print(item);    
}  
```
## String Interpolation  
- String 변수에 템플릿 변수 사용.  
    - $달러 기호를 붙이고 사용할 변수를 작성.  

```
void main(){    
    var name = "tom";    
    var age = 10;    
    var greeting = "hello $name, I'm ${age + 5}";    
}  
```

## Collection For

- list 객체에 for문을 이용하여 list를 추가할 수 있음.
```
	void main() {  
		var oldFriends = ["nico", "lynn"];  
		var newFriends = [  
			"tom",  
			"jon",  
			for (var friend in oldFriends) "❤️ $friend",
		];
	}
```

## Maps
- Java Map과 같음.
```
	var gifts = {
	  // Key:    Value
	  'first': 'partridge',
	  'second': 'turtledoves',
	  'fifth': 'golden rings'
	};

	Map<String, Object> gifts2 = {
		'name': 'aaa',
		'xp': 123.12
		'isAdmin': true,
	};
	
	List<Map<String, Object>> friends = [
		{
			'name': 'aaa',
			'xp': 123.12
			'isAdmin': true,
		},
		{
			'name': 'bbb',
			'xp': 100.12
			'isAdmin': false,
		}
	];
```

## Sets
- 중괄호({})를 사용하여 변수 생성 시 Set으로 설정됨.
- Set의 값은 유니크한 값만 사용가능.
```
	var numbers = {1,2,3,4};    //Set일때는 중복값 허용 않함.
	// var numbers = [1,2,3,4]; // List일때는 중복값 허용함.
	numbers.add(1);
	numbers.add(1);
	numbers.add(1);
	Set<int> numbers = {1,2,3,4};
```