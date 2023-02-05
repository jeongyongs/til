# Anonymous Class
Anonymous class is a class for an object that will be used only once while a program is running.  
An object can be created simultaneously with class definition in the method without the need to define the class as a file separately.  
Anonymous class is for reducing code.

<br>

## Index
1. [Usage](#1-usage)
2. [Location](#2-location)
3. [Compile](#3-compile)
4. [Lambda](#4-lambda)

<br>

## 1. Usage
Anonymous class can only use override method. The newly defined method cannot be used externally.  
It can be created using normal class, abstract class, and interface. Among them, it is best to use an interface.
### 1.1. How to make an anonymous class
1. Defind the interface which to create anonymous class.
    ```java
    interface Interface {
        public void method();
    }
    ```
2. Append a code block behind the class definition code. And complete override method.
    ```java
    public class Entry {
        public static void main(String[] args) {

            Interface anonymousObject = new Interface() { // class definition & create anonymous object
                @Override
                public void method() {
                    // function
                }
            }
        }
    }
    ```
### 1.2. Critical point
The critical point of anonymous class is that it is possible to create an object by implementing only one interface.  
Therefore, for multiple inheritance, class must be defined as the file separately and used.

[▲ Top](#anonymous-class)

<br>

## 2. Location
It can be used in various ways depending on where the anonymous class is defined in code.
### 2.1. Field
```java
public class Entry {
    public static void main(String[] args) {

        Interface anonymousObject = new Interface() {   // <--------- field
            @Override
            public void method() {
                // function
            }
        }
    }
}
```
### 2.2. Local variable
```java
public class Entry {
    public static void main(String[] args) {
        public void classMethod() { // define class method

            Interface anonymousObject = new Interface() {   // <--------- local variable
                @Override
                public void method() {
                    // function
                }
            }
        }
    }
}
```
### 2.3. Method parameter
```java
public class Entry {
    public void classMethod(Interface interface) {
        interface.method();
    }

    public static void main(String[] args) {
        classMethod(new Interface() {   // <--------- parameter
            @Override
            public void method() {
                // function
            }
        });
    }
}
```

[▲ Top](#anonymous-class)

<br>

## 3. Compile
Compiling an internal class results in a class name ```.class``` file containing the ```$``` symbol.  
Anonymous class is a kind of internal class, so the same is true.

[▲ Top](#anonymous-class)

<br>

## 4. Lambda
Anonymous class focuses on simplifying complex Java grammar.  
Anonymous implementation objects can be dramatically reduced by using lambda.
### 4.1. Constraint
1. It can only be made with an **interface**.
2. Only an interface with **only one abstract method defined** is possible. *(except for the default method)*
### 4.2. Usage
```java
public class Entry {
    public static void main(String[] args) {

        Interface anonymousObject = () -> {
            // function
        };
    }
}
```
If only have return in method:
```java
public class Entry {
    public static void main(String[] args) {

        Interface anonymousObject = () -> /* return */;
    }
}
```

[▲ Top](#anonymous-class)

<br>

## Reference
- [[JAVA] 익명 클래스(Anonymous Class) 개념 & 문법 정리](https://inpa.tistory.com/entry/JAVA-%E2%98%95-%EC%9D%B5%EB%AA%85-%ED%81%B4%EB%9E%98%EC%8A%A4Anonymous-Class-%EC%82%AC%EC%9A%A9%EB%B2%95-%EB%A7%88%EC%8A%A4%ED%84%B0%ED%95%98%EA%B8%B0)

[▲ Top](#anonymous-class)

<br>

[← Go back to TIL](https://github.com/jeongyongs/til/)