# Java-8-Features

Java 8 (codename: Spider) was released on March 18, 2014.


Features:
1. Lambda Expression
2. Functional Interface
3. Predefined Functional Interface -> Predicate, Consumer, Function, Supplier
4. Double Colon Operator :: -> Method reference and Construction reference
5. Stream
6. Date and Time API
7. Optional Class
8. Nashorn JavaScript Engine


**Lambda Expression**
“LISP” is the first programming which uses Lambda Expression.
The other languages which uses lambda expressions are:
```
* C#.Net
* C Objective
* C
* C++
* Python
* Ruby etc.
  and finally in Java also.
```

The Main Objective of Lambda Expression is to bring benefits of functional programming into
Java.

* Lambda Expression is just an anonymous (nameless) function. That means the function which doesn’t have the name, return type and access modifiers.
* Lambda Expression also known as anonymous functions or closures.

Example 1
```
public void m1() {
 sop(“hello”);
}
```
Lambda Expression:
```
() -> {
 sop(“hello”);
 }
() -> { sop(“hello”); }
() -> sop(“hello”);
```

Example 2
```
public int square(int a){
   return a*a;
}
```

Lambda Expression:
```
(int a)->{
    return a*a;
}
(int a)-> a*a;
(a)->a*a;
a->a*a;
```
//() bracket are option when there is only one argument

Example 3
```
public void method(int a, int b){
    System.out.println(a+b);
}

(int a, int b)->{
    System.out.println(a+b);
}


(a, b)->{
    System.out.println(a+b);
}
```
* Without Curly braces, we cannot use the return keyword
* Within curly braces, if we want to return some value compulsory we should use the return statement.
* If the type of the parameter can be decided by compiler automatically based on the context then
  we can remove types also.
* If multiple parameters present then these parameters should be separated with comma (,).
* If zero number of parameters available then we have to use empty parameter [ like ()].
  Ex: ()->sop(“hello”);
* Similar to method body lambda expression body also can contain multiple statements. If more
  than one statements present then we have to enclose inside within curly braces. If one statement
  present then curly braces are optional.
* Once we write lambda expression we can call that expression just like a method, for this
  functional interfaces are required.














Sources:
https://en.wikipedia.org/wiki/Java_version_history#Java_SE_8
