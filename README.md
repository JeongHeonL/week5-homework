# week5-homework
  #### 화면나누기
<pre>

  <code>
import 'package:flutter/material.dart';

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
      home: MyHomePage(),
    );
  }
}

class MyHomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: 
      Column(
        children: [
          Row(
            children: [
              Container(
                width: 200,
                height: 200,
                color: Colors.red, // 좌상단
              ),
              Container(
                width: 200,
                height: 200,
                color: Colors.indigo,
                child: Column(
                  children: [
                    Container(
                      width: 200,
                      height: 100,
                      color: Colors.blue, // 우상단 
                    ),
                    Row(
                      children: [
                        Container(
                          width: 100,
                          height: 100,
                          color: Colors.black, // 우상단 좌 하단
                        ),
                        Container(
                          width: 100,
                          height: 100,
                          color: Colors.orange, // 우상단 우 하단
                        ),
                      ],
                    ),
                  ],
                ),
              ),
            ],
          ),
          Row(
            children: [
              Container(
                width: 400,
                height: 200,
                color: Colors.yellow, // 하단 부분
              ),

            ],
          ),
        ],
      ),
    );
  }
}
  </code>
  <hr>
</hr>
</pre>
![2](https://github.com/user-attachments/assets/2ed05607-a135-42d3-9cbe-cf55d0e60c28)

#### 계산기 화면 구현 
<pre>
<code>
  import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData.dark(),
      home: Scaffold(
        appBar: AppBar(
        ),
        body: const Center(
          child: SizedBox(
            width: 800,
            height: 800, 
            child: CalculatorWidget(), // 계산기 위젯을 SizedBox 안에 넣음
          ),
        ),
      ),
    );
  }
}

class CalculatorWidget extends StatefulWidget {
  const CalculatorWidget({Key? key}) : super(key: key);

  @override
  State<CalculatorWidget> createState() => _CalculatorWidgetState();
}

class _CalculatorWidgetState extends State<CalculatorWidget> {
  String _output = "0";

  void buttonPressed(String buttonText) {
    setState(() {
      // 버튼 클릭 시 처리 로직 추가
      _output = buttonText; // 임시로 버튼 텍스트를 출력
    });
  }

  Widget buildButton(String buttonText) {
    return Expanded(
      child: Padding(
        padding: const EdgeInsets.all(4.0),
        child: MaterialButton(
          padding: const EdgeInsets.all(24.0),
          child: Text(
            buttonText,
            style: const TextStyle(fontSize: 20.0, fontWeight: FontWeight.bold),
          ),
          color: Colors.grey[800],
          textColor: Colors.white,
          onPressed: () => buttonPressed(buttonText),
        ),
      ),
    );
  }

  @override
  Widget build(BuildContext context) {
    return Container(
      decoration: BoxDecoration(
        border: Border.all(color: Colors.black, width: 2), // 테두리 추가 (선택 사항)
      ),
      child: Scaffold(
        backgroundColor: Colors.transparent,
        appBar: null,
        body: Column(
          children: <Widget>[
            Container(
              alignment: Alignment.centerRight,
              padding: const EdgeInsets.symmetric(vertical: 24.0, horizontal: 12.0),
              child: Text(
                _output,
                style: const TextStyle(fontSize: 48.0, fontWeight: FontWeight.bold, color: Colors.white),
              ),
            ),
            const Expanded(
              child: Divider(),
            ),
            Column(
              children: [
                Row(
                  children: [
                    buildButton("%"),
                    buildButton("CE"),
                    buildButton("C"),
                    buildButton("MR"),
                  ],
                ),
                Row(
                  children: [
                    buildButton("7"),
                    buildButton("8"),
                    buildButton("9"),
                    buildButton("/"),
                  ],
                ),
                Row(
                  children: [
                    buildButton("4"),
                    buildButton("5"),
                    buildButton("6"),
                    buildButton("x"),
                  ],
                ),
                Row(
                  children: [
                    buildButton("1"),
                    buildButton("2"),
                    buildButton("3"),
                    buildButton("-"),
                  ],
                ),
                Row(
                  children: [
                    buildButton("0"),
                    buildButton("."),
                    buildButton("="),
                    buildButton("+"),
                  ],
                ),
              ],
            )
          ],
        ),
      ),
    );
  }
}

</code>
</pre>
![3](https://github.com/user-attachments/assets/68e9cfe6-e5d7-4b4d-9de6-6238eceff502)
