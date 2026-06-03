# habit-trecker
my first habit trecker apps
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
colorScheme: ColorScheme.fromSeed(seedColor: Colors.black),
),
home: const MyHomePage(title: 'Habit'),
);
}
}

class MyHomePage extends StatelessWidget {
const MyHomePage({super.key, required this.title});

final String title;

@override
Widget build(BuildContext context) {
return Scaffold(
appBar: AppBar(
title: Text(title),
elevation: 1,
centerTitle: false,
),
body: Padding(
padding: const EdgeInsets.all(16.0),
child: Column(
children: [
HabitCard(
name: 'Drinking Water',
progress: '1/3 Glasses',
streak: 3,
cardColor: Colors.blue,
circleColor: Colors.red,
icon: Icons.water_drop,
),
const SizedBox(height: 16),
HabitCard(
name: 'Running',
progress: '1 Km',
streak: 5,
cardColor: Colors.green.shade100,
circleColor: Colors.green,
icon: Icons.directions_run,
),
const SizedBox(height: 16),
HabitCard(
name: 'Reading',
progress: '10 Pages',
streak: 7,
cardColor: Colors.blue.shade100,
circleColor: Colors.blue,
icon: Icons.menu_book,
),
const SizedBox(height: 16),
HabitCard(
name: 'Meditation',
progress: '10 min',
streak: 2,
cardColor: Colors.yellow.shade100,
circleColor: Colors.orange,
icon: Icons.self_improvement,
),
const SizedBox(height: 16),
HabitCard(
name: 'Hasan',
progress: 'Flutter Developer',
streak: 1,
cardColor: Colors.purple.shade100,
circleColor: Colors.purple,
icon: Icons.code,
),
],
),
),
);
}
}

class HabitCard extends StatelessWidget {
const HabitCard({
super.key,
required this.name,
required this.progress,
required this.streak,
required this.cardColor,
required this.circleColor,
required this.icon,
});

final String name;
final String progress;
final int streak;
final Color cardColor;
final Color circleColor;
final IconData icon;

@override
Widget build(BuildContext context) {
return Container(
decoration: BoxDecoration(
color: cardColor,
borderRadius: BorderRadius.circular(8),
),
child: Padding(
padding: const EdgeInsets.all(16),
child: Row(
mainAxisAlignment: MainAxisAlignment.spaceBetween,
children: [
Expanded(
child: Row(
children: [
Container(
width: 50,
height: 50,
decoration: BoxDecoration(
shape: BoxShape.circle,
color: circleColor,
),
child: Icon(
icon,
color: Colors.black,
size: 26,
),
),
const SizedBox(width: 10),
Expanded(
child: Column(
crossAxisAlignment: CrossAxisAlignment.start,
children: [
Text(name),
Text(progress),
],
),
),
],
),
),
Column(
crossAxisAlignment: CrossAxisAlignment.end,
children: [
Text('$streak'),
const Text('Streak'),
],
),
],
),
),
);
}
}
