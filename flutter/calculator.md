# Flutter 

이 Flutter 애플리케이션은 화면에 위젯을 배치하는 코드입니다.

body: Center(
  child: Container(...)
)를 통해 계산기를 화면 중앙에 위치

borderRadius를 사용해 모서리를 둥글게 설정

boxShadow를 통해 입체감을 줌

child를 사용해 부모의 위젯 Center안에 배치



## 📋 코드 예제
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(CalculatorApp());
}

class CalculatorApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: CalculatorUI(),
      debugShowCheckedModeBanner: false,
    );
  }
}

class CalculatorUI extends StatelessWidget {
  final List<List<String>> buttons = [
    ['MC', 'MR', 'M+', 'M-'],
    ['MS', 'CE', 'C', '⌫'],
    ['%', '√', 'x²', '1/x'],
    ['7', '8', '9', '÷'],
    ['4', '5', '6', '×'],
    ['1', '2', '3', '−'],
    ['±', '0', '.', '+'],
    [' ', ' ', ' ', '='],
  ];

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.cyan,
      body: Center(
        child: Container(
          width: 320,
          height: 500,
          padding: EdgeInsets.all(12),
          decoration: BoxDecoration(
            color: Colors.black87,
            borderRadius: BorderRadius.circular(16),
            boxShadow: [
              BoxShadow(
                color: Colors.black45,
                blurRadius: 10,
                offset: Offset(4, 4),
              ),
            ],
          ),
          child: Column(
            children: [
              Container(
                alignment: Alignment.centerRight,
                padding: EdgeInsets.symmetric(vertical: 20, horizontal: 12),
                child: Text(
                  '0',
                  style: TextStyle(
                    fontSize: 36,
                    color: Colors.white,
                  ),
                ),
              ),
              Expanded(
                child: GridView.builder(
                  physics: NeverScrollableScrollPhysics(),
                  itemCount: buttons.length * 4,
                  gridDelegate: SliverGridDelegateWithFixedCrossAxisCount(
                    crossAxisCount: 4,
                    mainAxisSpacing: 8,
                    crossAxisSpacing: 8,
                    childAspectRatio: 1.2,
                  ),
                  itemBuilder: (context, index) {
                    int row = index ~/ 4;
                    int col = index % 4;
                    String label = buttons[row][col];

                    if (label.trim().isEmpty) {
                      return SizedBox.shrink();
                    }

                    bool isEqual = label == '=';
                    bool isOperator = ['÷', '×', '−', '+', '=', 'CE', 'C', '⌫'].contains(label);

                    return Container(
                      decoration: BoxDecoration(
                        color: isEqual
                            ? Colors.lightBlue
                            : isOperator
                            ? Colors.grey[800]
                            : Colors.grey[700],
                        borderRadius: BorderRadius.circular(8),
                      ),
                      child: Center(
                        child: Text(
                          label,
                          style: TextStyle(
                            fontSize: 20,
                            fontWeight: FontWeight.bold,
                            color: isEqual ? Colors.white : Colors.white70,
                          ),
                        ),
                      ),
                    );
                  },
                ),
              ),
            ],
          ),
        ),
      ),
    );
  }
}

```

## 🖥️ 실행 결과
| 예제 실행 화면 |
|:---------------:|
| ![Hello World 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/calculator.png) |


