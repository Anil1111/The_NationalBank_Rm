# The National Bank
# ============

## Project : prjWin_NationalBank_Rm
Été-2017


The objective : To understand the class relationships and the concepts of object oriented programming

[Diagramme de classes UML](https://lipn.univ-paris13.fr/~gerard/docs/corrections/uml-corr02.pdf)

## Getting started

A bank has several agencies spread over the Quebec territory. A bank is characterized by the name of its director, 
its global capital, its own name and the address of its head office.

### Summary of classes:

We have these classes and their propierties.

![Summary of classes](/img/organization.jpg "Summary of classes")

We must complete the following class diagram using the required symbols to specify 
 *abstraction, encapsulation, inheritance, and polymorphism.*

### Summary of classes:


![Class Diagram](/img/classes.jpg "Class Diagram")

We did the analysis and we get the next diagrams.

### abstract class clsAccount:

![Class Diagram Account](/img/account.jpg "abstract class clsAccount")

### abstract class clsHuman:

![Class Diagram Human](/img/human.jpg "abstract class clsHuman")

### Class Diagram Developed:

![Class Diagram Developed](/img/Class_Diagram_StrategyPattern.jpg "Class Diagram Developed")

We implemented with C# and Visual Studio the abstract classes account (clsAccount) and human (clsHuman) and all their offspring.

### Concepts.

#### Encapsulation is -

 * Hiding Complexity,
 * Binding Data and Function together,
 * Making Complicated Method's Private,
 * Making Instance Variable's Private,
 * Hiding Unnecessary Data and Functions from End User.
 
Encapsulation implements Abstraction.

 #### Abstraction is -
 
 * Showing Whats Necessary,
 * Data needs to abstract from End User,
 
[What is the difference between Abstraction and Encapsulation ?](https://www.youtube.com/watch?v=1Q4I63-hKcY)
 
#### Inheritance is -

When we can reuse (inherits), the behavior of a super class (parent class) in a child class (class that inherits the members of the base class).

[Inheritance in C# and .NET](https://docs.microsoft.com/en-us/dotnet/csharp/tutorials/inheritance)

Not all membersfrom the parent class are nherited in the the child class.

 * Static constructors, *which initialize the static data of a class*.
 * Instance constructors, *which you call to create a new instance of the class. Each class must define its own constructors*.
 * Finalizers, *which are called by the runtime's garbage collector to destroy instances of a class*.
 
 
All members from the super class are inherited to the lower classes, but if they are visible or not depends on their accessibility.*

 * Private, *members are visible only in derived classes that are nested in their base class.*
 * Protected, *members are visible only in derived classes.*
 * Internal *members are visible only in derived classes that are located in the same assembly as the base class.*
 * Public, *members are visible in derived classes and are part of the derived class.*
 
 
A child classes can *override* inherited members by providing an implementation in the parent class. 
The member in the parent class have to be marked with the *virtual* keyword.

        Example: from the parent class : public abstract class clsAccount
 
        public virtual bool fncDeposit(double deposit)
        {
            if (deposit < 20 || 500 < deposit)
            {
                return false;
            }
            else
            {
                vBalance += deposit;
                return true;
            }
        }
		
		in the child class : public class clsPaidAccount : clsAccount
		
		public override bool fncDeposit(double deposit)
        {
            vInterestPayment = fncPayInterest(deposit);
            fncPaidAccountPayInterest(vInterestPayment);
            MessageBox.Show("an interest of : " + " " + vInterestPayment.ToString() + " $ " + " has been paid ");
            return base.fncDeposit(deposit);
        }










### Prerequisites

 * Visual Studio.
 * Object-oriented programming.
 * Programming language : C#.


## Versions and source manager. 

This project uses GitHub.com as source manager in the following repository:
https://github.com/RicardoAMendoza/The_NationalBank_Rm

Historique de versions : https://gitlab.com/AndyDelRisco/ConservatoireEMRTM/commits/master

## Auteur

* **Ricardo Mendoza** - *Analyste programmeur Jr* 

## Licence

Ce projet utilise les licences suivantes:
- Copyright Ricardo Mendoza
- the MIT License (MIT)

