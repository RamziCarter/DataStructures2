
# Review ABstract Classes
Polymorphism Overview

Abstraction Overview
#### Achieve Abstraction
* Abstaction allows you to focus on using an object and not how it functions
* There are twi tiiks we use

* what is abstraction
   * Abstract classes act as pure base classes
   * they allow partial implementation prodided for subclass use
   * any abstract method means you have to make the whole class abstract

   __all abstract methods must be implemented__


```Java
abstract class Vehicle
{
  private String id;

  Vehicle(String id)
    {
      this.id = id;
    }


  abstract boolean move(int speed);
  // notice the method header is just defined and must end in a semi-colon
  // any class that extends an abstract method MUST implement the move method

}



public static void main (String [] args)
{
Vehicle v = new Vehicle("vinExample");
}

// this will produce abd error

```

An abstract class may have abstract methods with the signiature defined but no implementation
There may also be non-abstract


#### SO what about interfaces?

Interfaces are pure abstraction
  * while an WHile an interface acts in many ways like a class you cannot instantiate an interface object without

  * Interfaces are describes as a contract
#### Review Interfaces

* any method signiatures (return type name and parameters would be included within the interface
* any variable that is declared in an interface is "FINAL"
* all interfaces are abstrat by default


Interfaces can extend other interfaces
Why?

---
Understand the difference between collections and comparable in java
Widely Used Interfaces - The Comparable interfaces

CHoosing between abstract classes and interfaces
* if thre are closely related classes that you want to share a lot of code us an abstract class
* also if you want to use a non static or non final field

* if you think completely unrelated classes would need some methods then use an interface
   * interfaces allow for multiple inheritance   
