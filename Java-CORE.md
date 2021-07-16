
Q. When to use || (logical OR) or | (bitwise OR) ?
  
logical OR is for Boolean (user defined, non primitive)
bitwise OR is for boolean(primitive type bool)


Q. Fail Fast vs fail -safe itterator

Failfast fails when try to update value while itteration (hashmap) and throws concurrentmodificationException.

Fail-safe doesn't fail and we can update value on itteration as it with work with clone copy.

Convert normal map to concurrent map `new ConcurrentHashMap(new HashMap());`

Comparable(compareTo method) is used for natural orderling of Person.age , whereas Comparator(compare()) is for different params like person.name,person.dob,person.city etc.


## JAVA core Interview qns
https://www.edureka.co/blog/java-collections/


```
Immutability
Serialization   & de-serialization 
Singleton - multiple instances( read resolve)
Collection - interfaces
Iterators(Types)
Concurrency - Concurrent set list
Iterators- fail fast and fail safe
Comparator and comparable
Volatile- long and double(Inconsistent)
Hashcode - equals contract
Cloning
Lock and wait and notify
thread& Executor
expected o/p ques

Java 
GC
hmap internal working collision
object clone way
blank final var


Spring boot, 

config server 
```
