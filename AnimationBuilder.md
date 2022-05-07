```flutter


import 'dart:math';

import 'package:flutter/material.dart';

class HomePage extends StatefulWidget {
  const HomePage({Key? key}) : super(key: key);

  @override
  State<HomePage> createState() => _HomePageState();
}

class _HomePageState extends State<HomePage> with SingleTickerProviderStateMixin{


late  AnimationController controller;
 late Animation<double> animation;

 @override
  void initState() {
   controller =AnimationController(
       duration: Duration(seconds: 3),
       vsync: this)..repeat();
    super.initState();
    animation = Tween<double>(
      begin: 0,
      end: pi
    ).animate(controller);
  }
  @override
  Widget build(BuildContext context) {
    return Scaffold(
        body:Stack(
          children: [
            AnimatedBuilder(
              child: Container(
                height: 200,
                width: 200,
                color: Colors.red,
              ),
                builder: (context, child){
                  return Positioned(
                    top: 0,
                    right:  controller.value * 200,
                    child: child!,
                  );
                },

              animation: controller,
            ),
          ],
        ),
    );
  }
}
