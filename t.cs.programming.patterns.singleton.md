---
id: zel05gaqy1ud01tke98s818
title: Singleton
desc: ''
updated: 1714626772790
created: 1714623141126
---

- 

## Java

To implement a singleton pattern, we have different approaches, but all of them have the following common concepts.

- Private constructor to restrict instantiation of the class from other classes.
- Private static variable of the same class that is the only instance of the class.
- Public static method that returns the instance of the class, this is the global access point for the outer world to get the instance of the singleton class.

### 1. Eager initialization

In eager initialization, the instance of the singleton class is created at the time of class loading. The drawback to eager initialization is that the method is created even though the client application might not be using it.

### 2. Static block initialization 

implementation is similar to eager initialization, except that instance of the class is created in the static block that provides the option for exception handling.

### 3. Lazy Initialization

Lazy initialization method to implement the singleton pattern creates the instance in the global access method.

### 4. Thread Safe Singleton

A simple way to create a thread-safe singleton class is to make the global access method synchronized so that only one thread can execute this method at a time.

  - reduces the performance because of the cost associated with the synchronized method, although we need it only for the first few threads that might create separate instances.

### 5. Bill Pugh Singleton Implementation

Prior to Java 5... the previous approaches used to fail in certain scenarios where too many threads tried to get the instance of the singleton class simultaneously. So Bill Pugh came up with a different approach to create the singleton class using an inner static helper class.

### 6. Using Reflection to destroy Singleton Pattern

Reflection can be used to destroy all the previous singleton implementation approaches.

### 7. Enum Singleton

To overcome this situation with Reflection, Joshua Bloch suggests the use of enum to implement the singleton design pattern as Java ensures that any enum value is instantiated only once in a Java program. Since Java Enum values are globally accessible, so is the singleton. The drawback is that the enum type is somewhat inflexible (for example, it does not allow lazy initialization).

### 8. Serialization and Singleton

Sometimes in distributed systems, we need to implement Serializable interface in the singleton class so that we can store its state in the file system and retrieve it at a later point in time. Here is a small singleton class that implements Serializable.
  - The problem with serialized singleton class is that whenever we deserialize it, it will create a new instance of the class.
  - To overcome this scenario, all we need to do is provide the implementation of readResolve() method.

## References

- https://www.digitalocean.com/community/tutorials/java-singleton-design-pattern-best-practices-examples