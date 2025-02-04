# Tugas_Week_4

Class Diagram
import 'dart:io';

// Abstraction
abstract class GradingSystem {
  String determineGrade(double score);
}

// Inheritance
class StandardGradingSystem extends GradingSystem {
  @override
  String determineGrade(double score) {
    if (score >= 85 && score <= 100) {
      return 'A';
    } else if (score >= 80 && score < 85) {
      return 'AB';
    } else if (score >= 70 && score < 80) {
      return 'B';
    } else if (score >= 65 && score < 70) {
      return 'BC';
    } else if (score >= 55 && score < 65) {
      return 'C';
    } else if (score >= 40 && score < 55) {
      return 'D';
    } else if (score >= 0 && score < 40) {
      return 'E';
    } else {
      return 'T (Tidak Valid)';
    }
  }
}

// Polymorphism
void main() {
  GradingSystem gradingSystem = StandardGradingSystem();

  while (true) {
    try {
      stdout.write('Masukkan skor (0-100) atau "exit" untuk keluar: ');
      String? input = stdin.readLineSync();

      if (input != null && input.toLowerCase() == 'exit') {
        print('Program selesai.');
        break;
      }

      double score = double.parse(input!);
      String grade = gradingSystem.determineGrade(score);

      print('Indeks nilai Anda: $grade');
    } catch (e) {
      print('Input tidak valid, masukkan angka antara 0-100 atau "exit".');
    }
  }
}


Flutter Basic
import 'package:flutter/material.dart';

void main() {
  runApp(const MainApp());
}

class MainApp extends StatelessWidget {
  const MainApp({super.key});

  @override
  Widget build(BuildContext context) {
    return const MaterialApp(
      home: Scaffold(
        body: Center(
          child: Column(
            children: [
              Text(
                'Muhammad Arief Faruq Wafdan',
                style: TextStyle(fontSize: 20, fontWeight: FontWeight.bold),
                ),
              Text(
                'S1 Informatika',
                style: TextStyle(fontSize: 20, fontWeight: FontWeight.bold),
                ),
            ],
          ),
        ),
      ),
    );
  }
}
