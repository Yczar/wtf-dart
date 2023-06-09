## Welcome to the "WTF Dart" repository!

inspired by the [wtfjs](https://github.com/denysdovhan/wtfjs) repository

This repository is a collection of Dart code snippets and examples that may make you say "WTF" (What the F\*ck) at first glance. However, these snippets are meant to be educational and demonstrate some of the more unusual or unexpected behaviors of the Dart programming language.

## How to Use

To use this repository, simply clone or download the code and explore the examples. Every code is labeled with a short description of what it demonstrates. You can run the code using the Dart SDK, which can be downloaded from the [official Dart website](https://dart.dev/get-dart).

It's important to note that some of these examples may not be suitable for production use, and should be used with caution. Additionally, some of the examples may have unintended consequences or may not behave as you expect, so be sure to read through the code and understand what it's doing before using it in your own projects.

## Contributing

If you have your own "WTF" Dart examples that you'd like to share, feel free to submit a pull request! We welcome contributions from the community, and we're always looking for new and interesting examples to add to the repository.

Please be sure to include a brief description of what your example demonstrates, as well as any notes or warnings about potential pitfalls or unexpected behavior.

# Table of Contents

- [💪🏻 Motivation](#-motivation)
- [👀 Examples](#-examples)
  - [null is not null](#null-is-not-null)
  - [This code does nothing](#this-code-does-nothing)
  - [Switch case fall-through](#switch-case-fall-through)
  - [Recursive function with no base case](#recursive-function-with-no-base-case)
  - [Type Mismatch and Comparison Error](#type-mismatch-and-comparison-error)
  - [String indexing](#string-indexing)
  - [Using `is` with `!`](#using-is-with--)
  - [Function with optional positional arguments](#function-with-optional-positional-arguments)
  - [Using `await` without `async`](#using--without--)
  - [Mixing `var` and `final`](#mixing-var-and-final)
  - [Comparing doubles](#comparing-doubles)
  - [Using `as` with `null`](#using-as-with-null)
  - [Accessing private members](#accessing-private-members)
  - [Using `assert` with side effects](#using-assert-with-side-effects)
  - [Using `try` without `catch` or `finally`](#using-try-without-catch-or-finally)
  - [Method Chaining with the Cascade Operator](#method-chaining-with-the-cascade-operator)
  - [Operator Precedence and Grouping](#operator-precedence-and-grouping)
  - [Copying Maps with `Map.from()`](copying-maps-with--)
  - [String Concatenation without the + Operator](#string-concatenation-without-the-+-Operator)
  - [Surprising Results with `num.parse()`](<#surprising-results-with-num.parse()>)
  - [String Interpolation with Conditional Expressions](#string-interpolation-with-conditional-expressions)
  - [Behavior with Optional Variables](#behavior-with-optional-variables)

# 💪🏻 Motivation

> "Programming is not about what you know, it's about what you can figure out."
>
> &mdash; _Chris Pine_

WTF-Dart is a repository created with the goal of showcasing surprising or unconventional behavior in Dart programming language. The repository contains a collection of Dart code snippets that demonstrate unexpected results or non-intuitive behavior in the language, which can be useful for developers who are learning Dart or working with it on a regular basis.

By exploring these code snippets and learning about the quirks and surprises of the Dart language, developers can gain a deeper understanding of how the language works and how to avoid potential pitfalls. This repository is also a valuable resource for educators who teach Dart programming, as it provides real-world examples of how the language can behave in unexpected ways.

Ultimately, WTF-Dart aims to help developers write more reliable and efficient code in Dart by providing them with a deeper understanding of the language's behavior. Whether you're a beginner or an experienced developer, this repository is a great resource for learning about the nuances of the Dart language and improving your coding skills.

> **⚠️ Note:** If you enjoy reading this document, please, [consider supporting the author of this collection](#-supporting).

## Null is not null

```dart
 var a = Null;
  if (a != null) {
    print("null is not null");
  }
```

### 💡 Explanation:

"Wait, so even though a is assigned the value Null, the condition a != null still evaluates to true? That doesn't make any sense! How can Null not be equal to null?"

The reason for this behavior is that Null is actually a type in Dart, not a value. When you assign a variable the value Null, you're actually assigning it the null value of the variable's declared type (which is usually dynamic if you don't specify a type). So even though a is assigned the value Null, its type is still dynamic, and the condition a != null evaluates to true because a has a non-null value (even though that value happens to be null). This can be confusing if you're not familiar with Dart's type system and null safety.

## This code does nothing

```dart
void main() {
  while(true);
}
```

### 💡 Explanation:

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

### 💡 Explanation:

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

### 💡 Explanation:

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

### 💡 Explanation:

At first glance, this code might seem reasonable: you're comparing two values to see which one is less. However, it will actually throw a runtime error because x is an integer and y is a string. In Dart, you cannot directly compare values of different types, so attempting to do so will result in a type error. This can be a WTF moment if you're not expecting it.

## String indexing

```dart
void main() {
  var str = "Hello";
  print(str[0]); // Prints "H"
}
```

### 💡 Explanation:

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

### 💡 Explanation:

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

### 💡 Explanation:

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

### 💡 Explanation:

In Dart, the await keyword is used to wait for a Future to complete, but it can only be used inside an async function. This code will produce a compiler error because main() is not declared as async.

## Mixing `var` and `final`

```dart
void main() {
  final var a = "Hello";
  print(a);
}
```

### 💡 Explanation:

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

### 💡 Explanation:

In Dart, comparing floating-point numbers can produce unexpected results due to the way they are represented in memory. This code will print "Not equal!" even though mathematically `0.1 + 0.2` is equal to `0.3`.

## Using `as` with `null`

```dart
void main() {
  var a = null;
  print(a as String);
}
```

### 💡 Explanation:

In Dart, you can use the `as` operator to cast a variable to a certain type, but it will throw a runtime error if the cast fails. This code will throw a `TypeError` because `a` is `null` and cannot be cast to `String`.

## Accessing private members

```dart
class Person {
  String _name = "czar";
}

void main() {
  var p = Person();
  print(p._name);
}
```

### 💡 Explanation:

In Dart, you can use an underscore prefix to mark a member as private, but it is still accessible from outside the class. This code will print "czar" even though `_name` is marked as private.

## Using `assert` with side effects

```dart
void main() {
  var a = 0;
  assert((a += 1) == 1);
  print(a);
}
```

### 💡 Explanation:

In Dart, you can use the `assert` keyword to check a condition during development, but it should not have any side effects. This code will print "1" even though `a` was modified by the` assert` statement.

## Using `try` without `catch` or `finally`

```dart
void main() {
  try {
    print("Hello");
  }
}
```

### 💡 Explanation:

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
    ..name = "Czar"
    ..age = 17
    ..greet();
}
```

### 💡 Explanation:

This will actually print "Hello, my name is Czar and I'm 17 years old.", because the cascade notation allows you to call the greet() method on the same object that you're setting the name and age properties on. This can be a bit confusing if you're not familiar with the cascade notation syntax.

## Operator Precedence and Grouping

```dart
void main() {
  int x = 1;
  int y = 2;
  print(x > 0 || y > 0 && x < y); // Output: true
}
```

### 💡 Explanation:

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

### 💡 Explanation:

In this code, `Map.from()` is used to create a copy of a map `source`. However, when a value is updated in the copy, the original map is not affected. This can be a WTF moment if you're expecting the two maps to be linked together.

## String Concatenation without the + Operator

```dart
void main() {
  String s = "hello" " world";// Output: hello world
  print(s);
}
```

### 💡 Explanation:

In Dart, you can concatenate strings using the `+` operator, just like in many other programming languages. However, you can also concatenate strings by simply placing them next to each other, without any operator between them.

In the above code, the string "hello" and "world" are placed next to each other without any operator between them. The resulting string is "hello world", which is printed to the console. This can be a WTF moment if you're not familiar with this syntax in Dart.

## Surprising Results with `num.parse()`

```dart
void main() {
  String str1 = '42';
  String str2 = '3.14159';
  String str3 = '0x42';
  int intVal = num.parse(str1).toInt();
  double doubleVal = num.parse(str2).toDouble();
  int hexVal = num.parse(str3).toInt();
  print(intVal); // Output: 42
  print(doubleVal); // Output: 3.14159
  print(hexVal); // Output: 66
}
```

### 💡 Explanation:

This Dart code snippet demonstrates how to use the `num.parse()` method to convert strings to numbers. However, the results can be surprising due to the way Dart handles different types of numbers. In this case, the code parses three different strings as integers, doubles, and hexadecimal integers, respectively, producing unexpected output values for each.

## String Interpolation with Conditional Expressions

```dart
void main() {
  bool isSunny = true;
  String message = 'It is ${isSunny ? 'sunny' : 'cloudy'} today.';
  print(message); // Output: It is sunny today.
}
```

### 💡 Explanation:

This Dart code snippet showcases the use of conditional expressions in string interpolation. It demonstrates how the result of a conditional expression can be directly included in a string using the "${expression ? trueCase : falseCase}" syntax. In this example, the value of the boolean variable `isSunny` determines whether the string "sunny" or "cloudy" is included in the resulting message.

## Behavior with Optional Variables

```dart
void main() {
  String? message;
  print(message?.toUpperCase()); // Output: null
}
```

### 💡 Explanation:

This Dart code snippet demonstrates the use of the null-aware operator with an optional variable. The null-aware operator "?." is used to call the `toUpperCase()` method on the `message` string variable, which is declared as nullable using the `String?` syntax. However, since the message variable is null, the output of the expression is also null, which may be unexpected to developers who are not familiar with the null-aware operator.

# 🤝 Supporting

| Service     |      Link       |                                                                       Action                                                                       |
| ----------- | :-------------: | :------------------------------------------------------------------------------------------------------------------------------------------------: |
| **Patreon** | Become a patron | <a href="https://www.patreon.com/user?u=84015491"><img src="https://c5.patreon.com/external/logo/become_a_patron_button@2x.png" width="120px"></a> |

## License

This repository is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.
