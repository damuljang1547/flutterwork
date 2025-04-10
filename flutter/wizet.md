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
        title: Text('위젯배치1')
      ),
      // body : Text('여기에 예제 작성'),
      // body : Container(
      //   width: 100,
      //   height: 100,
      //   margin: EdgeInsets.all(80.0),
      //   padding: EdgeInsets.all(16.0),
      //   color: Colors.blue,
      //   child: Text('강승구'),
      // )

      body: Row(
        children : [
          Container(
             width: 100,
             height: 100,
             margin: EdgeInsets.all(10.0),
             padding: EdgeInsets.all(16.0),
             color: Colors.blue,
             child: Text('사자'),
          ),
          Container(
            width: 100,
            height: 100,
            margin: EdgeInsets.all(10.0),
            padding: EdgeInsets.all(16.0),
            color: Colors.red,
            child: Text('호랑이'),
          ),
          Container(
            width: 100,
            height: 100,
            margin: EdgeInsets.all(10.0),
            padding: EdgeInsets.all(16.0),
            color: Colors.green,
            child: Text('거북이'),
          ),
        ]
      ),
      );
  }
}


```

## 🖥️ 실행 결과
| 예제 실행 화면 |
|:---------------:|
| ![Hello World 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/wizet1.png) |


