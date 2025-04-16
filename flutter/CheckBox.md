# Flutter 

이 Flutter 애플리케이션은 CheckBox를 이용한 예제 입니다.



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

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(

        colorScheme: ColorScheme.fromSeed(seedColor: Colors.deepPurple),
      ),
      home: TestCheckBox(),
    );
  }
}

```
## 📋 test_CheckBox.dart

```dart
import 'package:flutter/cupertino.dart';
import 'package:flutter/material.dart';

class TestCheckBox extends StatefulWidget {
  const TestCheckBox({super.key});

  @override
  State<TestCheckBox> createState() => _CheckBoxState();
}

class _CheckBoxState extends State<TestCheckBox> {
  bool? isChecked1 = false;
  bool isChecked2 = false;

  void _incrementCounter() {
    setState(() {

    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        backgroundColor: Theme.of(context).colorScheme.inversePrimary,
        title: Text('Checkbox / Switch 테스트'),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Checkbox(
              value: isChecked1,
              onChanged: (value) {
                setState(() {
                  isChecked1 = value;
                });
              }
            ),

            SizedBox(height: 80),

            Switch(
                value: isChecked2,
                onChanged: (value) {
                  setState(() {
                    isChecked1 = value;
                  });
                }
            )
           ],
        ),
      ),
    );
  }
}

```
## 🖥️ 실행 결과
| 예제 실행 화면 |
|:---------------:|
| ![Hello World 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/CheckBox.png) |


