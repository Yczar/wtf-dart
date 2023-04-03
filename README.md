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

## License

This repository is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.
