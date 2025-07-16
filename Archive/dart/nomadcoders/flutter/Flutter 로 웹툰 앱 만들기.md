
# Hello Flutter

## Installation

- mac : brew로 설치하거나 공홈에 있는 설치 압축파일 다운로드 후 path잡고 설치
- window : choco를 이용해 설치하거나 공홈의 압축파일을 이용하여 설치
- 시뮬레이터
	- 공홈에 설치방법이 있음.

## Dart Pad

- 설치가 필요없이 flutter 사용할 때 : dartpad.dev

## Running Flutter
- flutter create "프로젝트 명"
- vscode dart, flutter 플러그인 설치

## Hello World
* flutter 앱은 Widget로 구성되어 있음
- StatelessWidget, StatefulWidget을 상속받아서 시작해야 함.
- StatelessWidget vs StatefulWidget 비교

| StatelessWidget | StatefulWidget       |
| --------------- | -------------------- |
| 상태가 변하지 않음      | 상태가 변할 수 있음          |
| build() 메서드만 있음 | createState() 메서드 필요 |
| 한 번 생성되면 변경 안됨  | setState()로 재빌드 가능   |
| 성능이 더 좋음        | 상태 변화 시 성능 오버헤드      |
| 메모리 사용량 적음      | 상태 객체로 인한 메모리 사용     |
- StatelessWidget
	- 한번 만들면 변경 불가능한 위젯
	- build 메서드를 통해 화면을 그림
	- 정적인 UI 컴포넌트
	- 단순한 텍스트나 이미지 표시
	- 레이아웃 위젯들
	- 상태 변화가 없는 경우
- StatefulWidget
	- 사용자 입력에 반응해야 할 때
	- 애니메이션이 필요할 때
	- 데이터가 시간에 따라 변할 때
	- 폼 입력을 관리할 때
	- 카운터, 토글, 슬라이더 등

* Scaffold
	* Flutter에서 앱의 기본 레이아웃 구조를 제공하는 위젯.
	* Material Design의 기본 페이지 구조를 구현.
	* Scaffold 없이 사용하면:
		- 상태바와 겹칠 수 있음
		- 시스템 UI와 충돌 가능
		- 키보드 표시 시 레이아웃 문제
		- Material Design 가이드라인 위반
	* Scaffold의 장점
		1. 자동 레이아웃 관리
			- 상태바, 네비게이션바와의 자동 조정
			- 키보드 표시 시 자동 화면 조정
		2. 일관된 디자인
			- Material Design 표준 준수
			- 플랫폼별 자동 최적화
		3. 접근성 지원
			- 스크린 리더 지원
			- 키보드 네비게이션 지원
		4. 반응형 레이아웃
			- 다양한 화면 크기 자동 대응
			- 방향 변경 시 자동 조정

| 속성                       | 설명             | 예시                                     |
| ------------------------ | -------------- | -------------------------------------- |
| appBar                   | 상단 앱바          | AppBar(title: Text("제목"))              |
| body                     | 메인 콘텐츠 영역      | Center(child: Text("내용"))              |
| floatingActionButton     | 플로팅 액션 버튼      | FloatingActionButton(onPressed: () {}) |
| bottomNavigationBar      | 하단 네비게이션       | BottomNavigationBar(items: [])         |
| drawer                   | 왼쪽 사이드 메뉴      | Drawer(child: ListView())              |
| endDrawer                | 오른쪽 사이드 메뉴     | Drawer(child: ListView())              |
| backgroundColor          | 배경색            | Colors.white                           |
| resizeToAvoidBottomInset | 키보드 표시 시 화면 조정 | true                                   |

# UI Challenge

## Financial Mobile IOS App UI 디자인

### Text 박스에 예약 특수문자 사용
* $ 기호 사용이 필요할 때 "\"를 추가하여 사용
### Container
* Flutter에서 가장 자주 사용되는 위젯 중 하나로, HTML의 div 태그와 유사한 역할을 하는 컨테이너
*  Container의 주요 속성들

| 속성         | 설명       | 예시                                |
| ---------- | -------- | --------------------------------- |
| width      | 너비 설정    | width: 100                        |
| height     | 높이 설정    | height: 100                       |
| color      | 배경색 설정   | color: Colors.blue                |
| decoration | 고급 스타일링  | decoration: BoxDecoration(...)    |
| padding    | 내부 여백    | padding: EdgeInsets.all(16)       |
| margin     | 외부 여백    | margin: EdgeInsets.all(16)        |
| alignment  | 자식 위젯 정렬 | alignment: Alignment.center       |
| transform  | 변형 효과    | transform: Matrix4.rotationZ(0.1) |
| child      | 자식 위젯    | child: Text("내용")                 |

### EdgeInsets.symmetric
- 대칭적인 패딩이나 마진을 설정할 때 사용하는 편리한 메서드
- EdgeInsets.all - 모든 방향 동일
- EdgeInsets.only - 개별적으로 설정
```
	EdgeInsets.only(
		top: 10,
		right: 20,
		bottom: 30,
		left: 40,
	)
	// 결과: top: 10, right: 20, bottom: 30, left: 40
```
- EdgeInsets.fromLTRB - 순서대로 설정

### Row MainAxisAlignment.spaceBetween
- Row나 Column에서 자식 위젯들 사이에 균등한 공간을 만들어주는 정렬 방식
- UI 요소들을 양 끝에 배치하고 나머지 공간을 균등하게 분배하는 매우 유용한 정렬 방식
- 버튼 그룹이나 네비게이션 요소들을 배치할 때 자주 사용
	- spaceBetween - 양끝 배치, 사이 공간 균등
		- ``` 결과: [A] [B] [C] ```
	- spaceAround - 모든 위젯 주변에 균등한 공간
		- ``` 결과: [A] [B] [C] ```
	- spaceEvenly - 모든 공간이 완전히 균등
		- ``` 결과: [A] [B] [C] ```
	- center - 중앙 정렬
		- ``` 결과: [A][B][C] ```
	- start - 시작점 정렬
		- ``` 결과: [A][B][C] ```
	- end - 끝점 정렬
		- ``` 결과: [A][B][C] ```

## Stateful Widgets

### BuildContext
- Flutter에서 위젯 트리 내에서 특정 위젯의 위치와 정보를 나타내는 핵심 개념
- 위젯 트리에서 현재 위젯의 위치
- 상위 위젯들에 대한 참조
- 테마, 미디어 쿼리 등의 정보에 접근하는 통로

# Pomodoro App

## Flexible
- Flutter에서 Row, Column, Flex 내부의 자식 위젯이 사용 가능한 공간을 유연하게 차지할 수 있도록 해주는 위젯
- 반응형 레이아웃을 만들 때 매우 유용한 위젯
- 화면 크기에 따라 유연하게 조정되는 UI를 만들거나, 텍스트 오버플로우를 방지하거나, 복잡한 레이아웃을 구성할 때 핵심적인 역할을 한다
-  Flexible vs Expanded 비교

| Flexible                 | Expanded           |
| ------------------------ | ------------------ |
| 필요한 만큼만 공간 차지            | 사용 가능한 모든 공간 차지    |
| 자식 위젯 크기에 맞춤             | 강제로 공간 확장          |
| fit: FlexFit.loose (기본값) | fit: FlexFit.tight |

## Expanded
- Flutter에서 Row, Column, Flex 내부의 자식 위젯이 사용 가능한 모든 공간을 차지하도록 강제하는 위젯
- 사용 가능한 공간을 모두 차지해야 하는 위젯에 사용하는 강력한 레이아웃 도구입니다.
- 반응형 UI를 만들거나 공간을 효율적으로 분배할 때 필수


# Webtoon App

## async / await

- 네트워크 요청, 파일 읽기/쓰기처럼 시간이 걸리는 작업을 기다리는 동안 앱 전체가 멈춰버리지 않게 도와줌.
- `async`와 `await`는 이런 작업을 처리하는 동안에도 앱이 멈추지 않고 부드럽게 동작하도록 도와주는 **비동기(Asynchronous) 프로그래밍** 도구
### `async`
- 함수 선언부의 `()`와 `{}` 사이에 `async` 키워드를 붙이면, "이 함수는 비동기적으로 동작하며, 내부에 시간이 걸리는 작업이 있을 수 있습니다"라고 알려주는 표시입니다.
- `async` 함수는 항상 `Future`라는 특별한 객체를 반환합니다. `Future`는 '미래에 완료될 어떤 작업'을 의미해요. 지금 당장은 결과가 없지만, 나중에 결과(데이터 또는 에러)를 가지게 될 것이라는 '약속'과 같습니다.
### `await`
- `await`는 `async` 함수 안에서만 사용할 수 있습니다.
- `Future` 작업이 완료될 때까지 **해당 함수의 실행을 잠시 멈추고 기다리게** 만듭니다.
- 가장 중요한 점은, `await`가 기다리는 동안 프로그램 전체를 멈추는 것이 아니라, 현재 함수의 실행만 잠시 멈추고 Dart는 다른 작업(예: UI 업데이트, 사용자 입력 처리)을 계속할 수 있다는 것입니다.
- `Future` 작업이 완료되면, `await`는 `Future` 안에 담겨있는 실제 결과값을 꺼내주고, 멈췄던 부분부터 함수 실행을 다시 이어갑니다.

## Future
- 비동기 통신 시 결과값을 받는 객체.

## ListView
- 스크롤이 가능한 목록을 화면에 표시할 때 사용하는 가장 기본적인 위젯.
- 아이템 개수가 적고 고정되어 있을 때 사용합니다. 모든 아이템을 한 번에 만듬
## ListView.builder()
- 아이템 개수가 많거나 동적일 때 사용
- 화면에 보이는 아이템만 만들기 때문에 **성능이** 좋음
- 메모리 효율성을 위해 **화면에 실제로 보이거나 곧 보일 아이템들만 생성(build)하고 렌더링**
	- **최초 로딩 시**: Flutter는 `ListView`의 높이를 계산하고, 그 공간을 채울 수 있을 만큼의 아이템만 `itemBuilder`를 통해 생성합니다. 예를 들어, 리스트 높이가 600px이고 각 아이템 높이가 100px이라면, 약 6개의 아이템을 생성하여 화면에 보여줍니다.
	- **스크롤 시**:
	    - 사용자가 스크롤하여 화면 위로 사라지는 아이템은 메모리에서 제거(dispose)됩니다.
	    - 화면 아래에서 새로 나타날 아이템은 그 즉시 생성(build)됩니다.

## **`ListView.separated()`**
- `istView.builder`와 동일한 성능상 이점을 가지면서, 아이템 사이에 구분선을 쉽게 추가할 수 있습니다.

## GestureDetector
- Flutter에서 사용자의 터치, 탭, 드래그 등 다양한 제스처를 감지하고 처리하는 위젯
- 사용자 인터랙션을 처리하는 핵심 위젯

## Navigator.push(context, route)
- Flutter의 네비게이션 시스템
- 새로운 화면(페이지)을 스택에 추가
- context: 현재 위젯 트리의 위치 정보
- route: 이동할 페이지 정보

## MaterialPageRoute
- Material Design 스타일의 페이지 전환 효과
- 오른쪽에서 왼쪽으로 슬라이드되는 애니메이션
- builder: 새 페이지를 생성하는 함수

## Hero
- 두 화면 간의 위젯을 부드럽게 연결하는 애니메이션 효과를 제공하는 위젯
- 같은 tag를 가진 Hero 위젯들이 화면 전환 시 연결됨
- 첫 번째 화면의 위젯이 두 번째 화면의 위젯으로 부드럽게 변형
- 크기, 위치, 모양이 자연스럽게 애니메이션됨

## widget property
- Flutter의 StatefulWidget에서 상위 위젯으로부터 전달받은 title 속성에 접근하는 코드
	-  widget 키워드의 역할
		- StatefulWidget의 구조:
		- DetailScreen (StatefulWidget): 데이터를 보관
		- _DetailScreenState (State): UI를 구성
- StatefulWidget의 State 클래스에서 부모 위젯으로부터 전달받은 데이터에 접근하는 표준적인 방법

```
class DetailScreen extends StatefulWidget {
  final String id, title, thumb; // 상위에서 전달받는 속성들
  
  const DetailScreen({
    super.key,
    required this.id,
    required this.title,  // 이 title
    required this.thumb,
  });
  
  @override
  State<DetailScreen> createState() => _DetailScreenState();
}

class _DetailScreenState extends State<DetailScreen> {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text(widget.title), // widget.title로 접근
      ),
    );
  }
}
```