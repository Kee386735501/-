# COMP23311 Software Engineering 

## 1.*Building and Testing Open Source Systems*     

### Building VS Compiling 

- **Building** is done when preparing an application for release, which includes *compiling, packaging, testing,*
- **Compiling** is done at any time the compiler is involved in translating programming language code to machine code.



### Building Process 

1. develop 
2. testing
3. live



### Build Automation 

Automate Building tool: Maven,Ant,Gradle 

Aim: 

1.painless to initial 

2.completely repeatable

3.quick

### Run the tests

release pipelines gateway:

-Code Review 

-Coding standard /documentation procedures 

-Automatic Tests 

### Ant 

Apache Ant (**A**nother **N**eat **T**ool) is an open source project started by [Apache](https://www.javatpoint.com/how-to-install-apache-in-ubuntu) Software Foundation. Ant is a [Java](https://www.javatpoint.com/java-tutorial) library and a software tool used for automate software build processes such as compile, run, test and assemble [Java](https://www.javatpoint.com/history-of-java) application. It is designed and developed by [Apache](https://www.javatpoint.com/how-to-install-apache-web-server-on-centos) Software Foundation and initially released on 19 July 2000.

It is a better alternate of **Make** build tool of Unix. Ant is written in Java and require [JVM](https://www.javatpoint.com/internal-details-of-jvm) to build the [Java projects](https://www.javatpoint.com/free-java-projects).

Ant uses [XML](https://www.javatpoint.com/xml-tutorial) to describe build code and by default it's [XML](https://www.javatpoint.com/what-is-xml) file name is **build.xml**.

## 2.*Understanding Large Software Systems Through Tests* 

### Code Reading : A skill improved with practice

### Code Reading make your brain grow increasing :

​		Understanding of System 

​		Understanding of domain 

​		General technical understanding 

### An active process 

​		Asking questions

​		Formulate hypothesis

​		continually revise ideas   

### Must be combined with other software quality techniques

### Code Reading

​		General Domain Knowledge 

​		Mental Model Of The System

​		General Technical Knowledge 

## 3.*Debugging an Unfamiliar Code Base With Tests* 

#### Syntactical Errors 

1.  The language used to create the code is increate 

2. Capitalizing keywords, Missing parentheses,Missing        semicolon,  forgetting to import a type,etc.

3. Easy to deal with(most of the time)

4. Advanced IDES complain and won't compile

   

   

#### Conceptual Errors(Bugs)

- The language used to create the code is correct 

- There are no syntactical errors 

- The IDE is happy,and is able to compile the code 

- Logical  errors : the code does not work as intended 

-  Harder to spot(especially in large database)

  

#### Software Bugs 

- Refer to faults, errors or flaws in a codebase 
- Could be in the source code or in the system design
- Lead to incorrect or unexpected results or behaviour
- Origins of term:'The first actual case of bug being found

#### A Systematic Approach 

Uses systematic  approaches and formal techniques 

1. Start with the problem

2. Stabilise the problem 

3. isolate the source of the problem

4. Fix the problem

5. Test the fix 

6. Look at similar errors

   

#### 1-Start with a Problem

###### Confirm the reported problem by replicating it

- Make sure you understand the expected correct behaviour of the System

- Run the code to(using the same input data and conditions that created the reported problem)

- Observe the actual behaviour 

  

If the bug cannot be replicated 

-Make sure that you are running the code under same conditions that create the bug

-Request more info/discuss with the person who reported it 

#### 2-Stabilise the Problem

**Narrow** the problem to as **precise** a **statement** as is possible

e.g. "The save as feature of the application dose not work"

 Initially,this may be achieved using execution only 

Use test cases where appropriate

#### 3- Isolate the Source of the Problem 

###### Strategies

- ***Brute force***: work through the code from start to finish until you notice something odd 

- **Back-tracking**: start from the point at which a particular problem is detected and work backwards until you find the cause 

- **Binary search**: approximate the "middle" of the execution flow for this problem. Can you determine whether the error is manifest at that point?If so, find the middle of the first half if the execution; If not find the middle of the second half;If not find the middle of the second half - repeat

- **Cause elimination**: identify as many possible causes of the problem as possible. Work through them systematically, only ruling one out where you can prove that it must not be 

  the cause 

  ​         

###### Tactic

- **Print statement/console output**

- **Rubber Ducking**: just explain exactly the code is doing to someone else 

- Look for Common Problems: logical inversion,boundary errors,poor code,etc 

- IDE debugging tools: **break point** 

- **Test cases**: Instrument any code you're suspicious of tests 

- **Git commit logs**: Look at what's changed recently.

  Which commits altered which lines of each file



######  Use a combination: a strategy + a tactic

- **Cause elimination + tests** :- For each possible cause, write a test. Test that pass rule out causes

- Cause elimination + online debugger: - Step throw the code

  associated with each possible cause - is the state correct or incorrect?

- **Cause elimination + print statements** -For each possible cause, write a print statement before/after- Is the state correct or incorrect?

- **Binary search + print statement** -print the state out at the midpoint of execution,mid-way through the first half of the 

  execution flow,midway through the second quarter of the execution flow

  

#### 4-Fix the Problem 

- This is usually the easy part(compared to finding the problem)

- Double check with a teammate to make sure that your work is correct

  

#### 5-Test the Fix 

- Just run the tests you already have 

  

#### 6-Look for Similar Errors 

- Find at least one other occurrence of the method you've modified being called. Can you prove that this code behaves as intended

  

## *4.Cost estimate*

####      Cost Estimate

- Estimate the effort,resources and schedule for software projects 

  -effort

  -resources

  -Schedule

  

  

  

####       Work Breakdown Structures

- A hierarchical decomposition of a task/goal into smaller scales tasks or goals 
- The 100% Rule

####         WBS Example 

-    1.Fix bug about player losing health points between 5.00am to 7.00am in the morning

- 1.1Relicate the bug

  -  1.1.1 Replicate the bug manually
  - 1.1.2 Gather missing info reporter
  - 1.1.3 Find tests for this or similar functionally
  - 1.1.4 Write test that reveals the bug

- 1.2 Fix the bug

- 1.3 Check that the bug is really fixed 

- 1.4 Push the bug to the repository

- 1.5 Make sure the same bug doesn't exist elsewhere

  

## *5. Test-First Develop*

Test-Driven Development (TDD) or Test-First Development

#### Driver and Stubs

![image-20230122213649621](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230122213649621.png)

- A depends on B, which do you implement first
- How do you test your work A , while someone else work on B

​              Testing Class B

-  if we want to test class B, but class A isn't ready for testing , so we create a Driver class for B it is a slim version of Class A. Class A will eventually call B . If Class A is Test of B,we use that to test B. This

  is "Normal test after develop" 

  

  Testing Class A

- If B isn't ready for testing(or exist),we use 

  a stub version of B .

  Now A is the test for B, We write it first 

​                  it will false at first, when B fleshed out 

​                  Then part of A will begin to pass. When

​                 all of them are green it's down.

​                  This is "TDD" 

####            TDD Process 

![image-20230122220952754](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230122220952754.png)



## *6.Git Workflows*

#### 6.1 Definition

Git workflows are patterns of collaborative usage of Git that work well for particular team configuration and  project requirement 

6.2 What thy Specify 

![image-20230122222936005](C:\Users\38673\AppData\Roaming\Typora\typora-user-images\image-20230122222936005.png)

6.3 Lines of Development



 

## 7.Refactoring for Software Quality

#### 7.1 Functional/Non-Functional Requirement

- Functional Requirement(FR)
  - What features the system should implement 
  - Example:"player should be  able to chat to each other in game"

-  Non-Functional Requirement(NFR)
  - Quality criteria not related to system functionality/features
  - Example:"the system should support real time play for at least 100 simultaneous player"

#### 7.2 Performance 

- **Throughput**: how many requests must be handled to

- **Capacity**: how many simultaneous requests/users must be supported at the same time?

- **Scalability**: how many growth in number of request/user/volume of tasks must be supported over a certain period of time

- **Availability**: how much *downtime* is allowed

  

#### 7.3 Maintainability

- Readability: how easy should it be for the development team to work out what an unfamiliar part of the code does

- Extensibility: how easy should it be to add additional functionality to the code

-  Portability: how easy should it be to make the code run on a different platform/hardware/environment/browser/etc

- Localisability: how easy should it be to make the code suitable for use in different geographical/linguistic/cultural areas

    		

#### 7.4 Kinds of Code Change Revisited

- Perfective Change

- Corrective Change

- Adaptive Change

- Preventive Change

  

#### 7.5 Morden Approach to Code Quality

- Keep costs low by keeping scale of preventive changes small where possible
- Use tool to support to reduce and risks
- Use a comprehensive test suit to reduce the risks
- Use knowledge of common patterns to reduce costs and risks

#### 7.6 Code Smells 

A code pattern that may suggests the presence of poor code quality

e.g. Too many Parameters 

- Method with parameters

- Can indicate a missing class

#### 7.7 Technical Debt

poor quality code/design knowingly introduced into the code base, in order to meet delivery goals

#### 7.8 Software Refactoring 

A Software Refactoring  was originally a common pattern of code change

#### 7.9 Patterns of Code Change 

- A frequently occurring code change 

- Usually small in scale

- Example: 
  - Renaming a method or class

#### 7.9.1 Software Refactoring and Tests

in practice, a "software refactoring"is now a change to code that improves some NFR but does not cause functional regression

## 8.Design for Testability

#### 8.1What is testability

- A non-functional requirement
- Testable code is easy to put under test

#### 8.2 What is Design for Testability

- Make sure that we can test what we build
- letting testability concerns drive the design of production code

####       8.3 What Stops Code from being Testable

-   Non-deterministic code

- Hard-coding/hiding behaviour inappropriately

- Not allowing inheritance/overriding

  -Static code

  -constructors

- Complex/slow configuration requiremeny

- Breaking the Law of Demeter

#### 8.4 Controlling the Collaborating Objects

- When we wish to put a class under test, we need to be able to control the behaviour of the classes it collaborates with

- We use a "test double" to do this

- A test double is a version of a production code object whose behaviour is

  predictable/controllable in a way that helps us write the test

- Type of Test Double    

  - Mocks 

  ​          -Test double created on-                the-fly with behaviour that matches programmed expectations

  - Dummies

    -Passed around but never actually used. Often used to fill parameter lists

  - Stubs

    -Provide canned answers to calls made during the test

  - Fakes

    -Have working implementation,but take some short-cuts 

    compared to the production object

    

    

    

## 9.Software Design Patterns

#### 9.1 What is a Design Pattern

reusable design solution to recurring design problem

#### 9.2 Three group of Patterns

Behavioural Patterns

Structural Patterns

Creational Pattern

## 10.Risk Management

10.1What is a software risk

