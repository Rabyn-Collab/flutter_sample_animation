```flutter


import 'package:flutter/material.dart';

class HomePage extends StatefulWidget {
  const HomePage({Key? key}) : super(key: key);

  @override
  State<HomePage> createState() => _HomePageState();
}

class _HomePageState extends State<HomePage> {

  bool isChange = false;

  @override
  Widget build(BuildContext context) {

    return Scaffold(
        appBar: AppBar(
          backgroundColor: Colors.purple,
        ),
        body: Column(
          children: [
            InkWell(
                onTap: (){
                  setState(() {
                    isChange = !isChange;
                  });
                },
                child: AnimatedOpacity(
                  duration: Duration(seconds: 1),
                  opacity: isChange ? 1 : 0.5,
                  curve: Curves.easeIn,
                  child: Container(
                    height: 300,
                    width: 300,
                    color: Colors.red,
                    child: Center(child: Text('hello world')),
                  ),
                )
            ),
          ],
        )
    );
  }
}
