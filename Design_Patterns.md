# Oops Principles :-

### Key Concepts 
- **Encapsulation**
- **Abstraction**
- **Inheritance**
- **Polymorphism**
- **Coupling**
- **Composition**

## 1. Encapsulation

**Class** : Involves bundling the data/attributes/fields and methods/behaviours that operate on that data into a single unit called a class.

**Package** : A package in java is container of one or more classes.

**Encapsulation** : Object oriented programming principle that helps in hiding the internal implementation details of a class by only exposing the necessary functionalities to the outside world.

Encapsulation abstracts away the complexity of the implementation details, allowing users to focus on high level 
functionality provided by class.

## 2. Abstraction

Object oriented programming principle to reduce complexity by hiding the unnessary details of a class to a user of that class.

## 3. Inheritance 

Object oriented programming principle that involves creating new classes (subclasses or derived classes) based on 
existing classes(superclasses or base classes). Subclasses inherit properties and behaviour from their superclasses and can add new features or overrride existing ones. 

Inheritance is often described in terms of an "is-a" relationship.












### Key Features
- **Proven**: Tested and validated solutions.
- **Reusable**: Can be applied to multiple projects.
- **Efficient**: Saves time and effort in design.

### Examples
- Singleton Pattern
- Observer Pattern
- Factory Pattern

### Task List
- [x] Understand the problem
- [x] Identify the pattern
- [ ] Implement the solution
- [ ] Test the implementation

### Table of Patterns
| Pattern Name   | Description                                      |
|----------------|--------------------------------------------------|
| Singleton      | Ensures a class has only one instance            |
| Observer       | Defines a one-to-many dependency                 |
| Factory        | Creates objects without specifying the exact class |

### Code Example
```java
public class Singleton {
    private static Singleton instance;

    private Singleton() {}

    public static Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
}