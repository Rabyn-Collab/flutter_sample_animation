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
                child: Container(
                  height: 300,
                  width: 300,
                  color: Colors.red,
                  child: AnimatedAlign(
                    curve: Curves.easeIn,
                      duration: Duration(seconds: 1),
                      alignment: isChange ? Alignment.center : Alignment.topLeft,
                      child: Text('hello world')),
                )
            ),
          ],
        )
    );
  }
}

