# Flutter 

이 Flutter 애플리케이션은 TextField를 이용한 예제 입니다.



## 📋 main.dart
```dart
import 'package:a_6_1/test_DropDownButton.dart';
import 'package:a_6_1/test_Gesture.dart';
import 'package:a_6_1/test_TextField.dart';
import 'package:a_6_1/test_dialog.dart';
import 'package:flutter/material.dart';
import 'package:a_6_1/test_CheckBox.dart';
import 'package:a_6_1/test_Radio.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(

        colorScheme: ColorScheme.fromSeed(seedColor: Colors.deepPurple),
      ),
      home: TestTextField(),
    );
  }
}

// class MyHomePage extends StatefulWidget {
//   const MyHomePage({super.key, required this.title});
//   final String title;
//
//   @override
//   State<MyHomePage> createState() => _MyHomePageState();
// }
//
// class _MyHomePageState extends State<MyHomePage> {
//   int _counter = 0;
//
//   void _incrementCounter() {
//     setState(() {
//       _counter++;
//     });
//   }
//
//   @override
//   Widget build(BuildContext context) {
//     return Scaffold(
//       appBar: AppBar(
//         backgroundColor: Theme.of(context).colorScheme.inversePrimary,
//         title: Text(widget.title),
//       ),
//       body: Center(
//         child: Column(
//           mainAxisAlignment: MainAxisAlignment.center,
//           children: <Widget>[
//             const Text('You have pushed the button this many times:'),
//             Text(
//               '$_counter',
//               style: Theme.of(context).textTheme.headlineMedium,
//             ),
//           ],
//         ),
//       ),
//       floatingActionButton: FloatingActionButton(
//         onPressed: _incrementCounter,
//         tooltip: 'Increment',
//         child: const Icon(Icons.add),
//       ), // This trailing comma makes auto-formatting nicer for build methods.
//     );
//   }
// }



```
## 📋 test_TextField.dart

```dart
import 'package:flutter/cupertino.dart';
import 'package:flutter/material.dart';

class TestTextField extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('TextField 테스트'),),
      body:Padding(padding: EdgeInsets.all(16.0),
      child: Column(
        children: [
          TextField(),
          TextField(
            decoration: InputDecoration(
              labelText: '여기에 입력하세요',
            )
          ),

          SizedBox(height: 32),
          TextField(
            decoration: InputDecoration(
              border: OutlineInputBorder(),
              labelText: '여기도 입력하세요')
          )
        ],

      ) ,
      )
    );
  }

}
```
## 🖥️ 실행 결과
| 예제 실행 화면 |
|:---------------:|
| ![Hello World 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/TextField.png) |


