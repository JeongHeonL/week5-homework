# week5-homework

<pre>
  #### 화면나누기기
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
