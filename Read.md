# Design Patterns

Design Patterns are elegant solution to repeating problems. e.x. UNDO(){} 
it helps to build reusable, extensible & maintainable software. 

- 23 Design Patterns divided into 3 catogries.

| Pattern Name   | Description                                       |
|----------------|---------------------------------------------------|
| Creational     | All about different ways to create objects        |
| Stuctural      | Relationship between these objects                |
| Behavioural    | Interaction and communcation between these objects|


## 1. Package

A package in java is container of one or more classes.


## 2. Class

Involves bundling the data/attributes/fields and methods/behaviours that operate on that data into a single unit called a class.


## 3. Interface 
 
A contract that specifies the capabilities that a class should provide.
With Interface we can build loosely coupled application.

```java
public interface TaxCalculator {

    float calculateTax(); 

}
```

```java
public class TaxCalculator2019 implements TaxCalculator{

    @Override
    public float calculateTax(){
        return 1;
    }

}
```

```java
public class TaxCalculator2020 implements TaxCalculator{

    @Override
    public float calculateTax(){
        return 2;
    }
    
}
```
- Interface TaxCalculator is very lightweight, as long as we keep signature of calculateTax() same
- we are not going to have a breaking change.

```java
public class Main {

    public static void main (String [] args) {
     
        TaxCalculator calculator = getCalculator();
        calculator.calculateTax();

    }

    public static TaxCalculator getCalculator() { 
        return new TaxCalculator2019();
    }
    
}
```

## 4. Encapsulation 

Object oriented programming principle that helps in hiding the internal implementation details of a class by only exposing the necessary functionalities to the outside world.

Encapsulation abstracts away the complexity of the implementation details, allowing users to focus on high level 
functionality provided by class.

We can prevent our object getting into invalid state.

```java
public class Account {

// public float balance;
   private float balance;

   public void setBalance(float balance){
       if(balance > 0)          // for Some sort of validation  
          this.balance = balance;
   }

}
```

```java
public class Main {

    public static void main (String [] args) {
     
        var account = new Account();
    //  account.balance = -1;
        account.setBalance(-50);

    }
    
}
```

## 5. Abstraction

Reduce complexity by hiding unnessary details.

Object oriented programming principle to reduce complexity by hiding the unnessary details of a class to a user of that class.

```java
public class EmailService {

    public void sendEmail( ){  
    // connectServer(); 
       connectServer(timeout);
       authenticateUser();
       System.out.println("Hi Abhinav, How you Doing!...");
       disconectFromServer();
   }

// public void connectServer( ){   
// private void connectServer( ){   // to make the use of EmailService class simpler for user of that class
   private void connectServer(int timeout){  // We can change implementation of private methods won't affect Main class
      System.out.println("Connected to Email Server...");
   }

// public void authenticateUser(){
   private void authenticateUser(){ // to make the use of EmailService class simpler for user of that class
      System.out.println("User Authenticated...");
   }

// public void disconectFromServer(){
   private void disconectFromServer(){  // to make the use of EmailService class simpler for user of that class
      System.out.println("Disconnected from Email Server...");
   }

}
```

```java
public class Main {

    public static void main (String [] args) {
     
        var emailService = new EmailService();
     // It's like a remote control with only 4 imp buttons rest 46 is hidden and not visible to Main class 
        emailService.sendMail();   

    }
    
}
```

## 6. Inheritance

Object oriented programming principle that involves creating new classes (subclasses or derived classes) based on 
existing classes(superclasses or base classes). Subclasses inherit properties and behaviour from their superclasses and can add new features or overrride existing ones. 

Inheritance is often described in terms of an "is-a" relationship.


## 6. Polymorphism

Ability of a object to take many forms.

```java
public abstract class UIControl{  // Declare the class as Abstract as it has a abstract method.
                                  // we cannot instantiate an abstract class.
    public abstract void draw();  // Abstract method cannot have a body
}
```

```java
public class TextBox extends UIControl{
      
    @Override  
    public void draw(){
        System.out.println("Drawing a textbox...");
    }
}
```

```java
public class CheckBox extends UIControl{
      
    @Override  
    public void draw(){
        System.out.println("Drawing a checkbox...");
    }
}
```

```java
public class Main {

    public static void main (String [] args) {
     
        drawUIControl(new CheckBox());
        drawUIControl(new TextBox());

    }

    public static void drawUIControl(UIControl control){
         control.draw();
    }
    
}
```

## 7. UML(Unified Modeling Language)

-ve sign denote : private
+ve sign denote : public
:int denote datatype of field.

```java
|-----------------|        public class Shape {
|      Shape      |     
|-----------------|               private int positionX;
| - positionX:int |            
| + render()      |               public void render(){}
|-----------------|        }

```

```java
-------------------        
|      Shape      |        // IS-A Relation
|-----------------|        // Rectangle is a Shape                   
         ^                 public class Rectangle extends Shape {
         |
         |
         |
-------------------        }        
|   Rectangle     |     
|-----------------|            
```

```java
-------------------        
|      Shape      |      // HAS-A Relation (Composition Relationship) 
|-----------------|      // Shape class is composed of size class                   
        < >                 public class Shape {
         |                       
         |                       private Size size;
        \|/        
-------------------        }        
|       Size      |     
|-----------------|            
```

```java
-------------------        
|      Shape      |      // (Dependency Relationship) 
|-----------------|      // Somewhere in Shape class we have reference to Document Class                 
         :                  public class Shape {
         :                       
         :                       private void render(Document doc){
        \:/                          
-------------------              }        
|    Document     |     
|-----------------|         }    
```


## Design Patterns

## 1. Momento


















## 1. Reusable Solutions
Provide proven solutions to recurring problems in software design.

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
