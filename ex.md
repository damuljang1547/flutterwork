# 예제1


## 📋 코드 예제
```dart
import 'package:flutter/material.dart';

class Rectangle {
  // 사격형을 왼쪽, 상단, 너비, 높이로 표현
  num left, top, width, height;

  Rectangle(this.left, this.top, this.width, this.height);
  //오른쪽, 하단은 필드를 생성하지 않고 get/set 으로 계산하여 표현
  num get right => left + width;
  set right(num value) => left = value - width;
  num get bottom => top + height;
  set bottom(num value) => top = value - height;
}

void main() {
  var r1 = Rectangle(5, 10, 20, 25);
  print([r1.left, r1.top, r1.width, r1.height]);
  print([r1.width, r1.height]);
}

```

## 🖥️ 실행 결과
| 예제 실행 화면 |
|:---------------:|
| ![실행결과 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/ex1.png) |


# 예제2


## 📋 코드 예제
```dart
import 'package:flutter/material.dart';

class Hero {
  String name = '영웅';
  void run () {
    print('뛴다');
  }
}

class SuperHero extends Hero {
  @override
  void run (){
    super.run();
    this.fly();
    
  }
  
  void fly () {
    print('난다!');
  }
}

void main() {
  var hero = SuperHero();
  hero.run();
  //hero.fly();
  print(hero.name);
}

```

## 🖥️ 실행 결과
| 예제 실행 화면 |
|:---------------:|
| ![실행결과 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/ex2.png) |


# 예제3


## 📋 코드 예제
```dart
import 'package:flutter/material.dart';

abstract class Monster {
  void attack();
}

class Goblin implements Monster {
  @override
  void attack() {
    print('고블린 어택!');
  }
}

class Bat implements Monster {
  @override
  void attack() {
    print("할퀴기");
  }
}

void main() {
  Goblin g1 = Goblin();
  Bat b1 = Bat();
  g1.attack();
  b1.attack();

  //monster 의 타입은 ?
  var monster = [g1, b1];
  monster.forEach((m) => m.attack);
}
```

## 🖥️ 실행 결과
| 예제 실행 화면 |
|:---------------:|
| ![실행결과 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/ex3.png) |


# 예제4


## 📋 코드 예제
```dart
import 'package:flutter/material.dart';

enum Status { login, logout }

void main() {
  var authStatus = Status.logout;
  print(authStatus);

  switch (authStatus) {
    case Status.login:
      print('로그인');
      break;
    case Status.logout:
      print('로그아웃');
      break;
  }
}

```

## 🖥️ 실행 결과
| 예제 실행 화면 |
|:---------------:|
| ![실행결과 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/ex4.png) |


# 예제5


## 📋 코드 예제
```dart
import 'package:flutter/material.dart';


void main() {
  var l1 = [1, 2, 3, 4, 5, 6];
  var l2 = ['가', '나', '다', '라', '마', '바'];
  print(l1);
  print(l2);

  l1.add(7);
  print(l1);
  l1.remove(2);
  print(l1);

  var m1 = {'한국': '서울', '일본': '도쿄'};
  print(m1);
  print(m1['한국']);

  var s1 = {1, 2, 3, 3, 3, 3, 4, 5};
  print(s1);
  s1.add(6);
  print(s1);
  s1.add(6);
  print(s1);
}


```

## 🖥️ 실행 결과
| 예제 실행 화면 |
|:---------------:|
| ![실행결과 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/ex5.png) |
