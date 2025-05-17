

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

```
	import 'package:flutter/material.dart';
	
	void main() {
		runApp(App());  //위젯 App 클레스를 생성해야 함.
	}
	
	// widget class 생성 시 StatelessWidget을 상속받아야 함.
	// StatelessWidget 클레스는 build 메소드를 작성해야 함.
	class App extends StatelessWidget {
		@override
		  Widget build(BuildContext context) {
		    // CupertinoApp : IOS 스타일, MaterialApp : 구글 스타일
		    return MaterialApp(
		      home: Scaffold(
		        appBar: AppBar(
		          title: Text('Hello flutter!'),
		        ),
		        body: Center(
		          child: Text('Hello world!'),
		        ),
		      ),
		    );
		  }
	}
```