# Flutter 

이 Flutter 애플리케이션은 화면에 현재시간을 나타내는 텍스트를 표시하는 예제입니다.

pubspec.yaml에 intl: ^0.18.1를 추가해 intl 사용

날짜와 시간을 포맷하기 위해 intl패키지를 import, 
한국어 locale을 포맷하기 위해 import구문을 추가함.

DateTime.now()를 사용

final date = DateFormat('yyyy-MM-dd').format(now);
final time = DateFormat('a h:mm:ss', 'ko').format(now);
구문을 통해 날짜, 시간 형식 지정.

오전, 오후를 나타내기 위해 로케일 초기화가 필요해
await initializeDateFormatting('ko') 사용

await을 사용하기 위해 main에 async 추가

WidgetsFlutterBinding.ensureInitialized();를 추가해 위젯 엔진과 관련된 초기화 작업을 마쳤는지 확인
await initializeDateFormatting('ko') -> 비동기 코드가 있기 때문에 추가함







## 📋 코드 예제
```dart
import 'package:flutter/material.dart';
import 'package:intl/intl.dart'; // 날짜 포맷을 위해 필요함
import 'package:intl/date_symbol_data_local.dart';


void main() async{
  WidgetsFlutterBinding.ensureInitialized();
  await initializeDateFormatting('ko');
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: '현재 시각',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: const MyHomePage(),
    );
  }
}

class MyHomePage extends StatelessWidget {
  const MyHomePage({super.key});

  @override
  Widget build(BuildContext context) {
    final now = DateTime.now();
    final date = DateFormat('yyyy-MM-dd').format(now);
    final time = DateFormat('a h:mm:ss', 'ko').format(now);

    return Scaffold(
      appBar: AppBar(
        title: const Text('현재 시각'),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Text(
              date,
              style: const TextStyle(fontSize: 36),
            ),
            Text(
              time,
              style: const TextStyle(fontSize: 36),
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
| ![Hello World 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/Now_Time.png) |


