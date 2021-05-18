# Data Modeling

## Advantages to Test Driven Development

1. Better program design and higher code quality
2. Detailed project documentation
3. TDD reduces the time required for project development
4. Code flexibility and easier maintenance
5. With TDD you will get a reliable solution
6. Save project costs in the long run

## Downsides of Test Driven Development

- The tests are dependent on external dependencies. So they cannot maintain themselves.
- The tests are hard to write because the code is more complex to write and understand.
- The development of the code is slow. The rapid development of code is not possible because we have to write the test cases first, But it long term the development is very fast.
- The code of TDD is hard to understand as we know writing a code and writing a code well is different. The functionality of TDD is also not discussed, so many team leads only focus on code coverage and it does not tell you anything about code coverage.
- Sometimes we need the whole team when we are writing the unit test cases.
- It is not easy for anyone to learn, especially when someone is trying to learn it on their own. So it requires the efforts to learn it and takes more time.
- There are lots of misunderstandings which stops the person from learning it.
- If we want to refactor in an early stage then we have to refactor the test classes as well.
- If the whole team is not maintaining the tests then there is a change of system degrade.
- Concentrating on the fundamental plan now and not thinking ahead can mean major refactoring prerequisites.

## The case that we would need to use `beforeEach()` or `afterEach()` in a test suite?

To make some setup and restoring configrations for the test to not effect to each other, for example to set some mock states and removing them after each test.

## The primary difference between ES6 Classes and Constructor/Prototype Classes

The most important difference between class- and prototype-based inheritance is that a class defines a type which can be instantiated at runtime, whereas a prototype is itself an object instance.

## Why REST?

1. REST is Easy to Understand and Implement
2. REST Makes your Application More Scalable
3. Caching is Easier with REST
4. REST is Flexibile

## Terms

**Functional programming**: Functional programming (often abbreviated FP) is the process of building software by composing pure functions, avoiding shared state, mutable data, and side-effects. Functional programming is declarative rather than imperative, and application state flows through pure functions. Contrast with object oriented programming, where application state is usually shared and colocated with methods in objects.

**object-oriented programming (OOP)**: Object-oriented programming is a programming paradigm based on the concept of "objects", which can contain data and code: data in the form of fields, and code, in the form of procedures.

**Class**: A class is an extensible program-code-template for creating objects, providing initial values for state (member variables) and implementations of behavior (member functions or methods). *Super class* That class is called a superclass, or parent class. and *this* keyword refere to the object which made from the calss.

**Test-driven development**: Is a software development process relying on software requirements being converted to test cases before software is fully developed, and tracking all software development by repeatedly testing the software against all test cases.

**Jest**: Is a JavaScript testing framework designed to ensure correctness of any JavaScript codebase. It allows you to write tests with an approachable, familiar and feature-rich API that gives you results quickly.

**Continuous integration CI**: Is a coding philosophy and set of practices that drive development teams to implement small changes and check in code to version control repositories frequently.

**REST**: Representational state transfer is a software architectural style which uses a subset of HTTP. It is commonly used to create interactive applications that use Web services. A Web service that follows these guidelines is called RESTful.

**Data Model**: A data model is an abstract model that organizes elements of data and standardizes how they relate to one another and to the properties of real-world entities.
