# Dart 구구단 코드

이 구구단은 DartPad를 이용하여 출력한 코드입니다.

## 📋 코드 예제
```dart
import 'package:flutter/material.dart';

void main() {
  print("📌 구구단 출력 (가로 정렬)\n");

  for (int i = 1; i <= 9; i++) {
    String row = ""; // 한 줄에 여러 구구단을 출력할 문자열 생성
    for (int j = 2; j <= 9; j++) {
      row += "$j x $i = ${j * i}".padRight(12); // 공백 추가
    }
    print(row); // 한 줄 출력
  }
}

```

## 🖥️ 실행 결과
| 예제 실행 화면 |
|:---------------:|
| ![Hello World 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/gugu.png) |


