## Design patterns

DP are solutions to existing problem. DP are divided into three main - 
  - Creational(how objects are created)
      - Singleton
      - Builder
      - Factory
      - Abstract Factory
      - Prototype
  - Structural (How objects are organized/structured assembled to make efficient)
      - Adapter
      - Bridge
      - Decorator
      - Proxy
      - FlyWeight
      - Facade
      - Composite
  - Behavioural (how objects behaves on a action or event)
      - Chain-of-responsibility (approval of employee travel cost)
      - Obserable
      - Command
      - Strategy
      - State
      - Visitor 
      - Itterator
      
      
      
      
      
      

### Structural Patterns


#### FlyWeight DP
It helps to decrease count of number of similar objects created in app, it helps to overcome OutOfMemory error
Object created here are immutable 
As we minimizing creation of objects by sharing, it will be faster 

In flyweight , we use hashmap where wey store key and object. when as user ask for object with given key we return it or create and return it.










