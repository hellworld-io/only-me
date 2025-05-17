
## Your First Dart Class
- dart에서 class는 property(변수)와 메소드로 구성된다.
- property 선언시 타입을 명시해야 한다.
- class에서 property사용시 this는 생략해도 된다.
- class 인스턴스 생성 시 new 생성자는 생략해도 된다.

```
	class Player {
		String name = 'aaa';
		//final String name = 'aaa';   //상수로 선언하여 변경 불가능하게 설정
		int xp = 1500;
		
		void sayHello() {
			print("Hi my name is $name");
		}
	}
	void main() {
		var palyer = Player();
		print(palyer.name);
		palyer.name = 'bbb';   //property 변경. 상수로 선언 시 변경 불가능
		print(palyer.name);
		
		palyer.sayHello();    //class 메소드 사용
	}
```

## Constructors

- dart에서 class 생성자는 class명과 같아야 함.

```
	class Player {
		//late룰 사용하는 이유는 생성자를 호출하기 전까지 초기화되지 않기 때문에
		late String name;
		late int xp;
		
		//생성자 작성
		Player(String name, int xp) {
			this.name = name;
			this.xp = xp;
		}
		
		//생성자를 간결하게 생성. 이때는 property에 late삭제
		Player(this.name, this.xp);
		
		void sayHello() {
			print("Hi my name is $name");
		}
	}
	void main() {
		var palyer = Player('aaa', 100);
		player.sayHello();
		var palyer2 = Player('bbb', 200);
		player2.sayHello();
	}

```

## Named Constructor Parameters

- class 파라메터가 많아질 경우 작성에 어려움이 있음.
- 생성자를 호출할때 각 파라메터가 어떤 정보인지 알기 어렵고 순서에 맞게 생성해야 함.

```
	class Player {
		String name;
		int xp;
		String team;
		int age;
		
		//property가 늘어나면 생성자도 같이 변경되어야 함.
		Player(this.name, this.xp, this.team, this.age);
		
		void sayHello() {
			print("Hi my name is $name");
		}
	}
	void main() {
		//늘어난 property에 맞게 값의 위치와 갯수를 맞춰서 생성해야함.
		var palyer = Player('aaa', 100, 'red', 20);
	}
```
- 생성자에 중괄호({})를 추가해서 named parameter로 설정
- null값에 취약함.
```
	class Player {
		String name;
		int xp;
		String team;
		int age;
		
		//중괄호({})를 사용하여 named parameter 설정
		Player({this.name, this.xp, this.team, this.age});
		
		void sayHello() {
			print("Hi my name is $name");
		}
	}
	void main() {
		//가독성이 좋아지고 파라메터값 오류가 발생하지 않음
		var palyer = Player(
			name: 'aaa',
			xp: 100,
			team: 'red',
			age: 20,
		);
	}
```

- null값 방지를 위해 required를 사용.

```
	class Player {
		String name;
		int xp;
		String team;
		int age;
		
		//required를 선언하여 null 입력 방지
		Player({required this.name, required this.xp, required this.team, required this.age});
		
		void sayHello() {
			print("Hi my name is $name");
		}
	}
	void main() {
		//가독성이 좋아지고 파라메터값 오류가 발생하지 않음
		var palyer = Player(
			name: 'aaa',
			xp: 100,
			team: 'red',
			age: 20,
		);
	}
```

## Named Constructors

- 메소드 처럼 생성자명을 지정하여 생성자를 생성.
- 모든 파라메터를 전달할 필요없을때 나머지 property를 초기화 할때 사용.
- 콜론(:)을 사용하여 property 초기화 설정함.

```
	class Player {
		final String name;
		int xp;
		String team;
		int age;
		
		Player({required this.name, required this.xp, required this.team, required this.age});
		
		//콜론(:)을 사용하여 named constructor을 생성한다.
		Player.createBluePlayer({required String name, required int age}) :
			this.name = name,
			this.age = age,
			this.team = 'blue',
			this.xp = 0;
		
		Player.createRedPlayer(String name, int age}) :
			this.name = name,
			this.age = age,
			this.team = 'red',
			this.xp = 0;
		
		void sayHello() {
			print("Hi my name is $name");
		}
	}
	void main() {
		var bluePalyer = Player.createBluePlayer(
			name: 'aaa',
			age: 10,
		);
		
		var redPalyer = Player.createRedPlayer('cc', 20);
	}
```


## Recap

```
	class Player {
		final String name;
		int xp;
		String team;
		
		Player.fromJson(Map<String, dynamic> playJson) :
			name = playJson['name'],
			team = playJson['team'],
			xp = playJson['xp'],
		
		void sayHello() {
			print("Hi my name is $name");
		}
	}
	void main() {
		//API를 통해서 json 값을 받았을때 json값으로 class 생성.
		var apiData = [
			{
				"name":"aaa",
				"team":"blue",
				"xp":0
			},
			{
				"name":"bbb",
				"team":"red",
				"xp":0
			},
			{
				"name":"ccc",
				"team":"green",
				"xp":0
			},
		];
		
		apiData.forEach((playerJson) {
			var player = Player.fromJson(playerJson);
			player.sayHello();
		})
	}
```

## Cascade Notation

- class 인스턴스 행성 후 인스턴스 변수명을 반복적으로 사용하는 불편함을 해소해줌.
- 인스턴스 변수명 대신 .. 으로 대체

```
	class Player {
		String name;
		int xp;
		String team;
		
		Player({required this.name, required this.xp, required this.team, required this.age});
		
		void sayHello() {
			print("Hi my name is $name");
		}
	}
	void main() {
		var coma = Player(name : 'aaa', xp : 12000, team : 'red');
		//값을 변경할때 반복적으로 인스턴스 변수를 사용하여야 함.
		coma.name = 'bbb';
		coma.xp = 100;
		coma.team = 'blue';
		
		//..을 사용하여 사용할 수 있음. class 생성자 선언에서 세미콜론 제거 후 사용해야 함.
		var coma = Player(name : 'aaa', xp : 12000, team : 'red')
		..name = 'bbb'
		..xp = 100
		..team = 'blue'
		..sayHello();
	}
```

## Enums

```
	enum Team {red, blue }
	
	class Player {
		String name;
		int xp;
		
		//String team;
		Team team;    //enum 타입으로 변경
		
		Player({required this.name, required this.xp, required this.team, required this.age});
		
		void sayHello() {
			print("Hi my name is $name");
		}
	}
	void main() {
		// var coma = Player(name : 'aaa', xp : 12000, team : 'red');
		// enum으로 값 설정 변경
		var coma = Player(name : 'aaa', xp : 12000, team : Team.red);
		coma.name = 'bbb';
		coma.xp = 100;
		coma.team = Team.blud;
	}
```

## Abstract Classes

- 추상 클레스는 객체로 생성이 불가능.
- 직접 구현해야하는 메소드를 모아놓은 클레스

```
	//추상 클레스 생성. 추상 클레스는 구현구가 없는 메소드만 있음.
	abstract class Human {  
		void walk();  
	}
	
	enum Team {red, blue }
	
	//Human 추상 클레스를 확장하여 walk 메소드를 상황에 맞게 구현
	class Player extends Human{
		String name;
		int xp;
		
		//String team;
		Team team;    //enum 타입으로 변경
		
		Player({required this.name, required this.xp, required this.team, required this.age});
		
		void walk() {
			print(I am walking.);
		}
		
		void sayHello() {
			print("Hi my name is $name");
		}
	}
	void main() {
		// var coma = Player(name : 'aaa', xp : 12000, team : 'red');
		// enum으로 값 설정 변경
		var coma = Player(name : 'aaa', xp : 12000, team : Team.red);
		coma.name = 'bbb';
		coma.xp = 100;
		coma.team = Team.blud;
	}
```

## Inheritance
- 상속은 부모 클레스를 자식 클레스에서 상속받아 사용하는 것.
- 자식 클레스에서 super를 사용하여 부모클레스를 사용.

```
	class Human {  
		final String name;
		
		Human({this.name});
		
		void sayHello() {
			print("Hello my name $name");
		}
	}
	
	enum Team {red, blue }
	
	class Player extends Human{
		final Team team;
		
		//자식 클레스에서 부모 클레스 호출을 위해 supper을 사용
		Player({require this.team, require String name}) : super(name : name);
		
		//부모 클레스의 메소드 재사용
		@override
		void sayHello() {
			super.sayHello();
			print("my team ${team}");
		}
		
	}
	void main() {
		var player = Player(
			team: Team.red,
			name: 'aaa'
		);
	}
```

## Mixins

- 생성자가 없는 클레스.
- 사용시 with를 작성하여 사용.
- 여러 클레스의 프로퍼티와 메소드를 다 가져와서 사용.

```
	class Strong {
		final double strongLevel = 100.10;
	}
	
	class QuickRunner {
		void run() {
			print("ruuuun!!");
		}
	}
	
	class Player with Strong, QuickRunner {
	
	}
	
	void main() {
		var player.strongLevel;
		var player.run();
	}
```
