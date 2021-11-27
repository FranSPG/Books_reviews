# Clean Architecture: A Craftsman's guide to software structure and design - Robert C. Martin

# Introduction

> Hoards of junior programmers in cube farms around the world slog through massive requirements documents held in huge issue tracking systems to get their systems to “work” by the sheer brute force of will. The code they produce may not be pretty; but it works. It works because getting something to work once—just isn’t that hard. 
Getting it right is another matter entirely. Getting software right is hard. It takes knowledge and skills that most young programmers haven’t yet acquired. It requires thought and insight that most programmers don’t take the time to develop. It requires a level of discipline and dedication that most programmers never dreamed they’d need. Mostly, it takes a passion for the craft and the desire to be a professional.
And when you get software right, something magical happens: You don’t need
hordes of programmers to keep it working. You don’t need massive
requirements documents and huge issue tracking systems. You don’t need
global cube farms and 24/7 programming.
When software is done right, it requires a fraction of the human resources to create and maintain. Changes are simple and rapid. Defects are few and far between. Effort is minimized, and functionality and flexibility are maximized.
> 

# 1. What is Design and Architecture?

> The low-level details and the high-level structure are all part of the same whole. They form a continuous fabric that defines the shape of the system. You can’t have one without the other; indeed, no clear dividing line separates them. There is simply a continuum of decisions from the highest to the lowest levels.
> 

## The Goal?

> The goal of software architecture is to minimize the human resources required to build and maintain the required system.
> 

## What Went Wrong?

> The bigger lie that developers buy into is the notion that writing messy code makes them go fast in the short term, and just slows them down in the long term. [...]
The fact is that ***making messes is always slower than staying clean**,* no matter which time scale you are using.
> 

> ***The only way to go fast, is to go well.***
> 

> The developers may think that the answer is to start over from scratch and redesign the whole system—but that’s just the Hare talking again. The same overconfidence that led to the mess is now telling them that they can build it better if only they can start the race over. The reality is less rosy:
***Their overconfidence will drive the redesign into the same mess as the
original project.***
> 

## Conclusion

> In every case, the best option is for the development organization to recognize and avoid its own overconfidence and to start taking the quality of its software architecture seriously.
To take software architecture seriously, you need to know what good software architecture is. To build a system with a design and an architecture that minimize effort and maximize productivity, you need to know which attributes of system architecture lead to that end.
> 

# 2. A Tale of Two Values

## The Greater Value

> After all, there’s no such thing as a program that is impossible to change. However, there are systems that are practically impossible to change, because the cost of change exceeds the benefit of change. Many systems reach that point in some of their features or configurations.
> 

# 3. Paradigm Overview

> **Structured Programming** imposes discipline on direct transfer of control.
**Object-Oriented Programming** imposes discipline on indirect transfer
of control.
**Functional Programming** imposes discipline upon assignment.
> 

# 4. Structured Programming

## Test

> Dijkstra once said, *“Testing shows the presence, not the absence, of bugs.”* In
other words, a program can be proven incorrect by a test, but it cannot be
proven correct.
> 

# III. Design Principles

> The SOLID principles tell us how to arrange our functions and data structures into classes, and how those classes should be interconnected. The use of the word “class” does not imply that these principles are applicable only to object oriented software. A class is simply a coupled grouping of functions and data. Every software system has such groupings, whether they are called classes or not. The SOLID principles apply to those groupings. 
The goal of the principles is the creation of mid-level software structures that:
• Tolerate change,
• Are easy to understand, and
• Are the basis of components that can be used in many software systems.
> 

> **SRP:** The Single Responsibility Principle 
An active corollary to Conway’s law: The best structure for a software system is heavily influenced by the social structure of the organization that uses it so that each software module has one, and only one, reason to change.
**• OCP:** The Open-Closed Principle 
Bertrand Meyer made this principle famous in the 1980s. The gist is that for software systems to be easy to change, they must be designed to allow the behavior of those systems to be changed by adding new code, rather than changing existing code.
• LSP: The Liskov Substitution Principle
Barbara Liskov’s famous definition of subtypes, from 1988. In short, this principle says that to build software systems from interchangeable parts, those parts must adhere to a contract that allows those parts to be substituted one for another.
• ISP: The Interface Segregation Principle
This principle advises software designers to avoid depending on things that they don’t use.
• DIP: The Dependency Inversion Principle
The code that implements high-level policy should not depend on the code that implements low-level details. Rather, details should depend on policies.
>