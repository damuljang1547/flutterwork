# Flutter 

이 Flutter 애플리케이션은 화면에 레이아웃을 나누고 각자 다른 색을 채우는 코드입니다.

우선 Container로 외곽틀을 생성
가로 세로 300의 정사각형을 생성

생성된 정사각형 안에서 Colum을 사용하고 expanded로 flex 값을 1씩 할당 해 같은 비율로 칸을 나눔
후에 색 삽입
나눠진 사각형의 윗부분 안에 row를 사용해 2개로 나눔
색 삽입

반복


## 📋 코드 예제
```dart
import 'package:flutter/material.dart';

void main() => runApp(const MyApp());

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: const HomePage(),
      debugShowCheckedModeBanner: false,
    );
  }
}

class HomePage extends StatelessWidget {
  const HomePage({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.white,
      body: Center(
        child: Container(
          width: 300,
          height: 300,
          decoration: BoxDecoration(
            border: Border.all(color: Colors.black),
          ),
          child: Column(
            children: [
              Expanded(
                flex: 1,
                child: Row(
                  children: [
                    Expanded(
                      flex: 1,
                      child: Container(color: Colors.red), // 왼쪽 빨강
                    ),
                    Expanded(
                      flex: 1,
                      child: Column(
                        children: [
                          Expanded(
                            flex: 1,
                            child: Container(color: Colors.blue), // 위쪽 파랑
                          ),
                          Expanded(
                            flex: 1,
                            child: Row(
                              children: [
                                Expanded(
                                  flex: 1,
                                  child: Container(color: Colors.black), // 왼쪽 검정
                                ),
                                Expanded(
                                  flex: 1,
                                  child: Container(color: Colors.orange), // 오른쪽 주황
                                ),
                              ],
                            ),
                          ),
                        ],
                      ),
                    ),
                  ],
                ),
              ),
              Expanded(
                flex: 1,
                child: Container(color: Colors.yellow), // 아래 노란색
              ),
            ],
          ),
        ),
      ),
    );
  }
}


```

## 🖥️ 실행 결과
| 예제 실행 화면 |
|:---------------:|
| ![Hello World 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/layout.png) |


