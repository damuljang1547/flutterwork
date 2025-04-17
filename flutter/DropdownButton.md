# Flutter 

이 Flutter 애플리케이션은 DropDownButton을 이용한 예제 입니다.



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
      home: TestDropDownButton(),
    );
  }
}

```
## 📋 test_Radio.dart

```dart
import 'package:flutter/material.dart';

class TestDropDownButton extends StatefulWidget {
  const TestDropDownButton({super.key});

  @override
  State<TestDropDownButton> createState() => _DropDownButton();
}

class _DropDownButton extends State<TestDropDownButton> {
  final _valueList = ['첫 번째', '두 번째', '세 번째'];
  String? _selectedValue = '첫 번째';

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        backgroundColor: Theme.of(context).colorScheme.inversePrimary,
        title: Text('DropDownButton 테스트'),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            DropdownButton(
              value: _selectedValue,
              items:
              _valueList
                  .map(
                    (value) =>
                    DropdownMenuItem(value: value, child: Text(value)),
              )
                  .toList(),
              onChanged: (value) {
                setState(() {
                  _selectedValue = value;

                  print(_selectedValue);
                });
              },
            ),
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
| ![Hello World 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/DropDownButton.png) |


