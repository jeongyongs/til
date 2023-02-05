# Stream
A sequence of elements supporting sequential and parallel aggregate operations.  
The stream can be used without modifying the original data.

<br>

## Index
1. [Why use the stream](#1-why-use-the-stream)
2. [Feature](#2-feature)
3. [Usage](#3-usage)
4. [Performance](#4-performance)

<br>

## 1. Why use the stream
### 1.1. Declarative
More concise and readable.
### 1.2. Assembly of functions
More flexibility. It is divided into intermediate processing and final processing.
### 1.3. Parallelization
Performance improves.

[▲ Top](#stream)

<br>

## 2. Feature
### 2.1. Pipelining
Stream operations return the stream itself so that they can connect together to form a large pipeline.
### 2.2. Internal iteration
Unlike collections that explicitly iterate using repeaters, streams provide internal iterations.  
Therefore, since it is not necessary to define for-loop, it is possible to focus more on logic.
### 2.3. One-off
Streams can only be explored once, and streams that are discovered consume.  
Need to create a new stream to navigate again.

[▲ Top](#stream)

<br>

## 3. Usage
```java
List<String> list = new ArrayList<>();

int sum = list.stream()                         // create a stream
              .filter(w -> w.getColor() == RED) // intermediate processing, return stream object
              .mapToInt(w -> w.getWeight())
              .sum();                           // final processing
```

[▲ Top](#stream)

<br>

## 4. Performance
Basically, for-loop, where internal optimization is already well done, is faster than stream.  
However, in the following situations, the performance difference is insignificant.
1. The size of the stream source is large enough.  
This is because if there is a lot of data, iteration costs are expensive.
2. Computing operations must be very expensive enough.

In summary, when the sum of the iteration cost and the functionality cost is large enough, the speed of the sequential stream approaches for-loop.
### 4.1. Parallel
In general, parallel streams are faster than sequential streams.
However, in the following situations, the performance difference is insignificant.
1. Computing operations cost is very low.  
The reason is that the cost of dividing threads is much higher.
2. Computing operations is stateful.  
Stateful streams actually incur overhead costs of storing and comparing states.  
For each intermediate operation, the thread that has completed the operation does not proceed to the next operation until all other threads have completed the operation. This is called barrier, or algorithmic overhead.
> In my personal opinion, the reason why stream is used a lot is that the code has better readability and better maintenance.  
In addition, the size of the project has increased, so the performance difference between for-loop and stream is not large.

[▲ Top](#stream)

<br>

## Reference
- [Javadoc - Stream (Java Platform SE 8)](https://docs.oracle.com/javase/8/docs/api/java/util/stream/Stream.html)
- [[Java] 스트림(Stream) 이란? 스트림과 컬렉션의 차이점](https://ksr930.tistory.com/237)
- [Java Stream API는 왜 for-loop보다 느릴까?](https://sigridjin.medium.com/java-stream-api%EB%8A%94-%EC%99%9C-for-loop%EB%B3%B4%EB%8B%A4-%EB%8A%90%EB%A6%B4%EA%B9%8C-50dec4b9974b)
- [[Java] 스트림(Stream)](https://girawhale.tistory.com/126)

[▲ Top](#stream)

<br>

[← Go back to TIL](https://github.com/jeongyongs/til/)