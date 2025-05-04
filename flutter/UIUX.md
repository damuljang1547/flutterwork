# Flutter 

값(데이터)과 값을 화면에 표현하는 로직을 구분하여 구현하는 것이 중요한 이유

1. 관심사의 분리
: 데이터 로직(모델, 상태)은 실제 앱의 동작이나 기능을 처리하고, UI 로직(위젯 트리)은 사용자에게 보여지는 부분만 책임지게 하면, 각 부분을
  독립적으로   테스트, 수정, 재사용할 수 있음.

2. 유지보수가 쉬워짐
: 값이 바뀌었는데 화면이 안 바뀌거나, UI 바꾸다가 데이터가 손상되는 문제를 줄일 수 있음.

3. 테스트 용이성
: UI는 테스트가 복잡하고 시간이 오래 걸리지만 데이터 로직은 단위 테스트로 빠르게 가능함.
  값과 로직이 분리돼 있으면, 앱의 핵심 기능만 따로 테스트할 수 있음.

4. 재사용성과 확장성
: 하나의 CardWidget이 다양한 데이터를 받아서 표현할 수 있으려면, 데이터는 따로, 화면은 유연하게 구성돼야 함.
  이렇게 해두면 재사용 가능한 컴포넌트를 쉽게 만들 수 있음.




## 📋 복잡한 UI/UX main.dart
```dart

import 'package:a_7_1/page3.dart';
import 'package:flutter/material.dart';
import 'package:a_7_1/page1.dart';
import 'package:a_7_1/page2.dart';
import 'package:a_7_1/page3.dart';

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
      home: const MyHomePage(title: 'Flutter Demo Home Page'),
      debugShowCheckedModeBanner: false,
    );
  }
}

class MyHomePage extends StatefulWidget {
  const MyHomePage({super.key, required this.title});

  final String title;

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  var _index = 0;
  final _pages = [
    Page1(),
    Page2(),
    Page3(),
  ];

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        backgroundColor: Colors.white,
        title: const Text('복잡한 UI', style: TextStyle(color: Colors.black)),
        centerTitle: true,
        actions: [
          IconButton(
            icon: const Icon(Icons.add, color: Colors.black),
            onPressed: () {},
          )
        ],
      ),
      body: _pages[_index],
      bottomNavigationBar: BottomNavigationBar(
        currentIndex: _index,
        items: const [
          BottomNavigationBarItem(label: '홈', icon: Icon(Icons.home)),
          BottomNavigationBarItem(label: '이용서비스', icon: Icon(Icons.assignment)),
          BottomNavigationBarItem(label: '내 정보', icon: Icon(Icons.account_circle)),
        ],
        onTap: (index) {
          setState(() {
            _index = index;
          });
        },
      ),
    );
  }
}



```

## 📋 page1.dart
```dart
import 'package:flutter/material.dart';
import 'package:carousel_slider/carousel_slider.dart';
import 'data/image_data.dart';
import 'data/notice_data.dart';

class Page1 extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        _buildTop(),
        _buildMiddle(),
        _buildBottom(),
      ],
    );
  }

  Widget _buildTop() {
    return Column(
      children: [
        Row(
          mainAxisAlignment: MainAxisAlignment.spaceEvenly,
          children: List.generate(4, (_) => _buildTexiMenu()),
        ),
        const SizedBox(height: 20),
        Row(
          mainAxisAlignment: MainAxisAlignment.spaceEvenly,
          children: List.generate(3, (_) => _buildTexiMenu())..add(_buildTexiMenu(visible: false)),
        ),
      ],
    );
  }

  Widget _buildTexiMenu({bool visible = true}) {
    return Opacity(
      opacity: visible ? 1.0 : 0.0,
      child: InkWell(
        onTap: () {},
        child: Column(
          children: const [
            Icon(Icons.local_taxi, size: 40),
            Text('택시'),
          ],
        ),
      ),
    );
  }

  Widget _buildMiddle() {
    return CarouselSlider(
      items: ImageData.carouselUrls.map((url) {
        return Builder(
          builder: (context) => Container(
            width: MediaQuery.of(context).size.width,
            margin: const EdgeInsets.symmetric(horizontal: 5.0),
            decoration: const BoxDecoration(color: Colors.amber),
            child: Image.network(url, fit: BoxFit.cover),
          ),
        );
      }).toList(),
      options: CarouselOptions(height: 150, autoPlay: true),
    );
  }

  Widget _buildBottom() {
    return ListView.builder(
      shrinkWrap: true,
      physics: const NeverScrollableScrollPhysics(),
      itemCount: NoticeData.notices.length,
      itemBuilder: (context, index) {
        return ListTile(
          leading: const Icon(Icons.notifications_none),
          title: Text(NoticeData.notices[index]),
        );
      },
    );
  }
}

```

## 📋 data/image_data.dart
```dart
class ImageData {
  static final List<String> carouselUrls = [
    'https://cdn.pixabay.com/photo/2018/11/12/18/44/thanksgiving-3811492_1280.jpg',
    'https://cdn.pixabay.com/photo/2019/10/30/15/33/tajikistan-4589831_1280.jpg',
    'https://cdn.pixabay.com/photo/2019/11/25/16/15/sfari-4652364_1280.jpg',
  ];
}
```

## 📋 data/notice_data.dart
```dart
class NoticeData {
  static final List<String> notices = List.generate(
    10,
        (i) => '[이벤트] 이것은 공지사항 $i입니다',
  );
}

```

## 📋 page2.dart
```dart
import 'package:flutter/material.dart';

class Page2 extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Center(child: Text('이용 서비스', style: TextStyle(fontSize: 40)));
  }
}

```

## 📋 page3.dart
```dart
import 'package:flutter/material.dart';

class Page3 extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Center(child: Text('내 정보', style: TextStyle(fontSize: 40)));
  }
}
```



## 🖥️ 실행 결과
| FirstPage |
|:---------------:|
| ![Hello World 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/UIUX.png) |

| SecondPage |
|:---------------:|
| ![Hello World 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/UIUX2.png) |

| ThirdPage |
|:---------------:|
| ![Hello World 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/UIUX3.png) |


