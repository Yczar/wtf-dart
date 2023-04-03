## Welcome to the "WTF Dart" repository!

This repository is a collection of Dart code snippets and examples that may make you say "WTF" (What the F\*ck) at first glance. However, these snippets are meant to be educational and demonstrate some of the more unusual or unexpected behaviors of the Dart programming language.

## How to Use

To use this repository, simply clone or download the code and explore the examples. Each file is labeled with a short description of what it demonstrates. You can run the code using the Dart SDK, which can be downloaded from the [official Dart website](https://dart.dev/get-dart).

It's important to note that some of these examples may not be suitable for production use, and should be used with caution. Additionally, some of the examples may have unintended consequences or may not behave as you expect, so be sure to read through the code and understand what it's doing before using it in your own projects.

## Contributing

If you have your own "WTF" Dart examples that you'd like to share, feel free to submit a pull request! We welcome contributions from the community, and we're always looking for new and interesting examples to add to the repository.

Please be sure to include a brief description of what your example demonstrates, as well as any notes or warnings about potential pitfalls or unexpected behavior.

# Table of Contents

- [💪🏻 Motivation](#-motivation)
- [✍🏻 Notation](#-notation)
- [👀 Examples](#-examples)
  - [null is not null](#null-is-not-null)
  - [This code does nothing](#this-code-does-nothing)
  - [Switch case fall-through](#switch-case-fall-through)
  - [Recursive function with no base case](#recursive-function-with-no-base-case)
  - [Type Mismatch and Comparison Error](#type-mismatch-and-comparison-error)
  - [String indexing](#string-indexing)
  - [Using `is` with `!`](#using-is-with--!)
  - [Function with optional positional arguments](#function-with-optional-positional-arguments)
  - [Using `await` without `async`](#using--without--)
  - [Mixing `var` and `final`](#mixing-var-and-final)
  - [Comparing doubles](#comparing-doubles)
  - [Recursive function with no base case](#reecursive-function-with-no-base-case)
  - [Recursive function with no base case](#reecursive-function-with-no-base-case)
  - [Recursive function with no base case](#reecursive-function-with-no-base-case)
  - [Recursive function with no base case](#reecursive-function-with-no-base-case)
  - [Recursive function with no base case](#reecursive-function-with-no-base-case)
  - [Recursive function with no base case](#reecursive-function-with-no-base-case)
  - [Recursive function with no base case](#reecursive-function-with-no-base-case)
  - [Recursive function with no base case](#reecursive-function-with-no-base-case)
  - [Recursive function with no base case](#reecursive-function-with-no-base-case)

## Null is not null
```dart
 var a = Null;
  if (a != null) {
    print("null is not null");
  }
```
"Wait, so even though a is assigned the value Null, the condition a != null still evaluates to true? That doesn't make any sense! How can Null not be equal to null?"

The reason for this behavior is that Null is actually a type in Dart, not a value. When you assign a variable the value Null, you're actually assigning it the null value of the variable's declared type (which is usually dynamic if you don't specify a type). So even though a is assigned the value Null, its type is still dynamic, and the condition a != null evaluates to true because a has a non-null value (even though that value happens to be null). This can be confusing if you're not familiar with Dart's type system and null safety.

## This code does nothing
```dart
void main() {
  while(true);
}
```
This code may seem like an infinite loop, but it actually does nothing because the loop condition is always true and there is no code inside the loop. This can be a WTF moment if you're not expecting it.

`Disclaimer:` The above code crashed my Dart Pad.

## Switch case fall-through
```dart
void main() {
  var i = 2;
  switch (i) {
    case 1:
      print("One");
      break;
    case 2:
    case 3:
      print("Two or Three");
      break;
    default:
      print("Something else");
  }
}
```
In Dart, switch cases can fall through to the next case unless a break statement is used. This code will print "Two or Three" because the case 2: statement falls through to case 3:

## Recursive function with no base case
```dart
void main() {
  int factorial(int n) {
    return n * factorial(n - 1);
  }

  print(factorial(5));
}
```
This code defines a recursive function to calculate the factorial of a number, but there is no base case to stop the recursion. When factorial(0) is called, the function will continue to call itself with negative numbers until a stack overflow error occurs.

## Type Mismatch and Comparison Error
```dart
void main() {
  var x = 10;
  var y = "20";

  if (x < y) {
    print("x is less than y");
  }
}
```
At first glance, this code might seem reasonable: you're comparing two values to see which one is less. However, it will actually throw a runtime error because x is an integer and y is a string. In Dart, you cannot directly compare values of different types, so attempting to do so will result in a type error. This can be a WTF moment if you're not expecting it.

## String indexing
```dart
void main() {
  var str = "Hello";
  print(str[0]); // Prints "H"
}
```
In Dart, you can access individual characters of a string using square brackets, as if the string were an array. This can be a WTF moment if you're coming from a language that doesn't allow string indexing.

## Using `is` with `!`
```dart
void main() {
  var a = "Hello";
  if (a is! int) {
    print("a is not an int");
  }
}
```
In Dart, you can use the `is` operator to check the type of a variable, and you can negate the result using `!`. This code will print "a is not an int" because `a` is a string.

## Function with optional positional arguments
```dart
void main() {
  void greet(String name, [String greeting = "Hello"]) {
    print("$greeting, $name!");
  }

  greet("Czar"); // Prints "Hello, Czar!"
  greet("Czar", "Hi"); // Prints "Hi, Czar!"
}
```
In Dart, you can define optional positional arguments by enclosing them in square brackets. This can be a WTF moment if you're not expecting optional arguments.

## Using `await` without `async`
```dart
Future<String> getData() async {
  return "Data";
}

void main() {
  var data = await getData();
  print(data);
}
```
In Dart, the await keyword is used to wait for a Future to complete, but it can only be used inside an async function. This code will produce a compiler error because main() is not declared as async.

## Mixing `var` and `final`
```dart
void main() {
  final var a = "Hello";
  print(a);
}
```
In Dart, `var` is used to declare a variable with inferred type, and final is used to declare a variable that can only be assigned once. This code will produce a compiler error because `var` and `final` cannot be used together.

## Comparing doubles
```dart
void main() {
  var a = 0.1 + 0.2;
  var b = 0.3;
  if (a == b) {
    print("Equal!");
  } else {
    print("Not equal!");
  }
}
```
In Dart, comparing floating-point numbers can produce unexpected results due to the way they are represented in memory. This code will print "Not equal!" even though mathematically `0.1 + 0.2` is equal to `0.3`.

## Using `as` with `null`
```dart
void main() {
  var a = null;
  print(a as String);
}
```
In Dart, you can use the `as` operator to cast a variable to a certain type, but it will throw a runtime error if the cast fails. This code will throw a `TypeError` because `a` is `null` and cannot be cast to `String`.

## Accessing private members
```dart
class Person {
  String _name = "Alice";
}

void main() {
  var p = Person();
  print(p._name);
}
```
In Dart, you can use an underscore prefix to mark a member as private, but it is still accessible from outside the class. This code will print "Alice" even though `_name` is marked as private.

## Using `assert` with side effects
```dart
void main() {
  var a = 0;
  assert((a += 1) == 1);
  print(a);
}
```
In Dart, you can use the `assert` keyword to check a condition during development, but it should not have any side effects. This code will print "1" even though `a` was modified by the` assert` statement.

## Using `try` without `catch` or `finally`
```dart
void main() {
  try {
    print("Hello");
  }
}
```
In Dart, you can use the `try` keyword to enclose code that may throw an exception, but you must also use either catch or finally to handle the exception. This code will produce a compiler error because try is not followed by catch or finally

## Method Chaining with the Cascade Operator
```dart
class Person {
  String? name;
  int? age;
  void greet() => print("Hello, my name is $name and I'm $age years old.");
}

void main() {
  var person = Person()
    ..name = "John"
    ..age = 30
    ..greet();
}
```
This will actually print "Hello, my name is John and I'm 30 years old.", because the cascade notation allows you to call the greet() method on the same object that you're setting the name and age properties on. This can be a bit confusing if you're not familiar with the cascade notation syntax.

## Operator Precedence and Grouping
```dart
void main() {
  int x = 1;
  int y = 2;
  print(x > 0 || y > 0 && x < y); // Output: true
}
```
In this code, the `||` and `&&` operators are used to combine multiple boolean expressions. However, the order of evaluation can be unexpected. In this case, the `&&` operator has higher precedence than the `||` operator, so `y > 0 && x < y` is evaluated first, resulting in `true`. Then, `true || true` is evaluated, resulting in `true`. This can be a WTF moment if you're not familiar with operator precedence in Dart.

## Copying Maps with `Map.from()`
```dart
void main() {
  var source = {"a": 1, "b": 2};
  var copy = Map.from(source);
  copy["a"] = 3;
  print(source); // Output: {a: 1, b: 2}
  print(copy); // Output: {a: 3, b: 2}
}
```
In this code, `Map.from()` is used to create a copy of a map `source`. However, when a value is updated in the copy, the original map is not affected. This can be a WTF moment if you're expecting the two maps to be linked together.

## String Concatenation without the + Operator
```dart
void main() {
  String s = "hello" " world";// Output: hello world
  print(s);
}
```
In Dart, you can concatenate strings using the `+` operator, just like in many other programming languages. However, you can also concatenate strings by simply placing them next to each other, without any operator between them.

In the above code, the string "hello" and "world" are placed next to each other without any operator between them. The resulting string is "hello world", which is printed to the console. This can be a WTF moment if you're not familiar with this syntax in Dart.

## License

This repository is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.
