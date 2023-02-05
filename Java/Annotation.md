# Annotation
While studying the spring framework, I felt the need to study java annotation, so I started to study it.  
Annotation is a kind of metadata. It is additional information that tells you how to process code during compilation and execution.  
The advantage of annotation is simplicity. **Reduce unnecessary repetition code** and **focus more on business logic**.  
However, since the intention of annotation is hidden, it is **difficult to understand the logic flow** unless it is clear internally what behavior it does.

<br>

## Index
1. [Role](#1-role)
2. [Usage](#2-usage)

<br>

## 1. Role
When to use annotation
- Inform the compiler to check for code-writing grammar errors
- Provides information so that the software development environment can automatically generate code at build or deployment
- Provides information to run specific functions at runtime

[▲ Top](#annotation)

<br>

## 2. Usage
### 2.1. How to make custom annotation
1. Define annotation
    ```java
    @Target({ElementType.METHOD})
    @Retention(RetentionPolicy.RUNTIME)
    public @interface Annotation {  // Put '@' in front of the interface.
        int var() default 1;        // Append '()' behind the variable name
    }
    ```
2. Place annotation in the class
    ```java
    public class Service {
        @Annotation // <------------------ here
        public void method() {
            // function
        }
    }
    ```
3. Acquire additional information using Reflection and perform the function while the code is being executed.
    ```java
    public class Entry(){
        public static void main(String[] args) {

            Method[] methods = Service.class.getMethods();  // Using reflect

            for (Method method : mothods) {
                if (method.isAnnotationPresent(Annotation.class)) {  // Do if method has annotation above
                    Annotation annotation = method.getDeclaredAnnotation(Annotation.class);
                    System.out.println(annotation.value());
                }
            }
        }
    }
    ```

[▲ Top](#annotation)

<br>

## 3. More information
Visit the links below: The Java™ Tutorials  
https://docs.oracle.com/javase/tutorial/java/annotations/index.html

<br>

## Reference
- [[Java] 자바 어노테이션(Annotation) 사용법 및 예제 - 커스텀 어노테이션 만들기](https://hbase.tistory.com/169)
- [Java에서 어노테이션(Annotation) 이란 무엇인가에 대해 알아보자.](https://honeyinfo7.tistory.com/56)
- [시의적절한 커스텀 어노테이션](https://techblog.woowahan.com/2684/)

[▲ Top](#annotation)

<br>

[← Go back to TIL](https://github.com/jeongyongs/til/)