# Flutter 

이 Flutter 애플리케이션에서 Navigator.push() 메서드를 사용하여 FirstPage에서 SecondPage로 전환 후
Navigator.pop()메서드를 사용하여 현재 화면을 종료하고 메모리에 남아있는 FirstPage로 돌아갑니다.

initState는 위젯이 처음 생성될 때 딱 한 번 호출되는 함수로 생명주기 메서드 입니다.
오직 한 번만 호출 됩니다 (build는 여러번 호출 될 수 있음)
가장 먼저 호출 해야합니다.
초기 데이터 세팅을 initState에서 하기 때문에 build는 오로지 화면을 그리는 역할만 수행 할 수 있습니다.

dispose는 위젯이 사라질 때 호출되는 함수로 또한 생명주기 메서드입니다.
위젯이 더 이상 필요 없어질 때 호출 됩니다.
가장 마지막에 호출 해야합니다.
메모리 낭비를 막을 수 있는 장점이 있습니다.




## 📋 main.dart (initState, dispose 사용 x)
```dart
import 'package:flutter/material.dart';

import 'Person.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  const MyApp({super.key});
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
       colorScheme: ColorScheme.fromSeed(seedColor: Colors.deepPurple),
      ),
      home: FirstStatefulPage(),
    );
  }
}

class FirstStatefulPage extends StatefulWidget {
  @override
  _FirstStatefulPageState createState() => _FirstStatefulPageState();
}

class _FirstStatefulPageState extends State<FirstStatefulPage> {
  @override
  Widget build(BuildContext context) {
    print('FirstPage build()');
    return Scaffold(
      appBar: AppBar(
        title: Text('First'),
      ),
      body: ElevatedButton(
        child: Text('다음 페이지로'),
        onPressed: () {
          final person = Person('홍길동', 20);
          Navigator.push(
            context,
            MaterialPageRoute(builder: (context) => SecondStatefulPage(person: person)),
          );
        },
      ),
    );
  }
}


class SecondStatefulPage extends StatefulWidget {
  final Person person;

  SecondStatefulPage({Key? key, required this.person}) : super(key:key);

  @override
  _SecondStatefulPageState createState() => _SecondStatefulPageState();
}

class _SecondStatefulPageState extends State<SecondStatefulPage> {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Second'),
      ),
      body: ElevatedButton(
        child: Text('이전 페이지로'),
        onPressed: () {
          Navigator.pop(context);
        },
      ),
    );
  }
}

```

## 📋 main.dart (initState, dispose사용)
```dart
import 'package:flutter/material.dart';

import 'Person.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  const MyApp({super.key});
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
       colorScheme: ColorScheme.fromSeed(seedColor: Colors.deepPurple),
      ),
      home: FirstStatefulPage(),
    );
  }
}

class FirstStatefulPage extends StatefulWidget {
  @override
  _FirstStatefulPageState createState() => _FirstStatefulPageState();
}

class _FirstStatefulPageState extends State<FirstStatefulPage> {
  @override
  void initState() {
    super.initState();
    print('FirstPage initState()');
  }

  @override
  void dispose() {
    super.dispose();
    print('FirstPage dispose()');
  }

  @override
  Widget build(BuildContext context) {
    print('FirstPage build()');
    return Scaffold(
      appBar: AppBar(
        title: Text('First'),
      ),
      body: ElevatedButton(
        child: Text('다음 페이지로'),
        onPressed: () {
          final person = Person('홍길동', 20);
          Navigator.push(
            context,
            MaterialPageRoute(builder: (context) => SecondStatefulPage(person: person)),
          );
        },
      ),
    );
  }
}


class SecondStatefulPage extends StatefulWidget {
  final Person person;

  SecondStatefulPage({Key? key, required this.person}) : super(key:key);

  @override
  _SecondStatefulPageState createState() => _SecondStatefulPageState();
}

class _SecondStatefulPageState extends State<SecondStatefulPage> {
  @override
  void initState() {
    super.initState();
    print('SecondPage initState()');
  }
  @override
  void dispose() {
    super.dispose();
    print('SecondPage dispose()');
  }
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Second'),
      ),
      body: ElevatedButton(
        child: Text('이전 페이지로'),
        onPressed: () {
          Navigator.pop(context);
        },
      ),
    );
  }
}


```



## 🖥️ 실행 결과
| FirstPage |
|:---------------:|
| ![Hello World 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/initStatedispose1.png) |

| SecondPage |
|:---------------:|
| ![Hello World 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/initStatedispose2.png) |

| Log |
|:---------------:|
| ![Hello World 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/initStatedispose3.png) |


