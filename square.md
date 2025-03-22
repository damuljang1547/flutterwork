# Dart 사각형 만들기
이 코드는 사각형을 만드는 코드입니다.

## 📋 코드 예제
```dart
import 'package:flutter/material.dart';

void main() {
  int n = 10; // 정사각형의 크기

  print("\n📌 테두리 사각형");
  for (int i = 0; i < n; i++) {
    if (i == 0 || i == n - 1) {
      print('+' * n); // 윗줄, 아랫줄
    } else {
      print('+' + ' ' * (n - 2) + '+'); // 양쪽 테두리만
    }
  }
}

```

## 🖥️ 실행 결과
| 예제 실행 화면 |
|:---------------:|
| ![실행결과 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/square1.png) |



# Dart 사각형 만들기
이 코드는 위 사각형을 가득 채운 코드입니다.

## 📋 코드 예제
```dart
import 'package:flutter/material.dart';

void main() {
  int n = 10; // 정사각형의 크기

  print("\n📌 꽉 찬 사각형");
  for (int i = 0; i < n; i++) {
    print('+' * n); // 모든 줄을 '+'로 채움
  }
}


```

## 🖥️ 실행 결과
| 예제 실행 화면 |
|:---------------:|
| ![실행결과 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/square2.png) |


# Dart 사각형 만들기
이 코드는 첫 번째 만든 사각형에 왼쪽으로 대각선이 표시된 사각형입니다.

## 📋 코드 예제
```dart
import 'package:flutter/material.dart';

void main() {
  int n = 10; // 정사각형의 크기

  print("\n📌 왼쪽 대각선 사각형");
  for (int i = 0; i < n; i++) {
    if (i == 0 || i == n - 1) {
      print('+' * n); // 윗줄, 아랫줄
    } else {
      // 왼쪽 대각선 위치에 + 추가
      print('+' + ' ' * (i - 1) + '+' + ' ' * (n - i - 2) + '+');
    }
  }
}



```

## 🖥️ 실행 결과
| 예제 실행 화면 |
|:---------------:|
| ![실행결과 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/square3.png) |


# Dart 사각형 만들기
이 코드는 첫 번째 만든 사각형에 오른쪽으로 대각선이 표시된 사각형입니다.

## 📋 코드 예제
```dart
import 'package:flutter/material.dart';

void main() {
  int n = 10; // 정사각형의 크기

  print("\n📌 오른쪽 대각선이 포함된 사각형");
  for (int i = 0; i < n; i++) {
    if (i == 0 || i == n - 1) {
      print('+' * n); // 윗줄, 아랫줄
    } else {
      String row = '+';
      for (int j = 1; j < n - 1; j++) {
        if (i + j == n - 1) {
          row += '+'; // 오른쪽 대각선
        } else {
          row += ' '; // 왼쪽 부분은 공백
        }
      }
      row += '+';
      print(row);
    }
  }
}


```

## 🖥️ 실행 결과
| 예제 실행 화면 |
|:---------------:|
| ![실행결과 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/square4.png) |


# Dart 사각형 만들기
이 코드는 첫 번째 만든 사각형에 양쪽으로 대각선이 표시된 사각형입니다.

## 📋 코드 예제
```dart
import 'package:flutter/material.dart';

void main() {
  int n = 10; // 정사각형의 크기

  print("\n📌 양쪽 테두리와 X 형태의 대각선");
  for (int i = 0; i < n; i++) {
    String row = '';

    // 첫 번째와 마지막 행은 +로 가득 채우기
    if (i == 0 || i == n - 1) {
      row = '+' * n;
    } else {
      // 양쪽 테두리 추가
      row += '+';

      for (int j = 1; j < n - 1; j++) {
        if (i == j || i + j == n - 1) {
          row += '+'; // X 형태의 대각선
        } else {
          row += ' '; // 그 외는 공백
        }
      }

      row += '+'; // 마지막 테두리 추가
    }

    print(row);
  }
}


```

## 🖥️ 실행 결과
| 예제 실행 화면 |
|:---------------:|
| ![실행결과 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/square5.png) |