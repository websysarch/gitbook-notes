---
description: Frist Five Principles of Object Oriented Design
---

# SOLID

### Single Responsibility Principle

Each class, module or method should have one and only one responsibility.

Eg. Logging Engine, Below questions should be handled separately and not merged into one.

* What should be written?
* Where should it be written?

#### Identify Violations

Look for LARGE CLASSES which contain lots of functionality, chances are those classes could be broken up into smaller more focused ones. When you're dealing with already small size classes the line is a little less clear as to what is the definition of ‘single’.

### Open/Closed Principle

> A software entity should be open for extension but closed for modification

Implemented using:

* Class Inheritance
* Plug-in mechanism

Makes the code as flexible as possible.

#### Identify Violations

Look for LONG BLOCKS OF IF/ELSE STATEMENTS which check an object’s type and then does some similar action X (but differently) based on the result. When you add a new relevant type the class with this if/else type check code has to be modified to accommodate the new type, whereas the better way would be to use either interfaces or abstract classes.

### Liskov Substitution Principle

> If S is a subtype of T (ie. S extends T), then objects of type T may be replaced with object of type S, without altering any of the desired properties of the program.

This looks similar to Polymorphism, but it is focused on behavioural sub-typing and doesn't talk about compiling etc.

```
var sender = new MailSender()
// In future,
class AdvanceSender extends MailSender {}
var sender = new AdvanceSender()
```

For above, the behaviour of the code should not changed. like throwing new errors, etc. Also, if the new Sender, sends a copy to archive, it breaks the behaviour, even if the code is fully functional, since it added a new functionality.

#### Identify Violations

This one may be a little tougher to spot and indeed is it often the toughest principle for developers to grasp. Look for subclass methods which CHANGE THE BEHAVIOUR (even if only sometimes) of a base class method in such a way that consumers can’t call the derived method and have it ALWAYS behave as if it was the base class method. To find LSP violations look for things like...

Subclasses with overridden methods which throw NOTIMPLEMENTEDEXCEPTION().

Subclass methods which enforce STRICTER RULES ON PARAMETERS THAN THEIR BASE. For example… a base method accepts an integer as parameter but overridden method throws exception if this integer is not positive.

Methods which appear from a signature point of view to operate on a base class (or interface) but then within the method SOME TYPE CHECKING OCCURS.

### Interface Segregation Principle

> Many client-specific interfaces are better than on general-purpose interface.

```typescript
// BAD -> Its bloated
interface IData {
  readData(): string
  validateData(data: string)
  encode(data: string): string
  decode(data: string): string
  sendToExternalSys(string: data): void
}
// GOOD
interface IDataHandler {
    readData(): string
    validateData(data: string)
}
interface IDataEncoder {
    encode(data: string): string
    decode(data: string): string
}
interface IDataSender {
    sendToExternalSys(string: data): void
}
```

#### Identify Violations

Look for LARGE (FAT) INTERFACES with a lot of unfocused methods, also look at interfaces whose clients throw NotImplementedException() a lot.

### Dependency Inversion

> A technique whereby one object, supplies the dependencies of another object.

Makes the code modular, flexible and easy to maintain.

* Injection via factory methods
* Constructor Injection

#### Identify Violations

Look for a LOT OF NEW statements. New statements means concrete instantiations, which means coupling. Better to use a dependency injection framework or even (if you must) poor man’s dependency injection and push the creation of your objects up higher in the stack while simply passing down interfaces which provide a functionality contract but which makes no assertions about how that functionality is implemented.

### Referenced From:

* [Violations from LinkedIn post](https://www.linkedin.com/feed/update/urn:li:activity:6938031422871916545/)

