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
  - If we add more than one abstract method in ** _Function Interface_ **.
  - If we don't declare any abstract method in ** _Function Interface_ **.

### ** Inheritance with Function Interface ** ###

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



Sources:
https://en.wikipedia.org/wiki/Java_version_history#Java_SE_8
