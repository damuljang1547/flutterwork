# Dart 요일 출력 코드

이 코드는 DartPad를 이용하여 입력한 날짜를 요일로 출력하는 코드입니다.

## 📋 코드 예제
```dart
import 'package:flutter/material.dart';

void main() {
  var input = '2025-03-22'; // 입력 값

  // 입력 값을 DateTime 형식으로 변환
  DateTime date = DateTime.parse(input);

  // 요일 목록 (0: 일요일, 1: 월요일, ... 6: 토요일)
  List<String> weekdays = ['일', '월', '화', '수', '목', '금', '토'];

  // 결과 출력
  print('${weekdays[date.weekday % 7]}요일');
}


```

## 🖥️ 실행 결과
| 예제 실행 화면 |
|:---------------:|
| ![실행결과 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/date.png) |


