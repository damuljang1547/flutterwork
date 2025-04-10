# Flutter 

이 Flutter 애플리케이션은 화면에 위젯을 배치하는 코드입니다.



## 📋 코드 예제
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});


  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        colorScheme: ColorScheme.fromSeed(seedColor: Colors.deepPurple),
      ),
      home: const MyHomePage(),
    );
  }
}

class MyHomePage extends StatelessWidget {
  const MyHomePage ({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
          title: Text('위젯배치2')
      ),

      body: Stack(
        children: [
          Center(
              child : Container(
                color: Colors.red,
                width: 100,
                height: 100,
                padding: const EdgeInsets.all(8.0),
                margin: const EdgeInsets.all(8.0),
              )
          ),
          Center(
              child : Container(
                color: Colors.green,
                width: 80,
                height: 80,
                padding: const EdgeInsets.all(8.0),
                margin: const EdgeInsets.all(8.0),
              )
          ),
          Center(
              child : Container(
                color: Colors.blue,
                width: 60,
                height: 60,
                padding: const EdgeInsets.all(8.0),
                margin: const EdgeInsets.all(8.0),
                child: Center(child : Text('얼룩말')),
              )
          )
        ],
      ),
    );
  }
}

```

## 🖥️ 실행 결과
| 예제 실행 화면 |
|:---------------:|
| ![Hello World 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/wizet.png) |


