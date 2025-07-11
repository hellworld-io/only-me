
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