# Flutter 

이 Flutter 애플리케이션은 Radio를 이용한 예제 입니다.



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
      home: TestRadio(),
    );
  }
}

```
## 📋 test_Radio.dart

```dart
import 'package:flutter/cupertino.dart';
import 'package:flutter/material.dart';

enum Gender {
  Man,
  Woman,
}

class TestRadio extends StatefulWidget {
  const TestRadio({super.key});

  @override
  State<TestRadio> createState() => _RadioState();
}

class _RadioState extends State<TestRadio> {
  Gender _gender = Gender.Man;

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        backgroundColor: Theme.of(context).colorScheme.inversePrimary,
        title: Text('Radio 테스트'),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            ListTile(
              title: Text('남자'),
              leading: Radio(
                value: Gender.Man,
                groupValue: _gender,
                onChanged: (value) {
                  setState(() {
                    _gender = value!;
                  });
                },
              ),
            ),
            ListTile(
              title: Text('여자'),
              leading: Radio(
                value: Gender.Woman,
                groupValue: _gender,
                onChanged: (value) {
                  setState(() {
                    _gender = value!;
                  });
                },
              ),
            ),
            SizedBox(height: 80),
            RadioListTile(
              title: Text('남자'),
              value: Gender.Man,
              groupValue: _gender,
              onChanged: (value) {
                setState(() {
                  _gender = value!;
                });
              },
            ),
            RadioListTile(
              title: Text('여자'),
              value: Gender.Woman,
              groupValue: _gender,
              onChanged: (value) {
                setState(() {
                  _gender = value!;
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
| ![Hello World 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/Radio.png) |


