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
                child: AnimatedContainer(
                  duration: Duration(seconds: 1),
                  curve: Curves.easeIn,
                  height: isChange ? 200 : 300,
                  width: isChange ? 200 : 300,
                  color: Colors.red,
                )
            ),
          ],
        )
    );
  }
}








