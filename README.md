import 'dart:io';

void main() {
  // a. Prompt the user to input two integers: FirstNum and SecondNum
  print("Enter the first number (FirstNum): ");
  int firstNum = int.parse(stdin.readLineSync()!);

  print("Enter the second number (SecondNum): ");
  int secondNum = int.parse(stdin.readLineSync()!);

  if (firstNum >= secondNum) {
    print("FirstNum should be less than SecondNum. Please run the program again.");
    return;
  }

  // b. Store all the integers between FirstNum and SecondNum in a List.
  List<int> numbers = getList(firstNum, secondNum);

  // c. Output all odd numbers between FirstNum and SecondNum
  print("Odd numbers between $firstNum and $secondNum:");
  printOddNumbers(numbers);

  // d. Output the sum of all even numbers between FirstNum and SecondNum
  print("\nSum of even numbers between $firstNum and $secondNum:");
  printSumEvenNumbers(numbers);

  // e. Output the numbers and their squares between FirstNum and SecondNum
  print("\nNumbers and their squares between $firstNum and $secondNum:");
  printNumSquares(numbers);

  // f. Output the sum of the square of the odd numbers between FirstNum and SecondNum
  print("\nSum of squares of odd numbers between $firstNum and $secondNum:");
  printSumSquareOddNumbers(numbers);

  // g. Calculate the average value of the numbers between FirstNum and SecondNum
  print("\nAverage value of the numbers between $firstNum and $secondNum:");
  calculateAverage(numbers);
}

List<int> getList(int firstNum, int secondNum) {
  List<int> numbers = [];
  for (int i = firstNum; i <= secondNum; i++) {
    numbers.add(i);
  }
  return numbers;
}

void printOddNumbers(List<int> numbers) {
  for (int i = 0; i < numbers.length; i++) {
    if (numbers[i] % 2 != 0) {
      print(numbers[i]);
    }
  }
}

void printSumEvenNumbers(List<int> numbers) {
  int sum = 0;
  for (int i = 0; i < numbers.length; i++) {
    if (numbers[i] % 2 == 0) {
      sum += numbers[i];
    }
  }
  print(sum);
}

void printNumSquares(List<int> numbers) {
  for (int i = 0; i < numbers.length; i++) {
    print("${numbers[i]} -> ${numbers[i] * numbers[i]}");
  }
}

void printSumSquareOddNumbers(List<int> numbers) {
  int sum = 0;
  for (int i = 0; i < numbers.length; i++) {
    if (numbers[i] % 2 != 0) {
      sum += (numbers[i] * numbers[i]);
    }
  }
  print(sum);
}

void calculateAverage(List<int> numbers) {
  int sum = 0;
  for (int i = 0; i < numbers.length; i++) {
    sum += numbers[i];
  }
  double average = sum / numbers.length;
  print(average);
}
