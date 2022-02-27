# Read 03: Java Maps, primitives, and File I/O

### arraylist

A dynamic list allow us to

- Store object references as elements.
- Store elements of the same type.
- Access elements by index (just like arrays)
- Add elements
- Remove elements
- Use of generics rather than primitves.

## Java type system and memory?

- primitive in Java consist of

boolean – 1 bit
byte – 8 bits
short, char – 16 bits
int, float – 32 bits
long, double – 64 bits

Memory 

Boolean – 128 bits
Byte – 128 bits
Short, Character – 128 bits
Integer, Float – 128 bits
Long, Double – 192 bits

- reference types as
Integer
Boolean

- every primitve type corresponds to a reference type.
- Objects in Java are slower and have a bigger memory impact than their primitive analogs.

## Exceptions
- An exception is an event that occurs during the execution of a program that disrupts the normal flow of instructions.
- Java uses exceptions to handle errors and other exceptional events.
- an event that occurs during the exectution of a program that disrupts the normal flow of instructions.
- using excetions to manage errors has some advantages over traditional error-management techniques.

### How to catch excetion

- By useing try, catch, and finally blocks
- chained exceptions and logging

### Kinds of Exceptions :

checked exception.
the error.
runtime exception.

## Scanning
Scanning for read form user or from file
import java.util.Scanner;
-  The Obj of type `scanner` are useful for breaking down formatted input into tokens and translating indivdual tokens according to their data type.

### Map

 Map<K,V>
 object that maps keys to values
 A map cannot contain duplicate keys; each key can map to at most one value.
This interface takes the place of the Dictionary class,
 which was a totally abstract class rather than an interface.
