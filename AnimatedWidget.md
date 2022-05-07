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
        body: RotateWidget(listenable: controller, animation: animation,)
    );
  }
}


class RotateWidget extends AnimatedWidget {
  RotateWidget({required Listenable listenable, required this.animation}) : super(listenable: listenable);
  final Animation<double> animation;

  @override
  Widget build(BuildContext context) {
    return Center(
      child: Transform.rotate(
        angle: pi * animation.value,
        child: Container(
          color: Colors.red,
          height: 300,
          width: 300,
        ),
      ),
    );
  }
}

