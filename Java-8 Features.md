# Java-8-Features

Java 8 (codename: Spider) was released on March 18, 2014.


Features:
- [x] Lambda Expression
- [x] Functional Interface
- [ ] [Default Method in Interface](https://github.com/harshyatishmishra/Java-8-Features/blob/master/Notes/Java8-Default%20Method.md)
- [ ] Predefined Functional Interface -> Predicate, Consumer, Function, Supplier
- [ ] Double Colon Operator :: -> Method reference and Construction reference
- [ ] Stream
- [ ] Date and Time API
- [ ] Optional Class
- [ ] Nashorn JavaScript Engine


## **Lambda Expression**

“LISP” is the first programming which uses Lambda Expression.
The other languages which use lambda expressions are:
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
* If the type of the parameter can be decided by the compiler automatically based on the context then
  we can remove types also.
* If multiple parameters present then these parameters should be separated with a comma (,).
* If zero number of parameters available then we have to use empty parameter [ like ()].
  Ex: ()->sop(“hello”);
* Similar to method body lambda expression body also can contain multiple statements. If more
  than one statement present then we have to enclose inside within curly braces. If one statement
  present then curly braces are optional.
* Once we write lambda expression we can call that expression just like a method, for this
  functional interfaces are required.


## **Functional Interface**

"An Interface which contains Single Abstract Method(SAM)".

*These are the Functional Interface already available in Java. These Interfaces contain only one method.
 ```
  Runnable- run()
  Comparable - compareTo()
  Callable - call()
 ```

* Inside functional interface in addition to a single Abstract method (SAM) we write any number of
  default and static methods.
  
  ```
  interface interfaceEx{
      public abstract void method1();
      default void method2(){
        sop("Interface");
      }
   }
   ```
* Java 8 introduced @Functional Interface annotation to specify that the interface
  is Functional Interface.
```
@FunctionalInterface
Interface interfaceEx{
      public void method1();
}
```
* Compilation error raise :loudspeaker:
  - If we add more than one abstract method in _Function Interface_.
  - If we don't declare any abstract method in _Function Interface_.

###  Inheritance with Function Interface  ###

* If an interface extends Functional Interface and child interface doesn’t contain any abstract method then child interface is also Functional Interface.

```
@FunctionalInterface
interface A {
    public void method1(); 
}
@FunctionalInterface 
 Interface B extends A { 
 }
```
* In the child interface we can define exactly same parent interface abstract method.
```
@FunctionalInterface
interface A { 
    public void methodOne(); 
} 
@FunctionalInterface
interface B extends A { 
    public void methodOne(); 
}
```
* In both parent & child interface we can write any number of default methods and there are no restrictions. Restrictions are 
  applicable only for abstract methods.
```
@FunctionalInterface
interface A {
  public void methodOne();
}
interface B extends A {
  public void methodTwo(); 
}
```
  
* Compilation error raise :loudspeaker:
  - In the child interface we can’t define any new abstract methods otherwise child interface won’t be Functional Interface and
   if we are trying to use @FunctionalInterface annotation then compiler gives an error message.
   
```
@FunctionalInterface { 
interface A { 
      public void methodOne();
} 
@FunctionalInterface
interface B extends A {
    public void methodTwo();
}
```

| Anonymous Inner class | Lambda Expression |
|-----------------------|-------------------|
| It’s a class without name | It’s a method without name (anonymous function) |
| Anonymous inner class can extend Abstract and concrete classes| lambda expression can’t extend Abstract and concrete classes |
| Anonymous inner class can implement An interface that contains any number of Abstract methods | lambda expression can implement an Interface which contains single abstract method (Functional Interface)|
| Inside anonymous inner class we can Declare instance variables.|Inside lambda expression we can’t Declare instance variables, whatever the variables declared are simply acts as local variables.|
| Anonymous inner classes can be Instantiated | lambda expressions can’t be instantiated.|
| Inside anonymous inner class “this” Always refers current anonymous Inner class object but not outer class Object.|Inside lambda expression “this” Always refers current outer class object. That is enclosing class object.|
| Anonymous inner class is the best choice If we want to handle multiple methods.| Lambda expression is the best Choice if we want to handle interface With single abstract method (Functional Interface).|
| In the case of anonymous inner class At the time of compilation a separate Dot class file will be generated (outerclass$1.class)| At the time of compilation no dot Class file will be generated for Lambda expression. It simply converts in to private method outer class.|
| Memory allocated on demand | Whenever we are creating an object Reside in permanent memory of JVM (Method Area).||


Sources:
https://en.wikipedia.org/wiki/Java_version_history#Java_SE_8
