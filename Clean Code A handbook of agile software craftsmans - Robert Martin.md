# Clean Code: A handbook of agile software craftsmanship - Robert C. Martin

# 1. Clean Code

## The Boy Scout Rule

> If we all checked-in our code a little cleaner than when we checked it out, the code simply could not rot. The cleanup doesn’t have to be something big. Change one variable name for the better, break up one function that’s a little too large, eliminate one small bit of duplication, clean up one composite if statement.
Can you imagine working on a project where the code simply got better as time passed? Do you believe that any other option is professional? Indeed, isn’t continuous improvement an intrinsic part of professionalism?
> 

# 3. Functions

## Do One thing

> Functions should do one thing. They should do it well. They should do it only.
> 

> We can describe the function by describing it as a brief TO4 paragraph: 
TO RenderPageWithSetupsAndTeardowns, we check to see whether the page is a test page and if so, we include the setups and teardowns. In either case we render the page in HTML.
> 

## Flag Arguments

> Flag arguments are ugly. Passing a boolean into a function is a truly terrible practice. It immediately complicates the signature of the method, loudly proclaiming that this function does more than one thing. It does one thing if the flag is true and another if the flag is false!
> 

## 5. Formatting

> You should take care that your code is nicely formatted. You should choose a set of simple rules that govern the format of your code, and then you should consistently apply those rules. If you are working on a team, then the team should agree to a single set of formatting rules and all members should comply. It helps to have an automated tool that can apply those formatting rules for you.
> 

# 6. Objects and Data Structures

## Data Abstraction

> Hiding implementation is not just a matter of putting a layer of functions between the variables. Hiding implementation is about abstractions! A class does not simply push its variables out through getters and setters. Rather it exposes abstract interfaces that allow its users to manipulate the essence of the data, without having to know its implementation.
> 

# 7. Error Handling

## Don't Return Null

> In many cases, special case objects are an easy remedy. Imagine that you have code like this:
> 

```java
List<Employee> employees = getEmployees();
	if (employees != null) {
		for(Employee e : employees) {
			totalPay += e.getPay();
		}
	}
```

> Right now, getEmployees can return null, but does it have to? If we change getEmployee so that it returns an empty list, we can clean up the code:
> 

```java
List<Employee> employees = getEmployees();
	for(Employee e : employees) {
		totalPay += e.getPay();
	}
```

> Fortunately, Java has Collections.emptyList(), and it returns a predefined immutable list that we can use for this purpose:
> 

```java
public List<Employee> getEmployees() {
	if( .. there are no employees .. )
		return Collections.emptyList();
	}
```

> If you code this way, you will minimize the chance of NullPointerExceptions and your code will be cleaner.
> 

# 9. Unit Test

## The Three Laws of TDD

> By now everyone knows that TDD asks us to write unit tests first, before we write production code. But that rule is just the tip of the iceberg. Consider the following three laws:

**First Law** You may not write production code until you have written a failing unit test.

**Second Law** You may not write more of a unit test than is sufficient to fail, and not compiling is failing.

**Third Law** You may not write more production code than is sufficient to pass the currently failing test.
> 

## Test Enable the -ilities

> It is unit tests that keep our code flexible, maintainable, and reusable. The reason is simple. If you have tests, you do not fear making changes to the code! Without tests every change is a possible bug. No matter how flexible your architecture is, no matter how nicely partitioned your design, without tests you will be reluctant to make changes because of the fear that you will introduce undetected bugs. 
But with tests that fear virtually disappears. The higher your test coverage, the less your fear. You can make changes with near impunity to code that has a less than stellar architecture and a tangled and opaque design. Indeed, you can improve that architecture and design without fear!
So having an automated suite of unit tests that cover the production code is the key to keeping your design and architecture as clean as possible. Tests enable all the -ilities, because tests enable change. 
So if your tests are dirty, then your ability to change your code is hampered, and you begin to lose the ability to improve the structure of that code. The dirtier your tests, the dirtier your code becomes. Eventually you lose the tests, and your code rots.
> 

# F.I.R.S.T

> **Fast** Tests should be fast. They should run quickly. When tests run slow, you won’t want to run them frequently. If you don’t run them frequently, you won’t find problems early enough to fix them easily. You won’t feel as free to clean up the code. Eventually the code will begin to rot.
**Independent** Tests should not depend on each other. One test should not set up the conditions for the next test. You should be able to run each test independently and run the tests in any order you like. When tests depend on each other, then the first one to fail causes a cascade of downstream failures, making diagnosis difficult and hiding downstream defects. 
**Repeatable** Tests should be repeatable in any environment. You should be able to run the tests in the production environment, in the QA environment, and on your laptop while riding home on the train without a network. If your tests aren’t repeatable in any environment, then you’ll always have an excuse for why they fail. You’ll also find yourself unable to run the tests when the environment isn’t available.
**Self-Validating** The tests should have a boolean output. Either they pass or fail. You should not have to read through a log file to tell whether the tests pass. You should not have to manually compare two different text files to see whether the tests pass. If the tests aren’t self-validating, then failure can become subjective and running the tests can require a long
manual evaluation.
**Timely** The tests need to be written in a timely fashion. Unit tests should be written just before the production code that makes them pass. If you write tests after the production code, then you may find the production code to be hard to test. You may decide that some production code is too hard to test. You may not design the production code to be testable.
> 

# 10. Classes

## Cohesion

> Classes should have a small number of instance variables. Each of the methods of a class should manipulate one or more of those variables. In general the more variables a method manipulates the more cohesive that method is to its class. A class in which each variable is used by each method is maximally cohesive. In general it is neither advisable nor possible to create such maximally cohesive classes; on the other hand, we would like cohesion to be high. When cohesion is high, it means that the methods and variables of the class are co-dependent and hang together as a logical whole.
> 

## Organizing for Change

> In an ideal system, we incorporate new features by extending the system, not by making modifications to existing code.
> 

# 11. Systems

## Scaling up

> ***Software systems are unique compared to physical systems. Their architectures can grow incrementally, if we maintain the proper separation of concerns.***
>