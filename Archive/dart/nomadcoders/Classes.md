
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